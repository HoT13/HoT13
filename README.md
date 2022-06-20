#include <Servo.h>
Servo myservo;
int Lswitch = 2; 
int servo = 13; 
int flag = 0; 
 
void setup()
{

  Serial.begin(9600); 
  pinMode(Lswitch, INPUT); 
  pinMode(servo, OUTPUT); 
}
 
void loop()
{
  if( (digitalRead(Lswitch) == LOW) && (flag == 0) ) 
  {
    Serial.println("door is closed"); 
flag = 1; 
delay(20); 
  }
  
    if( (digitalRead(Lswitch) == HIGH) && (flag == 1) ) 
  {
    Serial.println("door is opened"); 
flag = 0;
delay(20); 
  }
  
  if ( flag == 1 ) 
  {
    digitalWrite(servo, HIGH); 
    delay(1000); 
    digitalWrite(servo, LOW); 
    delay(1000); 
  }
  
    if ( flag == 1 ) 
  {
digitalWrite(servo, LOW); 
  }
  
  digitalWrite(Lswitch, HIGH); 
 
}
