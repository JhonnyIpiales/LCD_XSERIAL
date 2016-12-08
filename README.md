# LCD_XSERIAL
DEBER
#include <LiquidCrystal.h>

LiquidCrystal lcd(12,11,5,4,3,2);
String palabras_e;
int num_e;
int cont;



void setup() {
  Serial.begin(9600);
  Serial.begin(16,2);
  lcd.clear();

}

void loop() {
  if (Serial.available()>0)  {
  palabras_e = Serial.readString();
 num_e = palabras_e.length();
  for(cont=16;cont>=1; cont--){
  lcd.clear();
  lcd.setCursor(cont, 0);
  lcd.print(palabras_e);
  delay(300);
      }   
 for(cont=0;cont<=num_e; cont++){
 lcd.setCursor(0,0);
 lcd.print(palabras_e.substring(cont-1));
 delay(300);
 lcd.clear();

}


}}
