# CODTECH-TASK1
This is my first project on GitHub
#include <LiquidCrystal.h>
LiquidCrystal lcd(22,23, 24, 25, 26, 27);
int tempC = 0;
int light = 0;
int tempPin = 1;
int ldrPin = A0;
int backlight = 44;
int val = 0;
void setup()
{
lcd.begin(16,2);
lcd.setCursor(0,0);
lcd.print("Temperature:");
lcd.setCursor(0,1);
lcd.print("Light Level:");
}
void loop()
{
tempC = analogRead(tempPin);
tempC = (5.0 * tempC * 100.0)/1024.0/10;
lcd.setCursor(12,0);
lcd.print(tempC);
light = analogRead(ldrPin);
lcd.setCursor(12,1);
val = analogRead(ldrPin);
analogWrite(backlight, val/3);
lcd.print(light);
delay(100);
}
