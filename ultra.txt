#include <WiFi.h>
#include <WebServer.h>
#include <DHT.h>

#define TRIG 5
#define ECHO 18
#define DHTPIN 4
#define DHTTYPE DHT11
#define BUZZER 15
#define RELAY 13

DHT dht(DHTPIN, DHTTYPE);

WebServer server(80);

const char* ssid = "ultra";
const char* password = "12345678";

bool pumpState = false;

long getDistance() {
  digitalWrite(TRIG, LOW);
  delayMicroseconds(3);
  digitalWrite(TRIG, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG, LOW);

  long duration = pulseIn(ECHO, HIGH, 30000);
  return duration * 0.034 / 2;
}

void handleWebpage() {
  float t = dht.readTemperature();
  float h = dht.readHumidity();
  long d = getDistance();

  String page = "<html><body style='text-align:center;'>";
  page += "<h2>ESP32 Monitor</h2>";
  page += "Distance: " + String(d) + " cm<br>";
  page += "Temp: " + String(t) + " C<br>";
  page += "Humidity: " + String(h) + " %<br>";
  page += "<br>Pump: " + String(pumpState ? "ON" : "OFF") + "<br><br>";

  page += "<a href='/pumpON'><button>Pump ON</button></a>";
  page += "<a href='/pumpOFF'><button>Pump OFF</button></a>";

  page += "</body></html>";

  server.send(200, "text/html", page);
}

void pumpOn() {
  pumpState = true;
  digitalWrite(RELAY, LOW);
  server.sendHeader("Location", "/");
  server.send(303);
}

void pumpOff() {
  pumpState = false;
  digitalWrite(RELAY, HIGH);
  server.sendHeader("Location", "/");
  server.send(303);
}

void setup() {
  Serial.begin(115200);

  pinMode(TRIG, OUTPUT);
  pinMode(ECHO, INPUT);
  pinMode(BUZZER, OUTPUT);
  pinMode(RELAY, OUTPUT);

  digitalWrite(RELAY, HIGH);

  dht.begin();

  // ---- AP MODE ----
  WiFi.mode(WIFI_AP);
  WiFi.softAP(ssid, password);

  delay(1500);  // IMPORTANT — AP fully start hoy

  Serial.println("Hotspot created.");
  Serial.print("SSID: "); Serial.println(ssid);
  Serial.print("PASS: "); Serial.println(password);

  // ---- AP IP PRINT FIX ----
  IPAddress apIP = WiFi.softAPIP();
  Serial.print("ESP32 AP IP: ");
  Serial.println(apIP);   // Ei line e IP PRINT HOIBE 100000%

  server.on("/", handleWebpage);
  server.on("/pumpON", pumpOn);
  server.on("/pumpOFF", pumpOff);

  server.begin();
  Serial.println("Web server started.");
}

void loop() {
  server.handleClient();

  long distance = getDistance();
  float temperature = dht.readTemperature();
  float humidity = dht.readHumidity();

  // Buzzer pattern (your style)
  if (distance > 0 && distance < 10) {
    digitalWrite(BUZZER, HIGH);
    delay(80);
    digitalWrite(BUZZER, LOW);
    delay(50);
  } else {
    digitalWrite(BUZZER, LOW);
  }

  // Auto pump safety
  if (temperature >= 40 || humidity >= 90) {
    pumpState = true;
    digitalWrite(RELAY, LOW);
  }
}


// SSID: ultra
// PASS: 12345678
// ESP32 AP IP: 192.168.4.1
