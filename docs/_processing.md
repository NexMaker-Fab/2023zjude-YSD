# Processing

## 1 Introduction

### 1.1 What is Processing
Processing is a flexible software sketchbook and a language for learning how to code. It is an open-source programming language that provides an environment for programming images, animations, and sounds. Processing is used by students, artists, designers, architects, researchers, and hobbyists to learn, prototype, and produce creative works. We can [download](https://processing.org/download) the Processing Development Environment for free and start writing Processing programs. To learn the Processing language, it is recommended to try a few of the built-in examples, and check out the reference. 

### 1.2 Similar New Tools
There are also some open-source tools available that are similar to Processing.

#### 1.2.1  P5.js
P5.js is a JavaScript library that is based on Processing and provides a similar environment for programming images, animations, and sounds. It is open-source and free to use, and it is widely used by artists, designers, and developers to create interactive and generative works. P5.js provides a simple and intuitive interface for drawing shapes, colors, and images, and it also provides advanced features for working with data, sound, and video.

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/P5js.jpg" width = "400"/>
</div>

#### 1.2.2 OpenFrameworks
OpenFrameworks is an open-source C++ toolkit designed for creative coding. It provides a simple and intuitive framework for experimentation and is designed to work as a general-purpose glue, wrapping together several commonly used libraries, including OpenGL, GLEW, GLUT, libtess2, and cairo for graphics. It is built on top of OpenGL and runs on Microsoft Windows, macOS, Linux, iOS, Android, and Emscripten.

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/openframe.png" width = "400"/>
</div>

---

## 2 a Little Demo
It is a little demo in Processing that can use mouse to interactive.
This is a pixel-style cartoon avatar. What we want to achieve is that its eyes will follow the movement of the mouse cursor.

### 2.1 Code
The code is divided into two steps:
- **Step1**: draw a pixel-style cartoon avater.

```java
void setup() {
  size(200, 200); // 设置画布大小
}

void draw() {
  background(255); // 设置背景颜色为白色
  
  // 绘制头部
  fill(255, 200, 0); // 设置填充颜色为黄色
  ellipse(100, 100, 80, 80); // 绘制头部
  
  // 绘制眼睛
  fill(0); // 设置填充颜色为黑色
  ellipse(85, 90, 10, 10); // 绘制左眼
  ellipse(115, 90, 10, 10); // 绘制右眼
  
  // 绘制嘴巴
  stroke(255, 0, 0); // 设置描边颜色为红色
  line(90, 110, 110, 110); // 绘制嘴巴
}

```
- **Step2**: add mouse interaction.

```java
void setup() {
  size(200, 200); // 设置画布大小
}

void draw() {
  background(255); // 设置背景颜色为白色
  
  // 计算眼睛位置
  float eyeX1 = 85 + (mouseX - width / 2) * 0.05;
  float eyeY = 90 + (mouseY - height / 2) * 0.05;
  float eyeX2 = 115 + (mouseX - width / 2) * 0.05;

  // 绘制头部
  fill(255, 200, 0); // 设置填充颜色为黄色
  ellipse(100, 100, 80, 80); // 绘制头部
  
  // 绘制眼睛
  fill(0); // 设置填充颜色为黑色
  ellipse(eyeX1, eyeY, 10, 10); // 绘制左眼
  ellipse(eyeX2, eyeY, 10, 10); // 绘制右眼
  
  // 绘制嘴巴
  stroke(255, 0, 0); // 设置描边颜色为红色
  line(90, 110, 110, 110); // 绘制嘴巴
}

```

### 2.2 Demo

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/GIF%202024-1-2%2017-36-13.gif" width = "400"/>
</div>

---

## 3 Processing with Arduino
In this experiment, we want to display the pressure magnitude on the pressure sensor using the degree of curvature of the lines.

### 3.1 List of components
- Arduino UNO * 1
- Pressure sensor * 1
- voltage converter * 1
- Some Dupont threads

### 3.2 Schematic circuit diagram
- Connect the relevant components.

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/624a4935b935a7ed8e146b422971507.jpg" width = "800"/>
</div>

- Write code both in the Arduino IDE and Processing.

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/1704207913399.png" width = "800"/>
</div>

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/1704207967326.png" width = "800"/>
</div>

- Run the code.

!> When run the code in Processing, the serial monitor in Arduino must be turned off.

- Debug and test.

### 3.3 Code
- Code for Arduino

```java
int val=0;
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
  val = analogRead(A0);
  Serial.println(val/4);
  delay(100);
}
```

- Code for Processing

```java
import processing.serial.*;
Serial port;
float val;
void setup (){
  size(600,600);
  frameRate(30);
  String myPort = Serial.list()[0];
  port = new Serial(this, myPort, 9600);
  background(255);
}

void draw() {
  background(0);
  
  if(port.available ()>0) {
    val = port.read();
    strokeWeight(5);
    noFill();
    stroke(255);
    val = int(map(val,255, 0, 400, 0));
    println(val);
    
  }
  ellipse(300,300,400,val);
}
```

### 3.4 Demo

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/GIF%202024-1-2%2022-59-34.gif" width = "800"/>
</div>

## Reference
- [Processing 官方网站](https://processing.org/)
- [P5.js 官方网站](https://p5js.org/)
- [OpenFrameworks 官方网站](https://openframeworks.cc/)
