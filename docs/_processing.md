# Processing
## 1 Introduction
### 1.1 What is Processing
Processing is a flexible software sketchbook and a language for learning how to code. It is an open-source programming language that provides an environment for programming images, animations, and sounds. Processing is used by students, artists, designers, architects, researchers, and hobbyists to learn, prototype, and produce creative works. We can download the Processing Development Environment for free and start writing Processing programs. To learn the Processing language, it is recommended to try a few of the built-in examples, and check out the reference. 
`a pic`
#### 1.2 Download and setup

### 1.2 Similar New Tools
There are also some open-source tools available that are similar to Processing.
#### 1.2.1  P5.js
P5.js is a JavaScript library that is based on Processing and provides a similar environment for programming images, animations, and sounds. It is open-source and free to use, and it is widely used by artists, designers, and developers to create interactive and generative works. P5.js provides a simple and intuitive interface for drawing shapes, colors, and images, and it also provides advanced features for working with data, sound, and video.
`a pic`
#### 1.2.2 OpenFrameworks
OpenFrameworks is an open-source C++ toolkit designed for creative coding. It provides a simple and intuitive framework for experimentation and is designed to work as a general-purpose glue, wrapping together several commonly used libraries, including OpenGL, GLEW, GLUT, libtess2, and cairo for graphics. It is built on top of OpenGL and runs on Microsoft Windows, macOS, Linux, iOS, Android, and Emscripten.
`a pic`
## 2 a Little Demo
It is a little demo in Processing that can use mouse to interactive.
This is a pixel-style cartoon avatar. What we want to achieve is that its eyes will follow the movement of the mouse cursor.
`a pic of the avater`
### 2.1 Code
The code is divided into two steps:
- Step1: draw a pixel-style cartoon avater.
```java
void setup() {
  size(200, 200);
  background(255); // 背景设为白色
}

void draw() {
  // 头部
  fill(255, 204, 0); // 设置填充颜色为黄色
  ellipse(100, 100, 80, 80); // 头部圆形

  // 眼睛
  fill(0); // 设置填充颜色为黑色
  ellipse(85, 90, 10, 20); // 左眼
  ellipse(115, 90, 10, 20); // 右眼

  // 嘴巴
  noFill();
  stroke(255, 102, 102); // 设置轮廓颜色为粉色
  arc(100, 110, 40, 40, 0, PI); // 嘴巴弧形

  // 身体
  fill(255, 204, 0); // 设置填充颜色为黄色
  rect(80, 120, 40, 60); // 矩形身体

  // 腿
  stroke(0); // 设置轮廓颜色为黑色
  line(90, 180, 90, 200); // 左腿
  line(110, 180, 110, 200); // 右腿
}
```
- Step2: add mouse interaction.
```java
void setup() {
  size(200, 200);
  background(255);
}

void draw() {
  // 头部
  fill(255, 204, 0);
  ellipse(100, 100, 80, 80);

  // 眼框
  fill(255);
  ellipse(85, 90, 30, 30);
  ellipse(115, 90, 30, 30);

  // 眼睛
  fill(0);
  float eye1X = map(mouseX, 0, width, 80, 90); // 计算左眼X坐标
  float eye1Y = map(mouseY, 0, height, 85, 95); // 计算左眼Y坐标
  float eye2X = map(mouseX, 0, width, 110, 120); // 计算右眼X坐标
  float eye2Y = map(mouseY, 0, height, 85, 95); // 计算右眼Y坐标
  ellipse(eye1X, eye1Y, 10, 20); // 左眼
  ellipse(eye2X, eye2Y, 10, 20); // 右眼

  // 嘴巴
  noFill();
  stroke(255, 102, 102);
  arc(100, 110, 40, 40, 0, PI);

  // 身体
  fill(255, 204, 0);
  rect(80, 120, 40, 60);

  // 腿
  stroke(0);
  line(90, 180, 90, 200);
  line(110, 180, 110, 200);
}
```
- Step3: Limit the movement of the eye to the eye frame.
```java
void setup() {
  size(200, 200);
  background(255);
}

void draw() {
  // 头部
  fill(255, 204, 0);
  ellipse(100, 100, 80, 80);

  // 眼框
  fill(255);
  ellipse(85, 90, 30, 30);
  ellipse(115, 90, 30, 30);

  // 眼睛
  float eyeSize = 10;
  float eyeDist = 20;
  float eyeX = map(mouseX, 0, width, 80, 90); // 计算左眼X坐标
  float eyeY = map(mouseY, 0, height, 85, 95); // 计算左眼Y坐标
  float eye1X = constrain(eyeX, 85 - eyeDist + eyeSize / 2, 85 + eyeDist - eyeSize / 2); // 左眼X坐标限制在眼框内
  float eye1Y = constrain(eyeY, 75 + eyeSize / 2, 105 - eyeSize / 2); // 左眼Y坐标限制在眼框内

  eyeX = map(mouseX, 0, width, 110, 120); // 计算右眼X坐标
  eyeY = map(mouseY, 0, height, 85, 95); // 计算右眼Y坐标
  float eye2X = constrain(eyeX, 115 - eyeDist + eyeSize / 2, 115 + eyeDist - eyeSize / 2); // 右眼X坐标限制在眼框内
  float eye2Y = constrain(eyeY, 75 + eyeSize / 2, 105 - eyeSize / 2); // 右眼Y坐标限制在眼框内
  
  fill(0);
  ellipse(eye1X, eye1Y, eyeSize, eyeSize); // 左眼
  ellipse(eye2X, eye2Y, eyeSize, eyeSize); // 右眼

  // 嘴巴
  noFill();
  stroke(255, 102, 102);
  arc(100, 110, 40, 40, 0, PI);

  // 身体
  fill(255, 204, 0);
  rect(80, 120, 40, 60);

  // 腿
  stroke(0);
  line(90, 180, 90, 200);
  line(110, 180, 110, 200);
}
```
### 2.2 Demo
`a gif`
## 3 Processing with Arduino
