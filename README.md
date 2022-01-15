# home automation using arduino
#code for home automation
#include <SoftwareSerial.h> 
String value;
int TxD = 0;
int RxD = 1;
int servoposition;
SoftwareSerial bluetooth(TxD, RxD);
void setup() 
{
 pinMode(10,OUTPUT);
 Serial.begin(9600);      
 bluetooth.begin(9600);
}
void loop()
{
   Serial.println(value);
 if (bluetooth.available())
   {
    value = bluetooth.readString();

    if (value == "on")
    {
    digitalWrite(10, HIGH);
    }
     if (value == "off")
     {
      digitalWrite(10, LOW);
     } 

}
}   
