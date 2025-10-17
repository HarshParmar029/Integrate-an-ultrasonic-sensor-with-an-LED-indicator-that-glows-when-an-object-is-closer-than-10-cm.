// Ultrasonic Sensor with LED Indicator
// LED glows when object is closer than 10 cm

long duration;
float distance;

void setup() {
  pinMode(9, OUTPUT);
  pinMode(10, INPUT);
  pinMode(13, OUTPUT);
  Serial.begin(9600);
}
void loop() {
  // Send ultrasonic pulse
  digitalWrite(9, LOW);
  delayMicroseconds(2);
  digitalWrite(9, HIGH);
  delayMicroseconds(10);
  digitalWrite(9, LOW);

  // Measure echo time
  duration = pulseIn(10, HIGH);

  // Calculate distance in cm
  distance = duration * 0.034 / 2;

  // Print distance to Serial Monitor
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  // LED condition
  if (distance < 10 && distance > 0) {
    digitalWrite(13, HIGH);  // Object is close
  } else {
    digitalWrite(13, LOW);   // Object is far
  }

  delay(200); // Small delay for stability
}
