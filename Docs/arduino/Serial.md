###Comunicare Arduino <-> Calculator 
Comunicarea se face folosind pinii digitali 0 (RX) si 1 (TX) si la calculator prin portul USB.
Trimiterea de date către calculator sau citirea datelor trimise de calculator se face cu _clasa_ Serial.

Clasa = ce este acesta ? Caută pe net: Object Oriented Programming.

Ca să înțelegi : poți să asimilezi (momentan) clasa ca find o structură un pic mai șmecheră - ex: conține funcții.

``` c++
struct Elev{			//structura mea elev
    char nume[20];

    void Speak(){       // functie !!!
        std::cout << "My name is " << nume << '\n';

    }
};

int main(){
    Elev a,b; 			//2 variabile de tip Elev
    
    strcpy(a.nume, "Ionel");    
    strcpy(b.nume, "Marcela");

    a.Speak();			//apelul funției Speak definită in structura Elev
    b.Speak();
}
```

Rezultatul cred că-l bănuiți:

``` 
My name is Ionel
My name is Marcela
``` 

Funcții definite in clasa `Serial`: (vezi si aici: https://www.arduino.cc/en/Reference/Serial)

`Seria.Begin(speed)` - setează parametrii de configurare ce guverneaza comunicarea Arduino -> Calculator
 - `speed' = viteza de comunicare (in bits per second (baud) - long): 300, 600, 1200, 2400, 4800, 9600, 14400, 19200, 28800, 38400, 57600, or 115200
 - de regulă este apelată în funcția `Setup`

####Comunicarea Arduino -> PC
 `Seria.print(data)` - trimite la calculator `data`  
 `Seria.println(data)` 
 Ex:
``` 
Serial.print(78) gives "78"
Serial.print(1.23456) gives "1.23"
Serial.print('N') gives "N"
Serial.print("Hello world.") gives "Hello world."
``` 

Ex: de program:
``` 
void setup(){
	Serial.begin(9600); 	//config viteza de comm cu PC-ul
}

int i=1;

void loop(){
	Serial.println(i++);      //trimite conținutul variabilei i la calculator
	delay(1000);
}
``` 

Pentru a intercepta pe calculator datele trimise de arduino folosim o aplicatie de tip "serial terminal" - există una inclusă în Arduino IDE - o pornim cu butonul  _Serial terminal_ (lupa din dreapta sus):
![Serial](img/Serial.png)

