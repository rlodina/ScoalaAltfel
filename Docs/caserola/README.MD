# Conținutul caserolei

## Breadboard
![beadboard](img/breadboard_layout.png)

În imaginea de mai sus este ilustrată legătura dintre perforațiile (găurile) breadboardului.
## Resistori

![Rezistoes](img/Rezistors.png)

Valoarea este marcata (codificat) cu acele cercuri colorate după următoarea convenție:
![Rezistors](img/ResistorColorCode.jpg) (tidyforms.com)


#### Divizorul de tensiune
Dacă unei grupări de rezistori înseriate i se aplica tensiunea Vin, de pe una din rezistentele grupării se poate culege o fracțiune din tensiunea aplicată, obținandu-se un divizor de tensiune (divizorul de tensiune rezistiv).

![Divizor_tens](img/DivizorulDeTensiune.png)

Tutorial: https://www.youtube.com/watch?v=XxLKfAZrhbM

## Led - Light Emitting Diode
  
![Led](img/led.jpg)


**ATENȚIE: nu se poate conecta direct la 5V.**

În catalogul producătorului sunt date caracteristicile de utilizare (pt. led-urile noastre portocalii):
 - tensiunea de alimentare este 2.4 V
 - curentul de funcționare: ~18 mA 

Vom monta un rezistor în serie cu led-ul care are rolul de a limita curentul prin led.

Căderea de tensiune (dorită) pe rezistor => 5V - 2.4V  = 2.6V

Știind curentul care străbate circuitul (18mA) aplicând legea lui Ohm R = U/I => R = 2.6V/0.018A =  144 Ohm

![Led](img/Ohm.png)

Noi vom pune o rezistență de 200 Ohm (că de astea avem).

Dacă modificăm tensiunea de alimentare a unui LED se modifică și intensitatea lui luminoasă (Atenție să nu depășim valoarea maximă acceptată).

Putem folosi:
- `digitalWrite` - ON sau OFF led
- `analogWrite`  - cu modificare tensiune de alimentare led ( 0 (off) .... 255(maxim))


## RGB - Led 
**R**ed**G**reen**B**lue - trei led-uri într-o singură componentă 

![RGB Led](img/RGB-led.png)

Ledul RGB folosit de noi este produs de LUCKY LIGHT (cod: LL-509RGBM2E-002).[Link datasheet](http://www.tme.eu/ro/Document/28b9468ad2f4590fbef186695f40eaef/LL-509RGBM2E-002.pdf) (pagina care descrie caracteristicele unei componente).

Prin combinarea celor 3 culori,în proporții diferite, (alimentăm ledurile diferit folosind `analogWrite`) obținem o gamă largă de culori (vezi: https://www.google.com/#q=RGB+color+table)

![color_composition](img/RGB-animation.gif)

http://www.mbeckler.org/microcontrollers/rgb_led/
![RGB Circuit](img/RGB-circuit.png)

``` c++
#define PIN_RED 6
#define PIN_GREEN 5
#define PIN_BLUE 3

#define NUM_COLORS 13
byte colors[NUM_COLORS][3] = {
    {0,255,0}, {0,0,255}, {255,255,0}, {0,255,255}, {255,0,255}, {192,192,192}, {128,128,128}, 
    {128,0,0}, {128,128,0}, {0,128,0}, {128,0,128}, {0,128,128}, {0,0,128}
};

void setup(){
    pinMode(PIN_RED, OUTPUT);
    pinMode(PIN_GREEN, OUTPUT);
    pinMode(PIN_BLUE, OUTPUT);
}

void loop(){
    for(byte i = 0; i< NUM_COLORS; i++){
        analogWrite(PIN_RED, colors[i][0]);
        analogWrite(PIN_GREEN, colors[i][1]);
        analogWrite(PIN_BLUE, colors[i][2]);    
        delay(400);
    }
}
```

## Difuzor - speaker
![speaker](img/Speaker.png)

- **obligatoriu rezistență în serie cu difuzorul** e ok si cea de 200 ohm.

Funcții:
- `tone(pin, frequency)` 
- `tone(pin, frequency, duration)`
- `noTone(pin)` - stop sound

Generează un o sunet în difuzorul conectat la pinu-ul PIN cu frecvența `frecvency` exprimată în Hz (interval [31.. 65535] Hz) și cu durata `duration` milisecunde.
 
Obs: nu se poate folosi funcția `tone` concomitent cu `analogWrite` pe pinii 3 sau 11

Librărie alternativa: [NewTone](https://bitbucket.org/teckel12/arduino-new-tone/wiki/Home)
Detalii instalare librării în mediul Arduino IDE: https://www.arduino.cc/en/Guide/Libraries 



