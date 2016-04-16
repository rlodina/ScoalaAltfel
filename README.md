##Un altfel de "Școala altfel".

[![Join the chat at https://gitter.im/rlodina/ScoalaAltfel](https://badges.gitter.im/rlodina/ScoalaAltfel.svg)](https://gitter.im/rlodina/ScoalaAltfel?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Ești ceea ce **alegi** să fii.



###Prima întâlnire:

1. [Instalare Eduino IDE](https://github.com/rlodina/ScoalaAltfel/blob/master/Docs/arduino/Arduino-IDE.md)
2. [Ce este un microcontroler ?](https://github.com/rlodina/ScoalaAltfel/blob/master/Docs/arduino/Microcontroller.md)
3. [Arduino - facem primul montaj + scriem codul](https://github.com/rlodina/ScoalaAltfel/blob/master/Docs/arduino/Joi-14.04.md)

Temă (pentru următoarea întâlnire):
  - crează un montaj cu 9 leduri care se aprind într-o succesiune interesantă
  - postează codul în repo-ul tău (Ex: ScoalaAltfel\LedArray) pe github (fă-i și un README.md)
  - pune un film pe youtube sa vedem și noi cum merge
 
Rezumat:
 
``` C++
   //in funcția setup 
   pinMode(3, OUTPUT);      //seteaz pinul 3 ca pin de iesire 
   
   //manipulare cu:
   digitalWrite(3, HIGH);   //aprinde led-ul   
   digitalWrite(3, LOW);    //stinge led-ul
   
```

Remarcați că putem folosi funcția `digitalWrite` - doar pentru HIGH sau LOW (1 sau 0, pornit sau oprit). Ex: Deschide_robinetul sau Inchide_robinetul


 

