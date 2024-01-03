# <font color="#99CCFF">IoT(Internet of Things)</font>

## 1 Introduction 

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/Top-10-IoT-Startups-Of-2019-According-to-IoT-Analytics.jpg" width = "800"/>
</div>

**IoT (Internet of Things)** is a system of computing devices, machines, and digital machines in relation to each other, with a universally unique identifier (UUID) and the ability to transmit data over a network without the need for person-to-person or person-to-device interaction

The Internet of Things digitizes the real world and has a wide range of applications. The Internet of Things can narrow dispersed data and integrate digital information between things. The application areas of the Internet of Things mainly include the following aspects: transportation and logistics, industrial manufacturing, health care, intelligent environment (home, office, factory), personal and social fields.

The Internet of Things is an emerging area of attention from all walks of life, but security is the main factor questioned by all walks of life, the main question is that the Internet of Things technology is developing rapidly, but the security challenges involved, and the regulatory changes that may be needed, are currently quite lacking.

## 2 Use arduino to program ESP32C3 and control LED

### 2.1 Hardware overview

#### 2.1.1 Pinout diagram

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/a.png" width = "800"/>
</div>

#### 2.1.2 Component overview

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/b.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/c.png" width = "800"/>
</div>

#### 2.1.3 Power pins

- 5V - This is 5v out from the USB port. You can also use this as a voltage input but you must have some sort of diode (schottky, signal, power) between your external power source and this pin with anode to battery, cathode to 5V pin.

- 3V3 - This is the regulated output from the onboard regulator. You can draw 700mA

- GND - Power/data/signal ground

#### 2.1.4 Strapping pins

According to the chip manual of ESP32C3, GPIO2, GPIO8 and GPIO9 in the chip are Strapping Pins, the high and low level configurations of these pins may allow the chip to enter into different Boot modes, please pay attention to this point when you use these pins, otherwise it may prevent your XIAO from uploading or executing the program all the time.

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/d.png" width = "800"/>
</div>

### 2.2 Get started

First, we are going to connect XIAO ESP32C3 to the computer, connect an LED to the board and upload a simple code from Arduino IDE to check whether the board is functioning well by blinking the connected LED.

#### 2.2.1 Hardware setup

!> Some USB cables can only supply power and cannot transfer data. If you don't have a USB cable or don't know if your USB cable can transmit data, you can check Seeed USB Type-C support USB 3.1.

- 1 x Seeed Studio XIAO ESP32C3
- 1 x Computer
- 1 x USB Type-C cable

- Step 1. Connect XIAO ESP32C3 to your computer via a USB Type-C cable.

- Step 2. Connect an LED

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103154806.png" width = "800"/>
</div>

#### 2.2.2 Software setup

- Step 1. Download and Install the latest version of Arduino IDE according to your operating system.

- Step 3. Add ESP32 board package to your Arduino IDE.

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/365b8b57fc07465bbd0ddd498e5b9c7.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/492371a61c6a80ddc32b8972336c9ee.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-01-03%20145105.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/5beafe65a7b576c5b391fb53822ace6.png" width = "800"/>
</div>

- Step 4. Select your board and port

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-01-03%20155032.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-01-03%20155313.png" width = "800"/>
</div>

#### 2.2.3 Blink the LED

The code to light up the LED is as follows:
```C#
// define led according to pin diagram
int led = D10;

void setup() {
  // initialize digital pin led as an output
  pinMode(led, OUTPUT);
}

void loop() {
  digitalWrite(led, HIGH);   // turn the LED on 
  delay(1000);               // wait for a second
  digitalWrite(led, LOW);    // turn the LED off
  delay(1000);               // wait for a second
}
```
Click the Upload button to upload the code to the board

LED has been lit up

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/GIF%202024-1-3%2015-57-46.gif" width = "800"/>
</div>

