# Production Process

<style>
  .image-container {
    display: flex; /* 使用 Flex 布局 */
  }
  .image-container img {
    width: 50%; /* 设置图片宽度为容器的一半 */
    height: auto; /* 让高度自适应保持比例 */
  }
</style>

## 1 Chessboard construction
Our device is mainly divided into two parts: a horizontal chessboard and a vertical background.
### 1.1 horizontal chessboard
- The chessboard is made according to the tourist map of Dongqian Lake Scenic Area, using a realistic style, with a focus on five locations including Ningbo Safari Park, Taogong Island, Xiashui Wetland Park, Hanling Old Street , and Xiayu Cicada Temple.

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/c004226ed391483bae3b52fe38f651f.png" width = "500"/>
</div>

#### 1.1.1 Process

- Carve the shape of Dongqian Lake on the foam board

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/curve.png" width = "500"/>
</div>

- Pave the lawn and slate road, and use water feature cream to create a lake effect

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/makewater.gif" width = "500"/>
</div>

- Add some details

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/stone.jpg" width = "500"/>
</div>

#### 1.1.2 Detail display

<div class="image-container">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/IMG_20240109_002744.jpg" alt="Image 1">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/IMG_20240109_002728.jpg" alt="Image 2">
</div>

### 1.2 vertical background

- The artistic style reference for the background section is as follows：

<div class="image-container">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/bg01.png" alt="Image 1">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/bg02.png" alt="Image 2">
</div>

- Using various materials, construct scattered elements such as servos and LEDs on the grass to simulate dynamic elements in different locations.
- Use disposable chopsticks and cardboard to create various plants such as trees and shrubs as backgrounds, and use plastic clay to pinch egrets, monkeys, and lions and color them as interactive objects.
- Create a bouquet using cardboard as an interactive object.
- The symbolic memorial archway of "Hanling Old Street" was made with cardboard and wooden chopsticks, and LED lights were pasted on the back as interactive objects.
- Cut out the Guanyin statue printed on copperplate paper and use the "arm" as the interactive object to stick it onto the fan blades of the servo, allowing it to sway left and right.

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/bg.jpg" width = "500"/>
</div>

## 2 Interactive hardware construction

### 2.1 Pressure sensing
In the interaction, it is necessary to use pressure sensors to sense the position of chess pieces on the chessboard, in order to trigger subsequent interactions. 
#### 2.1.1 pressure sensors
We use the pressure sensors as follows. This pressure sensor converts the pressure applied to the thin film area of the FSR sensor into a change in resistance value, thereby obtaining pressure information. The greater the pressure, the lower the resistance.

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/pressure-sensor.png" width = "500"/>
</div>

There are two ways for pressure sensors to read, namely **digital input** and **analog input**. 
- use `digitalRead()` to make digital input, with only two states:  `0` and `1`. `0` indicates pressure sensing, and `1` indicates no pressure. At this point, the pressure sensor should be connected to the **digital pin**.
- use `analogRead()` to make analog input, with a series of numbers from `0` to `1023` to display pressure magnitude. the The greater the pressure, the smaller the reading. At this point, the pressure sensor should be connected to the **analog pin**.

#### 2.1.2 Example Code
- Using pressure sensors to control lighting as an example.

```C++
# define sensor 2 //压力传感器连接数字引脚
# define LED 3
int val == 1; //记录压力传感器状态

void setup(){
  // put your setup code here, to run once:

  Serial.begin(9600);

  pinMOde(sensor, INPUT);
  pinMode(LED, OUTPUT);
}

void loop(){
  // put your main code here, to run repeatedly:

  val = digitalRead(sensor); //读取压力传感器数值
  Serial.println(val);

  if(val == 0){
    digitalWrite(LED, HIGH);
    delay(1000);
  }
  else{
    digitalWrite(LED, LOW);
    delay(1000);
  }
}
```

### 2.2 Movement Effects


#### 2.2.1 horizontal movement
- 

- **Example Code**

!> The initial position and rotation angle of the servo need to be continuously adjusted during actual us!

!> Pay attention to using a 180 degree servo motor.

```C++
# define sensor 2 //压力传感器连接数字引脚
const int my_servo = 9;
int val == 1; //记录压力传感器状态
Servo.myservo;

void setup(){
  // put your setup code here, to run once:

  Serial.begin(9600);

  pinMOde(sensor, INPUT);
  myservo.attach(my_servo);
  myservo.write(0); //舵机位置初始化
  delay(10);
}

void loop(){
  // put your main code here, to run repeatedly:

  val = digitalRead(sensor); //读取压力传感器数值
  Serial.println(val);

  if(val == 0){
    myservo.write(180);
    delay(1000);
  }
  else{
    myservo.write(0);
    delay(1000);
  }
}
```

#### 2.2.2 swing

### 2.3 Lighting Effects

### 2.4 Complete Code



## 3 Video demonstration
