# HOME-AUTOMATION
int ledPin =11;      
int analogPin = 0;   
int val = 0;
int ledPin1=12;
int sensorState;
float temp,celsius;

void setup() 
{
  pinMode(ledPin, OUTPUT); 
  pinMode(ledPin1,INPUT);
  pinMode(analogPin,INPUT);
   pinMode(A1,INPUT);
pinMode(7,OUTPUT);  
  Serial.begin(9600);
}

void loop()
{
  int b=0,a=0,r=0; 
  sensorState=digitalRead(12);
  Serial.println(sensorState);
   if(sensorState==1)
  {
   temp=analogRead(A0);
   celsius=(((temp/1024)*5)-0.5)*100;
   Serial.println(celsius);
     if(celsius>28&&celsius<=100)
     {
       b=map(celsius,28,100,0,255);
     }
     a=analogRead(A1);
     r=map(a,0,1023,0,255);
     
} 
  analogWrite(11,b);
  Serial.println(b);
  analogWrite(7,a);
  Serial.println(a);
}
 
