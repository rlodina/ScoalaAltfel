#Sumar funcții & diverse

https://www.arduino.cc/en/Reference/HomePage

##`pinMode(NR_PIN, OUTPUT | INPUT);` 

- setare mod de lucru pin `OUTPUT` = ieșire, `INPUT` - intrare
- de regulă se face în funcția setup (o singură dată)
   
##`digitalWrite(NR_PIN, HIGH | LOW);` 
setează 5V (HIGH) pe pinul NR_PIN sau 0V (LOW_ - față de GND (-)

##`analogWrite(NR_PIN, value);`
 - **numai** pe pinii: **D3, D5, D6, D9, D10, D12**
 - se poate folosi ca să modifici intensitatea luminoasă a unui led, să modifici turația motoarelor de curent continuu, etc.




##Dicționar

GND - ground sau masă = simbol pentru borna - 
