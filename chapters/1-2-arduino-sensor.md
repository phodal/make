Arduino 传感器控制
===

传感器入门
---

> 传感器是一种物理装置或生物器官，能够探测、感受外界的信号、物理条件（如光、热、湿度）或化学组成（如烟雾），并将探知的信息传递给其他装置或器官。“传感器”在新韦式大词典中定义为：“从一个系统接受功率，通常以另一种形式将功率送到第二个系统中的器件”。根据这个定义，传感器的作用是将一种能量转换成另一种能量形式，所以不少学者也用“换能器－Transducer”来称谓“传感器－Sensor”。[^wiki_sensor]

[^wiki_sensor] : https://zh.wikipedia.org/wiki/%E4%BC%A0%E6%84%9F%E5%99%A8

### 模拟元件与数字元件

超声波传感器
---


![Arduion 超声波传感器连线图](./images/arduino/arduino-hs-sr04.png)

使用到库：[NewPing]，GitHub 地址：[https://github.com/PaulStoffregen/NewPing](https://github.com/PaulStoffregen/NewPing)

![下载 Zip 格式](./images/arduino/download-zip.png)

添加库

![添加 NewPing 库](./images/arduinoadd-zip-library.png)


```c
#include <NewPing.h>

#define TRIGGER_PIN  12  // Arduino pin tied to trigger pin on the ultrasonic sensor.
#define ECHO_PIN     11  // Arduino pin tied to echo pin on the ultrasonic sensor.
#define MAX_DISTANCE 200 // Maximum distance we want to ping for (in centimeters). Maximum sensor distance is rated at 400-500cm.

NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE); // NewPing setup of pins and maximum distance.

void setup() {
  Serial.begin(115200); // Open serial monitor at 115200 baud to see ping results.
}

void loop() {
  delay(50);                     // Wait 50ms between pings (about 20 pings/sec). 29ms should be the shortest delay between pings.
  Serial.print("Ping: ");
  Serial.print(sonar.ping_cm()); // Send ping, get distance in cm and print result (0 = outside set distance range)
  Serial.println("cm");
}
```

![输出示例](serial-output-example.png)

控制继电器
---
