# Esp_Challenge
#include <WiFi.h>
#include <WebServer.h>

// Wi-Fi ağ bilgilerinizi buraya girin
const char* ssid = "sky-lab"; // Wi-Fi ağ adınız
const char* password = "sky-labharika"; // Wi-Fi ağ şifreniz

// Web sunucusu portu (varsayılan: 80)
WebServer server(80);

// LED pini
const int ledPin = 2; // ESP32 üzerinde yerleşik LED GPIO2 pininde

// LED durumu                                                                                                                                                                                                                                                                                                                                                                                bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbö
bool ledState = false;

// Root (ana) URL'ye yapılan GET isteğine yanıt verecek fonksiyon
void handleRoot() {
  String html = "<html><body><h1>ESP32 Web Sunucusu</h1>";
  html += "<p>LED Durumu: ";
  html += (ledState) ? "Açık" : "Kapalı";
  html += "</p>";
  html += "<button onclick=\"toggleLED()\">LED'i Aç/Kapat</button>";
  html += "<script>function toggleLED() { fetch('/toggle'); }</script>";
  html += "</body></html>";
  server.send(200, "text/html", html);
}

// LED durumunu değiştiren fonksiyon
void handleToggle() {
  ledState = !ledState;
  digitalWrite(ledPin, ledState ? HIGH : LOW);
  server.send(200, "text/plain", "OK");
  handleRoot(); // Sayfayı güncellemek için ana sayfayı tekrar yükle
}

void setup() {
  // Seri iletişimi başlat
  Serial.begin(115200);
  
  // LED pinini çıkış olarak ayarla
  pinMode(ledPin, OUTPUT);
  digitalWrite(ledPin, LOW);

  // Wi-Fi'ye bağlanma girişimi
  Serial.println();
  Serial.print("Wi-Fi'ye bağlanıyor ");
  Serial.println(ssid);

  // Wi-Fi modülünü başlat ve belirtilen SSID ve parola ile Wi-Fi'ye bağlan
  WiFi.begin(ssid, password);

  // Bağlanana kadar bekle
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }

  // Bağlanıldığında IP adresini yazdır
  Serial.println("");
  Serial.println("Wi-Fi'ye başarıyla bağlanıldı!");
  Serial.print("IP Adresi: ");
  Serial.println(WiFi.localIP());

  // Root URL için fonksiyonu ayarla
  server.on("/", handleRoot);
  
  // LED durumunu değiştiren URL için fonksiyonu ayarla
  server.on("/toggle", handleToggle);

  // Web sunucusunu başlat
  server.begin();
  Serial.println("Web sunucusu başlatıldı.");
}

void loop() {
  // Sunucuya gelen istemcileri işle
  server.handleClient();
}

