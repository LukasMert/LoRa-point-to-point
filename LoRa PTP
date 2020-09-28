#include <SPI.h>
#include <LoRa.h>

int counter = 0;
int val;
int sensorPin = A10;

void setup() {
  Serial.begin(9600);
  while (!Serial);

  Serial.println("LoRa Sender");

  if (!LoRa.begin(8681E5)) {
    Serial.println("Starting LoRa failed!");
    while (1);
  }
}

void loop() {
  val = digitalRead(sensorPin);
  Serial.print("Sending packet: ");
  Serial.println(counter);

  Serial.println("Vocht");
  Serial.println(val);

  LoRa.print(val);
  LoRa.endPacket();

  counter++;

  delay(100000);
}
