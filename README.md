# RGB_LED_programming_On_Arduino
This code was used to program the LEDs on the world Map in the living room.

This link was used for the code.
https://learn.adafruit.com/rgb-led-strips/arduino-code


```
#define REDPIN 4
#define GREENPIN 5
#define BLUEPIN 6
 
#define FADESPEED 100     // make this higher to slow down
 
void setup() {
  pinMode(REDPIN, OUTPUT);
  pinMode(GREENPIN, OUTPUT);
  pinMode(BLUEPIN, OUTPUT);
//  analogWrite(REDPIN, 255);

  Serial.begin(9600);
}
 
 
void loop() {
  int r, g, b;
    Serial.println("red on");
    analogWrite(REDPIN, 255);
    delay(5000);  
    
  
    Serial.println("green on");
    analogWrite(GREENPIN, 255);
    delay(1000);  
    
 
  // fade from blue to violet
  for (r = 0; r < 256; r++) { 
    analogWrite(REDPIN, r);
    delay(FADESPEED);
  }
    
  // fade from violet to red
  for (b = 255; b > 0; b--) { 
    analogWrite(BLUEPIN, b);
    delay(FADESPEED);
  } 
      Serial.println("red on");
    analogWrite(REDPIN, 255);
    delay(2000);  
  
  // fade from red to yellow
  for (g = 0; g < 256; g++) { 
    analogWrite(GREENPIN, g);
    delay(FADESPEED);
  } 
  // fade from yellow to green
  for (r = 255; r > 0; r--) { 
    analogWrite(REDPIN, r);
    delay(FADESPEED);
  } 
  // fade from green to teal
  for (b = 0; b < 256; b++) { 
    analogWrite(BLUEPIN, b);
    delay(FADESPEED);
  } 
  // fade from teal to blue
  for (g = 255; g > 0; g--) { 
    analogWrite(GREENPIN, g);
    delay(FADESPEED);
  }
   
}

```
