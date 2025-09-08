# Bluetooth-Wi-Fi-Range-Testing
To experimentally measure RSSI (Received Signal Strength Indicator) at different distances and analyze path loss.
#include "WiFi.h"

// Replace with your Wi-Fi network
const char* ssid     = "YOUR_WIFI_SSID";
const char* password = "YOUR_WIFI_PASSWORD";

void setup() {
  Serial.begin(115200);
  delay(1000);

  WiFi.begin(ssid, password);
  Serial.println("Connecting to Wi-Fi...");

  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  Serial.println("\nConnected!");
}

void loop() {
  long rssi = WiFi.RSSI();   // Get signal strength in dBm
  Serial.print("RSSI: ");
  Serial.println(rssi);      // Send RSSI to Serial Monitor
  delay(1000);
}
