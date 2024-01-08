# Production Process
## 1 Chessboard construction

## 2 Interactive hardware construction

### 2.1 Pressure sensing
In the interaction, it is necessary to use pressure sensors to sense the position of chess pieces on the chessboard, in order to trigger subsequent interactions. 
#### 2.1.1 pressure sensors
We use the pressure sensors as follows:


#### 2.1.2 Example Code
- Using pressure sensors to control lighting as an example.

```C++
# define sensor 2
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

  val = digitalRead(sensor);
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
