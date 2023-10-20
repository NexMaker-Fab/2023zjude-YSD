# Arduino Basic

## 1 An open source project
### 1.1 Program brief

   In view of the problems that people often cannot water potted plants at home or office in time due to their busy lives and unreasonable watering methods, this paper designs an intelligent watering device for indoor potted plants based on Arduino, and uses soil temperature and humidity sensors to monitor soil temperature and humidity in real time.
### 1.2 Project diaplay
   - Picture presentation

      ![](https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-10-20%20171955.png)
   - Video presentation

       https://www.youtube.com/watch?v=T_tpKoNCVYw
### 1.3 Code
   
   The code can be downloaded from here: https://github.com/DIY-Machines/SmartPlantV1

### 1.4 Keypoint
   - A great idea which combines 3D printing and arduino 
   - A combination of sensors
   - Develop a low-cost smart flower pot

***

## 2 Water Light Program

### 2.1 List of components
- Arduino UNO * 1
- Breadboard * 1
- LED * 6
- 1kΩ resistance * 6
- Some Dupont threads 

### 2.2 Schematic circuit diagram
- Connect the relevant components according to the wiring diagram.
<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E6%B5%81%E6%B0%B4%E7%81%AF.png" width=400/>
</div>
<br>

- Write code in the Arduino IDE.
<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/arduino%E6%88%AA%E5%9B%BE.png" width=400/>
</div>
<br>

- Upload the code.
<br>

- Debug, run and test.
<br>

### 2.3 Code
```C++
// water light program
const int numled=6;
const int ledpins[]={2,3,4,5,6,7};
const int wait=200;

void setup()
{ 
  for(int i=0;i<numled;i++)
  pinMode(ledpins[i], OUTPUT);
}

void loop()
{
  for(int i=0;i<numled;i++)
  {
  digitalWrite(ledpins[i], LOW);
  delay(wait); 
  digitalWrite(ledpins[i+1], LOW);
  delay(wait); 
  digitalWrite(ledpins[i], HIGH); 
  delay(wait*2);
  }
  
  for(int i=numled-1;i>0;i--)
  {
  digitalWrite(ledpins[i], LOW);
  delay(wait); 
  digitalWrite(ledpins[i-1], LOW);
  delay(wait); 
  digitalWrite(ledpins[i], HIGH); 
  delay(wait*2);
  }
}
```
***

## Reference
- 《Arduino权威指南》, Micbael Margolis, 杨昆云（译）
