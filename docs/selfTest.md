# selfTest.py
Tento soubro slouží pro testování robota, jeho motorů, senzorů a speciálně gyroskpu. To co má testovat lze vše nastavit v parameters.py
## Přehled funkcí

### Start()
`Start()`<br>
Funkce pro spouštění jednotlivých testů na základě nastaení v parameters.py.

**Parametry** 
Žádné<br>

<br>
<br>

### TestMotors
`TestMotors(graphics: bool)`<br>
Funkce pro testování motorů. Nejdříve se ukáže animace testování motorů, vyčistí sed displej a spustí se smyčka která zkusí každy motor který jse zpasaný v parameters.py. Otočí motorem a zároveň ukáže animace, po dokončení pohybu se motor vypne.

**Průběh testování**
Funkce jako první ukáže animaci, která oznamuje, že se budou testovat motory. Spustí se první motor a zároveň se spustí animace rychlosti. Každý motor má svůj sloupeček. Krajní (0. a 4.) slouží pro motory na pohyb (base) prostřední (2. a 3.) slouží pro motory na nástavce.

**Parametry**<br>
- graphics - Jestli se má v průběh testování naznačovat grafickým znázorněním.<br>

<br>
<br>

### Sensors
`Sensors()`<br>
Funkce která slouží pro testování senzorů (zatím jenom barevných). Funkce se skládá ze dvou daších funkcí. <br>

#### Lights
`Lights()`<br>
Pdfunkce funkce `Sensors()` pro testování světel v barevných senzorech. Nejdříve se psustí smyš'čka která vyzkouší všechny barevné senzory. Každý se vybere a v něm se vybere jaké ze 3 světel se má rozsvítit a jak moc.<br>

**Průběh testování**<br>
Jako první se objeví šipka která ukazuje směrem který barevný senzor s ebude zkoušet. U každého senzoru se rozsvítí každé ze tří světel s postupným jasem které se zvyšuje po 10 od 0 po 100.

<br>

#### Colors
`Colors()`<br>
Podfunkce funkce `Sensors()` pro testování čtení barev pomocí barevných senzorů. Nejdříve se spustí smyčka která vyzkouší všechny baarevné senzory. Po tom co jeden vybere, čeká než uvidí požadovanou barvu, mezitím co čeká ukazuje animaci a bliká prostřední tlačítko požadovanou barvou. Pokud ji uvidí pípne a přejde na další barvu/senzor.<br>

**Průběh testování**<br>
Displej dvakrát zabliká a potom žačne blikat prostřední tlačítko barvou kterou barevný senzor potřebuji videět. Každý senzor potřebuje vidět červenou, modrou a zelenou. Potom co barvu senzor uvidí pípne a buď začne blkat další barvou kterou potřebuje vidět nebo se horní senzor zhase as posdní se rozsvítí.<br>

<br>
<br>

### Gyro
`Gyro()`<br>
Funkce pro testování gyroskopu pomocí zatáčení. Jako první funkce čeká než se robot uklidí/položí se na stůl, tím se zajití že se nebude hýbat a potom se okamžitě nastaví gyroskop pro co nejpřesnější zatáčení. Potom co se to nastaví robot se otočí na 360 a zpět na 0, to setejné na ruhou stranu, -360 a 0. Po každém otočení na 0, musí uživtel odsouhlasit že otočení proběhlo v pořádku.<br>

**Průběh testování**<br>
Robot čkaá než bude pevně stát, vyresetuje si gyroskop a otčí se na 360 a zpět na 0, potom robot bude požadovat odsoouhlasení že otočení proběho vpořádku a přesně, to stejné na druhou stranu. Na -360 a zpět na 0 a odsouhlasení.


## Pouižté parametry

Použité paramtery jsou napsané ve formátu.<br>
`NÁZEV_PROMĚNÉ_V_SOUBORU = parameters.NÁZEV_PROMĚNÉ_V_PARAMETERS`<br>

<br>
Pořadí testování motorů<br>
`MOTOR_ORDER_TEST = parameters.MOTOR_ORDER_TEST`<br>

<br>
Nastavení sloupce pro zobrazení průběhu testování jednotlivých motorů<br>
`MOTOR_GRAPHICS_DISPLAY_COLUMN = parameters.MOTOR_GRAPHICS_DISPLAY_COLUMN`<br>

<br>
Získávání protů pro barevné senzory<br>
```py
COLOR_SENSOR_UP_PORT = parameters.COLOR_SENSOR_UP_PORT # pro horní senzor
COLOR_SENSOR_DOWN_PORT = parameters.COLOR_SENSOR_DOWN_PORT # pro spodní senzor
```<br>

<br>
Barvy které se mají otestovat u barevných senzorů<br>
`TESTING_COLORS = parameters.TESTING_COLORS`<br>

<br>
Jaké snzory se maji testovat<br>
`TESTING_SENSORS = parameters.TESTING_SENSORS`<br>

<br>
Zda se mají testotvat motory<br>
`MOTOR_TESTING = parameters.MOTOR_TESTING`<br>

<br>
Zda se mají testovat barevné senzory<br>
`COLOR_TESTING = parameters.TESTING_COLORS`<br>

<br>
Zda se má testovat gyroskop<br>
`GYRO_TESTING = parameters.GYRO_TESTING`<br>

<br>
Cekaní nez nez se program dostane z menu do tesotvání motorů<br>
`ST_WAIT_MOTOR_TEST = parameters.ST_WAIT_MOTOR_TEST`<br>

<br>
Čekání vyčištění displeje<br>
`CLEAR_DISPLAY = parameters.DISPLY_CLEAR_DISPLEY`<br>

<br>
Rychlost animace<br>
`FAST_ANIMATION = parameters.FAST_ANIMATIONS`<br>

<br>
Normální rychlost animace<br>
`NORMAL_ANIMATIONS = parameters.NORMAL_ANIMATIONS`<br>

<br>
Rychlost hodně pomalé animace<br>
`VERY_SLOW_ANIMATION = parameters.VERY_SLOW_ANIMATION`

<br>
Základní hlasitost<br>
`DEAFULT_VOLUME = parameters.DEAFULT_VOLUME`<br>