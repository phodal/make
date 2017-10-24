Arduino Hello, World
===

开发板选择
---

![Arduino 开发板示例](arduinos.jpg)

![扩展板](shields.jpg)

Arduino IDE 默认会安装相应环境的包，如果你的开发板不在这些环境里，如你使用的是 Arduino M0 开发板。那么，系统可能会检测出来，并自动为你安装相应的环境，如下图所示。

![](arduino-install-package.png)

对于非官方的开发板来说，则需要开发者自己手动通过『开发板管理器』来安装。


hello, world
---

与桌面端使用 print、puts、console.log 来输出 Hello, world 不同的是，点亮一个 LED 是 电子世界的 Hello, world。


官方的 Blink 示例如下：

```
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

```
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

### 电路图

使用 Fritzing 画板时

![](./images/arduino/fritzing-example.jpg)

我们所需要的连线图

![](./images/arduino/arduino-button.jpg)