!> If the following error occurs, you can refer to:[https://blog.csdn.net/weixin_43034503/article/details/128733085](https://blog.csdn.net/weixin_43034503/article/details/128733085#:~:text=%E5%B0%86Arduino,IDE%E6%9B%B4%E6%96%B0%E5%88%B0%E6%9C%80%E6%96%B0%E7%89%88%E6%9C%AC%EF%BC%8C%E7%9B%B4%E6%8E%A5%E5%9C%A8%E2%80%9C%E5%BC%80%E5%8F%91%E6%9D%BF%E7%AE%A1%E7%90%86%E5%99%A8%E2%80%9D%E8%BE%93%E5%85%A5esp32%EF%BC%8C%E7%82%B9%E5%87%BB%E2%80%9C%E5%AE%89%E8%A3%85%E2%80%9D%EF%BC%8C%E5%AE%8C%E6%88%90%E5%90%8E%E5%8D%B3%E5%8F%AF%E4%BD%BF%E7%94%A8%E3%80%82)

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/e3b8273c234bab070babfc81e4bee53.png" width = "800"/>
</div>

## 3 Connect ESP32C3 with Aliyun-IOT

- Log in to the IoT platform console.


- On the Instance Overview page, click on the Public Instance.

- In the left-hand navigation pane, select Device Management > Products, then click on Create Product.

- On the New Product page, after setting the following information, click on Confirm.

- On the Create Product page, click on Go to Add.

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103180652.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103180910.png" width = "800"/>
</div>

- In the Device List tab, click on Add Device
<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103180938.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103181019.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103190436.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103213213.png" width = "800"/>
</div>

- As shown in the figure above, we created a product on the Alibaba Cloud Internet of Things platform, defined the function of an led switch in the product, and then we only need to release it online, and the device can be connected to the Internet of Things platform.

- After successfully creating the device, in the pop-up dialog box for completion, click on Go to View or Copy Device Certificates to obtain the device certificates.

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103181108.png" width = "800"/>
</div>

- Device certificates include ProductKey, DeviceName, and DeviceSecret. These certificates are crucial credentials for subsequent communication between the device and the IoT platform, so ensure they are securely stored.

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103181156.png" width = "800"/>
</div>

## 4 Use Aliyun-IOT to get ESP32C3 information and then control ESP32C3

We use AliyunIoTSDK.h to connect to the Alibaba Cloud IoT platform. AliyunIoTSDK is a library for Arduino, which can be found in the Arduino application store. Here is [the open-source project address](https://github.com/xinyu198736/arduino-aliyun-iot-sdk) based on the AliyunIoTSDK library.

Arduino requires downloading and installing the ArduinoJson, Crypto, PubSubClient, and ESP8266 libraries. These library files can be downloaded directly from the Arduino IDE.

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-01-03%20181455.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-01-03%20181350.png" width = "800"/>
</div>


You can directly download the AliyunIoTSDK to the Arduino project file saving address.

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/4b6ca51e0d9b940cef295563099fa8e.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/5fa31ace1acef98ba89b4b6364b9425.png" width = "800"/>
</div>

- In addition, you need to find the file PubSubClient, open the.h file inside and modify the two macros:
MQTT_MAX_PACKET_SIZE 1024;
MQTT_KEEPALIVE 60;

- Copy the code of the AliyunIoTSDK library open source project at the beginning of the article to make a simple modification, and the project has detailed instructions for use.

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103213429.png" width = "800"/>
</div>

<div align="center">
<img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/20240103213450.png" width = "800"/>
</div>

- Because AliyunIoTSDK is a routine of ESP8266, it needs to use the ESP32 way to connect to WiFi on the WiFi connection, and the other is not much changed.

- The overall code is as follows:

  ```C#
  // 引入 wifi 模块，并实例化，不同的芯片这里的依赖可能不同
#include <WiFi.h>
static WiFiClient espClient;

// 引入阿里云 IoT SDK
#include <AliyunIoTSDK.h>

// 设置产品和设备的信息，从阿里云设备信息里查看
#define PRODUCT_KEY "k0pqkbRe6g4"
#define DEVICE_NAME "esp32"
#define DEVICE_SECRET "533801ccd7e82796581ebe200b1cd679"
#define REGION_ID "cn-shanghai"

const char* ssid     = "态度姐";         // Change this to your WiFi SSID
const char* password = "87654321";    // Change this to your WiFi password

void setup()
{
    Serial.begin(112500);
    
    // 初始化 wifi
    wifiInit("态度姐", "87654321");
    
    // 初始化 iot，需传入 wifi 的 client，和设备产品信息
    AliyunIoTSDK::begin(espClient, PRODUCT_KEY, DEVICE_NAME, DEVICE_SECRET, REGION_ID);
    
    // 绑定一个设备属性回调，当远程修改此属性，会触发 powerCallback
    // PowerSwitch 是在设备产品中定义的物联网模型的 id
    AliyunIoTSDK::bindData("PowerSwitch", powerCallback);
    
    // 发送一个数据到云平台，LightLuminance 是在设备产品中定义的物联网模型的 id
    AliyunIoTSDK::send("LightLuminance", 100);
}

void loop()
{
    AliyunIoTSDK::loop();
}

// 初始化 wifi 连接
void wifiInit(const char *ssid, const char *passphrase)
{
    WiFi.mode(WIFI_STA);
    WiFi.begin(ssid, passphrase);
    while (WiFi.status() != WL_CONNECTED)
    {
        delay(1000);
        Serial.println("WiFi not Connect");
    }
    Serial.println("Connected to AP");
}

// 电源属性修改的回调函数
void powerCallback(JsonVariant p)
{
    int PowerSwitch = p["PowerSwitch"];
    if (PowerSwitch == 1)
    {
        // 启动设备
    } 
}
  ```
