#Glosar Arduino

https://www.arduino.cc/en/Reference/HomePage


####`pinMode(NR_PIN, OUTPUT | INPUT);` 


- setare mod de lucru pin `OUTPUT` = ieșire, `INPUT` - intrare
- de regulă se face în funcția setup (o singură dată)
   
####`digitalWrite(NR_PIN, HIGH | LOW);` 
setează 5V (HIGH) pe pinul NR_PIN sau 0V (LOW_ - față de GND (-)

####`analogWrite(NR_PIN, value);`
 - `value` =  intre 0 (always off) și 255 (always on) 
 - **numai** pe pinii: **D3, D5, D6, D9, D10, D12**
 - se poate folosi pentru modificarea intensității luminoase a unui led, să modifici turația motoarelor de curent continuu, etc.

####`delay(MS);`
opreste execuția programului pentru `MS` milisecunde

##`millis()`
Returns the number of milliseconds since the Arduino board began running the current program. This number will overflow (go back to zero), after approximately 50 days.


####`tone`   

`tone(pin, frequency)` 

`tone(pin, frequency, duration)`

`noTone(pin)` - stop sound

- **obligatoriu rezistență în serie cu difuzorul** e ok si cea de 200 ohm.
- nu se poate folosi funcția `tone` concomitent cu `analogWrite` pe pinii 3 sau 11

####`map(value, fromLow, fromHigh, toLow, toHigh)`
"mapeaza" valoarea `value` din intervalul  [`fromLow`, `fromHigh`] în intervalul [`toLow`, `toHigh`]



####Dicționar

GND - ground sau masă = simbol pentru borna - 
