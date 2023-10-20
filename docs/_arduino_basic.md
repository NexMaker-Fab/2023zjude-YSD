# Arduino Basic

## 1 Water Light Program

### 1.1 List of components
- LED

### 1.2 Schematic circuit diagram

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
