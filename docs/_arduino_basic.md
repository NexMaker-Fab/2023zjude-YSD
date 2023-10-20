# Arduino Basic

## 1 Water Light Program

### 1.1 List of components
- Arduino UNO * 1
- Breadboard * 1
- LED * 6
- 1kΩ resistance * 6
- Some Dupont threads 

### 1.2 Schematic circuit diagram
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

- Debug code, run and test.
<br>

### 1.3 Code
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
