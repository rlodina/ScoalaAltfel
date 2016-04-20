#Construim și programăm mașinuța

![masinuta](img/img_12_small.jpg)

Detalii legate de ansablare [aici](Ansamblare.md)

#Componente noi

##HC-SR04 - măsurarea distanței până la un obstacol

![HR-SR04_POZA](img/HC-SR04.jpg)

Principiu de funcționare:

![HR-SR04](img/Ultrasonic-Sensor-Equasions.png)

1. Ping:  emite un sunet cu frecvența de 40000 Hz - ultrasunet (noi nu-l putem auzi) - este un difuzor.

2. Echo: măsurăm timpul necesar intoarcerii undelor sonore reflectate (echo) - cu un fel de microfon
 
http://howtomechatronics.com/tutorials/arduino/ultrasonic-sensor-hc-sr04/

Cod simplu de test:
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
    digitalWrite(trigger_Pin, HIGH);    //emitem un ultrasunet
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
 - teoretic poate măsura distante cuprinse între 2 cm și 4 m (cu precizie de câțiva mm)

##H-Bridge - driver motoare

Sensul de rotatie al unui motor de curent continuu se poate schimba inversând firele de alimentare (+ cu -)

Deoarece motorașele folosite de noi consuma ~200 mA nu le putem alimenta direct din microcontroler (Arduino) - mai țineți minte un pin poate oferi maxim 40 mA. De accea folosim o placă adaptoare - driver:

 ![H-Bridge](img/H-Bridge.jpg)

Pinii:

- **IN1** și **IN2** controlează funcnționarea motorului **A** 
    - IN1 = LOW și IN2 = LOW => STOP motor **A**
    - IN1 = HIGH și IN2 = LOW => motor **A** se rotește în sensul acelor de ceasornic
    - IN1 = LOW și IN2 = HIGH => motor **A** se rotește în sensul **invers** al acelor de ceasornic
    
- **IN3** și **IN4** controlează funcnționarea motorului **B**
    - IN3 = LOW și IN4 = LOW => STOP motor **B**
    - IN3 = HIGH și IN4 = LOW => motor **B** se rotește în sensul acelor de ceasornic
    - IN3 = LOW și IN4 = HIGH => motor **B** se rotește în sensul **invers** al acelor de ceasornic


