##Un altfel de "Școala altfel".

[![Join the chat at https://gitter.im/rlodina/ScoalaAltfel](https://badges.gitter.im/rlodina/ScoalaAltfel.svg)](https://gitter.im/rlodina/ScoalaAltfel?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Ești ceea ce **alegi** să fii.



###Prima întâlnire:

1. [Instalare Eduino IDE](https://github.com/rlodina/ScoalaAltfel/blob/master/Docs/arduino/Arduino-IDE.md)
2. [Ce este un microcontroler ?](https://github.com/rlodina/ScoalaAltfel/blob/master/Docs/arduino/Microcontroller.md)
3. [Arduino - facem primul montaj + scriem codul](https://github.com/rlodina/ScoalaAltfel/blob/master/Docs/arduino/Primul-pas.md)

######Temă (pentru următoarea întâlnire):
  - crează un montaj cu 9 leduri care se aprind într-o succesiune interesantă
  - postează codul în repo-ul tău (Ex: ScoalaAltfel\LedArray) pe github (fă-i și un README.md)
  - pune un film pe youtube să vedem și noi cum merge
  - dă-ne un semn [Facebook](https://www.facebook.com/groups/ScoalaAltfel) - suntem extrem de curioși și nerăbdători.

Rezumat:
``` C++
   //in funcția setup 
   pinMode(3, OUTPUT);      //seteaz pinul 3 ca pin de iesire 
   
   //manipulare cu:
   digitalWrite(3, HIGH);   //aprinde led-ul   
   digitalWrite(3, LOW);    //stinge led-ul
   
```

Remarcați că putem folosi funcția `digitalWrite` - doar pentru HIGH sau LOW (1 sau 0, pornit sau oprit). Ex: Deschide_robinetul sau Inchide_robinetul

###O pată de culoare

Este momentul să experimentezi. Lasă-te dus de val, alimentează-ți curiozitatea, încercă un cod de pe net (este plin de experimente cu Arduino).

######Output cu tensiune variabilă 0 ... 5V 
Vezi [secțiunea RGB Led](https://github.com/rlodina/ScoalaAltfel/tree/master/Docs/caserola#rgb---led).
 
`analogWrite(PIN, value);`
 - `value` =  intre 0 (always off) și 255 (always on) 
 - PIN => **numai** pe pinii: **D3, D5, D6, D9, D10, D12**
 - se poate folosi pentru modificarea intensității luminoase a unui led, să modifici turația motoarelor de curent continuu, etc.
 

######Scoatem și sunete
 Vezi [secțiunea speaker](https://github.com/rlodina/ScoalaAltfel/tree/master/Docs/caserola#difuzor---speaker)

`tone(PIN, frequency, duration)` - generează un o sunet în difuzorul conectat la pin-ul PIN cu frecvența `frecvency` exprimată în Hz (interval [31.. 65535] Hz) și cu durata `duration` milisecunde.


######News:
Am adăugat 2 noi documente (_în lucru_) : 
- [Conținutul caserolei](https://github.com/rlodina/ScoalaAltfel/tree/master/Docs/caserola) - cu descrierea și explicații legate de componentele din caserolă
- [Glosar Arduino](https://github.com/rlodina/ScoalaAltfel/blob/master/Docs/Glosar.md) - un sumar al funcțiilor folosite. Rămâne referință: https://www.arduino.cc/en/Reference/HomePage


######Temă (pentru următoarea întâlnire):
  - încerca să reproduci (cu câteva leduri și cu difuzorul) efectele vizuale și sunetul unei mașini de poliție / salvare / pompieri.
  - postează codul în repo-ul tău (Ex: ScoalaAltfel\Sirena) pe github (fă-i și un README.md)
  - pune un film pe youtube să vedem și noi cum merge
  - dă-ne un semn [Facebook](https://www.facebook.com/groups/ScoalaAltfel) - suntem extrem de curioși și nerăbdători.

###Comunic deci exist 
Comunicarea intre calculator si arduino: [Serial](Docs/arduino/Serial.md)

###E pur si muove
[Ansamblăm și programăm mașinuța](Proiecte/Masinuta/README.md)

![masinuta](Proiecte/Masinuta/img/img_12_small.jpg)

Punem la treabă bagajul de cunoștințe acumulat până acum.


