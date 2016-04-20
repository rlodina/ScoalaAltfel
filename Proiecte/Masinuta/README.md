#Construim și programăm mașinuța

![masinuta](img/img_12_small.jpg)

Detalii legate de ansablare [aici](Ansamblare.md)

#Componente noi

##Măsurarea distanței până la un obstacol - HC-SR04

![HR-SR04_POZA](img/HC-SR04.jpg)
Principiu de funcționare:

![HR-SR04](img/Ultrasonic-Sensor-Equasions.png)

http://howtomechatronics.com/tutorials/arduino/ultrasonic-sensor-hc-sr04/

Cod simplu de test:
Pentru a rula acest cod:
 - alimentati senzorul HC-SR04 (+ si -)
 - conectati pinul trig (trigger) as senzorului la pin 7 al MC-ului
 - conectati pinul echo as senzorului la pin 8 al MC-ului

``` c++
//am luat 2 pini digitali la întâmplare
const int trigger_Pin = 7;  
const int echo_Pin = 8;
 
void setup(){

    pinMode(trigger_Pin, OUTPUT);
    pinMode(echo_Pin, INPUT);           //Atenție INPIUT pin
  
    Serial.begin(9600);                 //cfg. comunicare cu calculatorul
  
}
 
void loop(){
    digitalWrite(trigger_Pin, LOW);
    digitalWrite(trigger_Pin, HIGH);    //emitem un semnal ultrasonic
    delayMicroseconds(10);              //un delay mai minuțios    
    digitalWrite(trigger_Pin, LOW);     //stop emitere semnal
    
    long durata = pulseIn(echo_Pin, HIGH);    //măsuram durata (în microsec) 

    long dist = 0.017 * durata;          //calc. distanta 
    
    Serial.print("distanta: ");         //trimitem val. distantei la calculator
    Serial.print(dist);
    Serial.println(" cm");
    
    delay(100);
}
```

 - poți săi verifici precizia cu un liniar si un obstacol 
 - emite un sunet cu frecvența de 40000 Hz - ultrasunet (noi nu-l putem auzi)
 - teoretic poate măsura distante cuprinse între 2 cm și 4 m (cu precizie de câțiva mm)

