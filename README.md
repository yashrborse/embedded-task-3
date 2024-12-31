# embedded-task-3
#include <LiquidCrystal.h>
int i = 0;
int sensor = A0;
float temp;
float tempc;
float tempf;

/*
Circuit:
 * RS pin connected to digital pin 12
 * pin E (Enable) connected to digital pin 11
 * pin D4 connected to digital pin 5
 * pin D5 connected to digital pin 4
 * pin D6 connected to digital pin 3
 * pin D7 connected to digital pin 2
 * R / W pin connected to the GND
 * pin 1 and pin 4 connected to GND
 * pin 2 connected to + Vcc
 * 10 KOhm potentiometer / trimmer control panel connected to pin 3 of the LCD
 * pin SX potentiometer / trimmer connected to + Vcc
 * DX potentiometer / trimmer pin connected to GND
 * the left and right pins of the potentiometer / trimmer can be interchanged
*/
 
  
/*
   The instance of the LiquidCrystal object called lcd is created in which
   the LCD pins connected to the Arduino digital outputs are indicated
*/
LiquidCrystal lcd (12, 11, 5, 4, 3, 2);
  
void setup () {
   // set the number of columns and the number of lines of lcd
  lcd.begin (16, 2);
  // I see the message on the display
  //lcd.print ("Hackatronic.com ");
}
  
void loop () {
  // place the cursor in column 0 and line 1
  // (note: line 1 and the second line, as it counts starting from 0):
  //for(i=0;i++;15){
  //lcd.setCursor (i, 2);
  //}
  // print the number of seconds since the last reset
  //lcd.print (micros () / 1000);
  //lcd.print("^^^");
  //lcd.print("   ");
  //delay(100);


//delay(2000);
//t=t+2;
temp=analogRead(sensor);
tempc=(temp*5)/10;
tempf=(tempc*1.8)+32;
lcd.setCursor(0,0);
lcd.print("Temp in C = ");
lcd.println(tempc);
lcd.setCursor(0,1);
lcd.print("Temp in F = ");
lcd.println(tempf);
}
