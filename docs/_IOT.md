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
<img src="" width = "800"/>
</div>

#### 2.1.2 Component overview

<div align="center">
<img src="" width = "800"/>
</div>

<div align="center">
<img src="" width = "800"/>
</div>

#### 2.1.3 Power pins

- 5V - This is 5v out from the USB port. You can also use this as a voltage input but you must have some sort of diode (schottky, signal, power) between your external power source and this pin with anode to battery, cathode to 5V pin.

- 3V3 - This is the regulated output from the onboard regulator. You can draw 700mA

- GND - Power/data/signal ground

#### 2.1.4 Strapping pins

According to the chip manual of ESP32C3, GPIO2, GPIO8 and GPIO9 in the chip are Strapping Pins, the high and low level configurations of these pins may allow the chip to enter into different Boot modes, please pay attention to this point when you use these pins, otherwise it may prevent your XIAO from uploading or executing the program all the time.

<div align="center">
<img src="" width = "800"/>
</div>

### 2.2 Get started

First, we are going to connect XIAO ESP32C3 to the computer, connect an LED to the board and upload a simple code from Arduino IDE to check whether the board is functioning well by blinking the connected LED.

#### 2.2.1 Hardware setup

> ! Some USB cables can only supply power and cannot transfer data. If you don't have a USB cable or don't know if your USB cable can transmit data, you can check Seeed USB Type-C support USB 3.1.

- 1 x Seeed Studio XIAO ESP32C3
- 1 x Computer
- 1 x USB Type-C cable

- Step 1. Connect XIAO ESP32C3 to your computer via a USB Type-C cable.

<div align="center">
<img src="" width = "800"/>
</div>

- Step 2. Connect an LED

<div align="center">
<img src="" width = "800"/>
</div>

#### 2.2.2 Software setup

#### 2.2.3 Blink the LED


