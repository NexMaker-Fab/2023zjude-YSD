# <font color="#99CCFF">Arduino Input & Output</font>

## 1 Arduino Input Program

### 1.1 Introduction
With the increasingly serious problem of environmental pollution, living conditions have been greatly improved, and people's attention to the environment has also greatly increased. Based on this, our team have designed and developed a project that integrates multiple functions such as measuring temperature, humidity, PM2.5, water level, and soil moisture.

### 1.2 Experiment

#### 1.2.1 Experimental Purpose

The project plans to implement some functions of a real weather detection system, by using sensors for environmental detection to collect and detect data. Implement a project design that integrates multifunctional monitoring.

#### 1.2.2 Experimental design

1. Accurate measurement of temperature and humidity, PM2.5, water level, and soil moisture sensor data;
2. When the specified range value is exceeded, the RGB light can light up the corresponding color note, and the buzzer will sound;
3. LCD screen display: scrolling display, button switching display, infrared button for screen switching+infrared button (press a certain key to go to a specified value).

#### 1.2.3 List of components

- Arduino UNO * 1
- Breadboard * 2
- DHT11 temperature and humidity sensor * 1
- PM2.5 sensor * 1
- YL-69 soil humidity sensor * 1
- water level sensor * 1
- buzzer * 1
- LCD display screen * 1
- potentiometer * 1
- Some Dupont threads

#### 1.2.4 Schematic circuit diagram

- Connect the relevant components according to the wiring diagram.

<div align="center">
 <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/environment_wire.png" width=400/>
</div>

<div align="center">
 <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/environment_photo.png" width=400/>
</div>

- Write code in the Arduino IDE.

<div align="center">
 <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/environment_code.png" width=400/>
</div>

- Upload the code.
<br>

- Debug, run and test.
<br>

#### 1.2.5 Code

```C++
#include <dht11.h>
#include <ESP8266WiFi.h>
#include <WiFiClient.h>
#include <ESP8266WebServer.h>
const char *ssid = "SEKIRO";
const char *password = "01010101";
ESP8266WebServer server(80);
dht11 DHT11;
#define DHT11PIN  D2
#define pin_A0 D3
#define pin_D0 D4 
#define waterpin D5
#define mqApin D6
#define mqDpin D7
unsigned int samplingTime = 280;
unsigned int deltaTime = 40;
unsigned int sleepTime = 9680;
float voMeasured = 0;
float calcVoltage = 0;
float dustDensity = 0;
void handleRoot() {
  float h = getHumidity();
  float t = getTemperature();
  float s=getsoil();
  float m=getmq();
  float w=getwaterlevel();
  String str = "<head><meta charset=\"utf-8\" /><title>ESP-12E试验</title></head><h1>当前湿度(%):";
  str += String(h);
  str += "<br>当前温度(℃):";
  str += String(t);
  str += "<br>当前土壤湿度（%）:";
  str += String(s);
  str += "<br>可燃气体浓度（%）：";
  str += String(m);
  str += "<br>水位（cm):";
  str += String(w);
  str += "</h1>";
  server.send(200, "text/html", str);
}
void setup() {
  delay(1000);
  Serial.begin(115200);
  Serial.println();
  Serial.print("Configuring access point...");
  WiFi.softAP(ssid, password);
  IPAddress myIP = WiFi.softAPIP();
  Serial.print("AP IP address: ");
  Serial.println(myIP);
  server.on("/", handleRoot);
  server.begin();
  Serial.println("HTTP server started");
  pinMode(mqApin,INPUT);
}
float getHumidity()//湿度
{
  int chk = DHT11.read(DHT11PIN);
  return (float)DHT11.humidity;
}
float getTemperature()//温度
{
int chk = DHT11.read(DHT11PIN);
return (float)DHT11.temperature;
}
float getsoil()//土壤
{
  int ao=analogRead(pin_A0);
  int soil=map(ao,0,1023,100,0);
  return soil;
}
float getmq()//可燃气体
{
  int mqbite=0;
  int mqval=0;
  float mqvot=0;
  mqval=analogRead(mqApin);
  mqvot= mqval*0.0049;
  return mqval;
}
float getwaterlevel()//水位
{float a,waterlevel;
   a=(long)analogRead(waterpin);
  waterlevel=abs((a/650)*4-0.13);
  return waterlevel;
}
void loop()
{
  server.handleClient();
}
```

### 1.3 Video Presentation
**We uploaded the demonstration video to the YouTube.**

<iframe width="480" height="360" src="https://www.youtube.com/embed/iA5BMdU4myI?si=eRnwno4qKqoCv8X9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen>
</iframe>

## 2 Arduino Output Program
### 2.1 Introduction
This project is a simple attempt to use Arduino to control the servo. The desired result is for the servo to rotate from 0 ° to 180 °, and then from 180 ° to 0 °.
### 2.2 Experiment
#### 2.2.1 List of components

 - Arduino UNO * 1
 - Servo * 1
 - Some Dupont threads

#### 2.2.2 Schematic circuit diagram

- Connect the relevant components according to the wiring diagram.

<div align="center">
 <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/servo_wire.png" width=400/>
</div>

- Write code in the Arduino IDE.

<div align="center">
 <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/servo_code.png" width=400/>
</div>

- Upload the code.
<br>

- Debug, run and test.
<br>

#### 2.2.3 Code

```C++
#include <Servo.h>
 
Servo myservo;  // 定义Servo对象来控制
int pos = 0;    // 角度存储变量
 
void setup() {
  myservo.attach(9);  // 控制线连接数字9
}
 
void loop() {
  for (pos = 0; pos <= 180; pos ++) { // 0°到180°
    // in steps of 1 degree
    myservo.write(pos);              // 舵机角度写入
    delay(5);                       // 等待转动到指定角度
  }
 
  for (pos = 180; pos >= 0; pos --) { // 从180°到0°
    myservo.write(pos);              // 舵机角度写入
    delay(5);                       // 等待转动到指定角度
  }
}
```
### 2.3 Video Presentation

<div align="center">
 <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/GIF%202023-11-7%2021-45-42.gif" width=400/>
</div>

