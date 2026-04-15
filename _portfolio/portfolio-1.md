---

title: "Arduino LM35 Temperature Monitoring System"
excerpt: "Multi-sensor temperature monitoring system using Arduino and LM35 with real-time output (CSV/JSON)<br/><img src='/images/500x300.png'>"
collection: portfolio
---------------------

This project implements a temperature monitoring system using LM35 sensors connected to an Arduino board. The system reads temperature data from multiple analog channels (A0, A1, A2), converts ADC values into Celsius, and outputs the results in real time.

The project supports both CSV and JSON formats, making it suitable for IoT applications and data visualization. A PC application (C# Windows Forms) is used to display temperature values, while Proteus is used for simulation.

Key features include:

* Multi-channel temperature sensing (A0, A1, A2)
* ADC to temperature conversion (°C)
* Real-time Serial communication
* Output formats: CSV and JSON
* Modular and scalable design

Example Arduino code:

```cpp
int sensorPins[3] = {A0, A1, A2};

void setup() {
  Serial.begin(9600);
}

void loop() {
  float temp[3];

  for (int i = 0; i < 3; i++) {
    int adc = analogRead(sensorPins[i]);
    temp[i] = (adc * 500.0) / 1023.0;
  }

  Serial.print("{\"temp1\":");
  Serial.print(temp[0]);
  Serial.print(",\"temp2\":");
  Serial.print(temp[1]);
  Serial.print(",\"temp3\":");
  Serial.print(temp[2]);
  Serial.println("}");

  delay(1000);
}
```

GitHub repository:
https://github.com/Hui-2304/Arduino_LM35_TempMonitor

This project demonstrates embedded system design, IoT integration, and version control using Git and GitHub, including branching, merging, and collaboration workflows.

