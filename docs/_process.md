# Production Process
## 1 Chessboard construction
Our device is mainly divided into two parts: a horizontal chessboard and a vertical background.
### 1.1 horizontal chessboard

### 1.2 vertical background
- The artistic style reference for the background section is as follows：

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

### 2.3 Lighting Effects

## 3 Video demonstration
