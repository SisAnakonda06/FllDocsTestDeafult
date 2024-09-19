# movement.py

Soubor sloužící ovládání pohybů motorů. V souboru se také nastavuje PID regulátor. 

## Funkce

### Straight()
```py
Straight(value:float, usePID:bool, speed:int, acc:int, interrupt:bool, last:bool)
```
Funkce nejdříve nastaví rychlost a akceleraci pro jizdu. Po nastaveni zkontroluje zda se bude pouzivat PID nebo na 
zaklade usePID. Pokud se pouzivat bude (usePID = True) tak se zkontroluje zda robot pojede dopředu nebo dozadu. Pokud
pojede dopredu nasatvi se konstatnty pro jizdu dopredu, ale pokud pojede dozadu nastavi se konstanty pro jizdu dozadu.
Az se toto vse nastavi tak se sputi motory na vzdalenost value

**Parametry:**<br>
- value - Jak daleko ma jet<br>
- wait - Zda ma cekat az se tento pohyb dokonci<br>
- usePID - Zda se ma pouzivat PID (defult: True)<br>
- speed - Jakou rychlosti ma jet (deafult: DEAFULT_SPEED_STRAIGHT_BASE = 900)<br>
- acc - Jakou akcelereaci ma zrychlovat (deafult: DEAFULT_ACC_STRAIGHT_BASE = 1000)<br>

<br>
<br>

### Turn()

```py
Turn(onAngle:int, interrupt:bool, speed:int, acc:int, last:bool)
```
Funkce která se stará o otáční robota. Funkce jako první zkontroluje zda je to poslední pohyb nebo ne. Pokud je to poslední pohyb nastaví se zastavení na nedržení polohy, ale pokud to není poslední pohyb tak se zastavení nastaví na držení polohy motoru. Následně se spustí otáčení na úhel a spoečně s tím se spustí interrupt na základě parametru interrupt.

**Parametry**<br>
- onAngle - Na jaký úhel se má robot otočit<br>
- interrupt - Zda se má robot zastavit pokud se zvedne<br>
- speed - Jakou rychlostí se má robot otáčet<br>
- acc - Jak moc ma akcelerovat při zatáční<br>
- last - Zda je to poslední pohyb nebo ne<br>

<br>
<br>

### Curve()

```py
Curve(radius:float, angle:int, wait:bool speed, acc:int, last:bool)
```
Funkce jako první nastaví rychlost a akceleraci. Potom zkontroluje zda je pohyb poslední. Pokud je pohyb poslení. Pokud je pohyb poslední, tak se nastaví zastavení na na nedržení polohy motorů. Potom se spustí motory, společně s funkcí interrupt ketrá se stavá o zastavení robota při zvendnutí. Robot se při jízdě trošku třese.

**Parametery**<br>
- radius - Poloměr kruhu<br>
- angle - Uhel podel kruhu<br>
- interrupt - Pokud se má robot při zvednutí zastavit (deafult:False)<br>
- speed - Jakou rychlostí se má jet (deafult:DEAFULT_SPEED_STRAIGHT_BASE = 900)<br>
- acc - Nastavení zrychlení (deafult: DEAFULT_ACC_STRAIGHT_BASE = 1000)<br>
- last Zda je to poslední pohyb

<br>
<br>

### TurnToolTo

```py
TurntTool(angle: int, speed:int, motorSelect:str, wait:bool, last:bool)
```
Funkce jako první zkontroluje kterým motorem se má otáčet a potom spustí motory s danou rychlostí na danný úhel.

**Patametry**
- angle - O kolik se ma motor otočit<br>
- speed - Jakou rychlostí se má motor otočit<br>
- motorSelect - Jaky motor se má otočit (R/L)<br>
- interrupt - Zda má robot zastavit když se zvedne (deafult:True)<br>
- last - Zda je tento pohyb poslední (deafult:False)<br>

<br>
<br>

### InitialValue()

```py
InitialValue(resetWait:bool)
```

Funkce pro zapsání prvontích hodnto z gyroskopu (pro interrupt), resetování gyroskopu pro zatáčení a připravení barevých senzorů (jejich rozsvícení). Funkce jako první počká nežrobot bude stát pevně a až potom vše nastaví a připraví. Tato funkce se spušít při startu programu, před testem gyroskopu a při zvolení I v menu. Funkci bylo potřeba vytvořit pro přesnější hýbání robota přípravu robota. 

**Parametry**<br>
- resetWait - zda se má čekat než se robot uklidní/bude na stole.<br>

<br>
<br>

### Interrupt()
```py
Interrupt(gear)
```
Tato funkce slouží k zastavení pohybu při zvednutí robota. Jako první se spustí smyčka která běží dokud motor nedokončí svůj pohyb nebo robot se nezvedne. Pokud se smyčka ukončí tak se program přesune do menu pro výběr jízd. Tato funkce se spouští při jakémkoliv pohybu, pokud není vypnutý. Funke využívá možnosti `wait` při spouštění nebo obládání motorů, tak že běží smyčka ve funkci a čeká než se motor dohýbe, toto umožňuje využít čas který byl použit při čekání dokončení pohybu efektivněji, kontrolování natočení robota.

