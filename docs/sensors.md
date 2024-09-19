# sensors.py
Soubor který slouží pro ovládání a získávání informací ze senzorů. Zatím jsou podporavné pouze barevné senzory a baterie.

## Seznam funkcí
### DefineOne()
`DefineOne(port:str)`<br>
Funkce pro získávání a sjednoscení portů. Funkce na základě proměné port vybare a vrátí port.

**Parametry**<br>
- port - Jaky port se ma vybrat<br>

**Return**<br>
Funkce zpět vrací zppět správný port.<br>

<br>
<br>

### GetColor
`GetColor(port:str, surface:bool)`<br>
Funkce pro získávání barvy z barevných senzorů.

**Parametry**<br>
- port - Z jakého senzoru se má číst barva<br>
- surface - Na jakém povrchu se čte barva (jesti na povrchu jako displej nebo jako papír, deafult:True - jako papír)<br>

**Return**<br>
Funkce vrací získanou barvu.<br>

<br>
<br>

### GetAmbient()
`GetAmbient(port:str)`<br>
Funkce pro získávání okolního světla<br>

**Parametry**<br>
- port - Jaky port se má použít<br>

**Return**<br>
Funkce vvrací naměřenou hodnotu<br>

<br>
<br>

### GetReflection()
`GetRefelction(port:str)`<br>
Funkce pro získání odraženého světla<br>

**Parametry**<br>
- port - Jaký port se má použít <br>

**Return**
Funkce vrací  naměřené hodnoty.<br>

<br>
<br>

### ColorLightOn
`ColorLightOn(port:str, brightness:tuple)`<br>
Funkce pro rozsvícení světel na barevném senzoru<br>

**Parametry**<br>
- port - Jaky senzor se má rozsvítit<br>
- brightness - Jak moc se má jaké světlo v senzoru rozsvítit (deafult:[100, 100, 100])<br>

<br>
<br>

### CheckBaterryPercentage()
`CheckBaterryPercentage()`<br>
Funkce pro kontrolu a zěmření nabití baterie v procentech. Funkce kontorluje mV baterie a na základě dat z PyBricks fóra kontroluje procento nabití baterie. Na základě procent funkce rozsvítí prostřední talčítko,<br>zelené = nabito<br>oranžová = skoro vybyto (na této úrovni se už program nezapne)<br>červená = vybyto<br>

**Parametry**<br>
Žádné<br>

**Return**<br>
Funkce vrací zda může program pokračovat dál nebo už je baterie moc vybytá. (True - pokud může pokračovat, False - Pokud nemůže pokračovat)

<br>
<br>
<br>

## Použité parametry
Použité paramtery jsou napsané ve formátu.<br>
`NÁZEV_PROMĚNÉ_V_SOUBORU = parameters.NÁZEV_PROMĚNÉ_V_PARAMETERS`<br>

<br>
Port pro hodní barevný senzor<br>
`COLOR_UP_PORT = parameters.COLOR_SENSOR_UP_PORT`<br>

<br>
Port pro spodní barevný senzor<br>
`COLOR_DOWN_PORT = parameters.COLOR_SENSOR_DOWN_PORT`<br>

<br>
mV plné baterie<br>
BATERRY_FULL = parameters.BATERRY_FULL<br>

<br>
mv skoro nabité baterie baterie<br>
`BATERRY_OK = parameters.BATERRY_OK`<br>

<br>
mV skoro vybité baterue<br>
`BATERRY_LOW = parameters.BATERRY_LOW`<br>

<br>
mV vybité baterie<br>
`BATERRY_CRITICAL = parameters.BATERRY_CRITICAL`<br>

<br>
mV baterie od které se už program nespustí<br>
`BATERRY_OFF = parameters.BATERRY_OFF`<br>

<br>
Jestli se má zapnout omezení baterie (BATERRY_OFF)<br>
`BATERRY_OFF_CONTROL = parameters.BATERRY_OFF_CONTROL`<br>
<br>
