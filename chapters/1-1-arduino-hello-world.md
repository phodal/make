Arduino Hello, World
===

开发板选择
---

![Arduino 开发板示例](./images/arduino/arduinos.jpg)

![扩展板](./images/arduino/shields.jpg)

Arduino IDE 默认会安装相应环境的包，如果你的开发板不在这些环境里，如你使用的是 Arduino M0 开发板。那么，系统可能会检测出来，并自动为你安装相应的环境，如下图所示。

![](./images/arduino/arduino-install-package.png)

对于非官方的开发板来说，则需要开发者自己手动通过『开发板管理器』来安装。


hello, world
---

与桌面端使用 print、puts、console.log 来输出 Hello, world 不同的是，点亮一个 LED 是 电子世界的 Hello, world。


官方的 Blink 示例如下：

```c
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);                       // wait for a second
}
```


### setup()

源码中的：

```c
int main(void)
{
    init();
    setup();
    for(;;)
        loop();

    return 0;
}
```

### loop()

输入控制输出
---

GOAL

SMART 原则 

仍然采用的是官方的示例：

![Arduino 控制 LED 示例](./images/arduino/fritzing-button.png)

官方示例（[Digital Read Serial](https://www.arduino.cc/en/Tutorial/DigitalReadSerial)）代码：

```c
// digital pin 2 has a pushbutton attached to it. Give it a name:
int pushButton = 2;

// the setup routine runs once when you press reset:
void setup() {
  // initialize serial communication at 9600 bits per second:
  Serial.begin(9600);
  // make the pushbutton's pin an input:
  pinMode(pushButton, INPUT);
}

// the loop routine runs over and over again forever:
void loop() {
  // read the input pin:
  int buttonState = digitalRead(pushButton);
  // print out the state of the button:
  Serial.println(buttonState);
  delay(1);        // delay in between reads for stability
}
```

### 电路图

使用 Fritzing 画板时

![](./images/arduino/fritzing-example.jpg)

我们所需要的连线图

![](./images/arduino/arduino-button.jpg)