**Parametry**<br>
- gear - Co se má při zvednutí zastavit, proměná motoru ketrý se právě hýbe.

<br>
<br>
<br>

## Použité parametry
Použité paramtery jsou napsané ve formátu.<br>
`NÁZEV_PROMĚNÉ_V_SOUBORU = parameters.NÁZEV_PROMĚNÉ_V_PARAMETERS`<br>
<br>

Nastavení konstant PID pro jízdu vpřed
```py
K_P_STRAIGHT_BASE = parameters.K_P_STRAIGHT_BASE
K_I_STRAIGHT_BASE = parameters.K_I_STRAIGHT_BASE
K_D_STRAIGHT_BASE = parameters.K_D_STRAIGHT_BASE
```
<br>

Integral deadzone pro PID regulátor<br>
`INTEGRAL_DEADZONE_STRAIGHT_BASE = parameters.INTEGRAL_DEADZONE_STRAIGHT_BASE`<br>
<br>

Integral rate pro PID regulátor<br>
`INTEGRAL_RATE_STRAIGHT_BASE = parameters.INTEGRAL_RATE_STRAIGHT_BASE`<br>
<br>

Konstanty pro vypnuté PID
```py
K_P_STRAIGHT_BASE_OFF = parameters.K_P_STRAIGHT_BASE_OFF 
K_I_STRAIGHT_BASE_OFF = parameters.K_I_STRAIGHT_BASE_OFF 
K_D_STRAIGHT_BASE_OFF = parameters.K_D_STRAIGHT_BASE_OFF 
```
<br>

Integral deadzone pro vypnuté PID<br>
`INTEGRAL_DEADZONE_STRAIGHT_BASE_OFF = parameters.INTEGRAL_DEADZONE_STRAIGHT_BASE_OFF`<br>
<br>

Integral rate pro vypnuté PID<br>
`INTEGRAL_RATE_STRAIGHT_BASE_OFF = parameters.INTEGRAL_RATE_STRAIGHT_BASE_OFF`<br>
<br>

Základní rychlost pro jízdu dopředu<br>
`DEAFULT_SPEED_STRAIGHT_BASE = parameters.DEAFULT_SPEED_STRAIGHT_BASE`<br>
<br>

Zákldaní akcelrace pro jízdu dopředu<br>
`DEAFULT_ACC_STRAIGHT_BASE = parameters.DEAFULT_ACC_STRAIGHT_BASE`<br>
<br>

Základní rychlost zatáčení<br>
`DEAFULT_TURN_RATE_BASE = parameters.DEAFULT_TURN_RATE_BASE`<br>
<br>

Základní akcelerace pro zatáčení<br>
`DEAFULT_TURN_ACC_BASE = parameters.DEAFULT_TURN_ACC_BASE`<br>
<br>

Jestli se má při jízdě dopředu a zátáčení používat gyroskop pro rovnání<br>
`DEAFULT_USEING_GYRO = parameters.DEAFULT_USING_GYRO_BASE`<br>
<br>

Nastavení portů pro motory na pohyb<br>
```py
MOTOR_R_PORT = parameters.MOTOR_R_PORT
MOTOR_L_PORT = parameters.MOTOR_L_PORT 
```
<br>

Nastavení portů pro motory na nástavce<br>
```py
MOTOR_ATT_R_PORT = parameters.MOTOR_ATT_R_PORT 
MOTOR_ATT_L_PORT = parameters.MOTOR_ATT_L_PORT
```
<br>

Nastavení směru otáčení motorů pro jízdu<br>
```py
MOTOR_L_DIRECTION = parameters.MOTOR_L_DIRECTION 
MOTOR_R_DIRECTION = parameters.MOTOR_R_DIRECTION
```
<br>

Nastavení axle tarck (vzdálensot mezi body kde se robot dotýká země)<br>
`AXLE_TRACK = parameters.AXLE_TRACK`<br>
<br>

Velikost koleček<br>
`WHEEL_DIAMETER = parameters.WHEEL_DIAMETER`<br>
<br>

Od jaké vzdálenosti má robot jet dopředu<br>
`MINMAL_STRAIGHT_VALUE_BASE = parameters.MINIMAL_STRAIGHT_VALUE_BASE`<br>
<br>

Od jaké vzdálenosti má robot jet dozadu<br>
`MINIMAL_BACK_VALUE_BASE = parameters.MINIMAL_BACK_VALUE_BASE`<br>
<br>

Nastavení úhlu, o kolik se musí robot otočit pro aktivaci interrupt<br>
`INTERRUPT_ANGLE = parameters.INTERRUPT_ANGLE`<br>
<br>

Nastavení jakým způsbem má zastavit pokud je to poslední pohyb<br>
`STOP_IF_LAST = parameters.STOP_IF_LAST`<br>
<br>

Nastavení jakým způsobem má zastavit pokud to není poslední pohyb<br>
`STOP_IF_NOT_LAST = parameters.STOP_IF_NOT_LAST`<br>
<br>

Normální rychlost animací<br>
`NORMAL_ANIMATIONS = parameters.NORMAL_ANIMATIONS`<br>
<br>
