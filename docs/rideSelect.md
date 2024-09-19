# RideSelect.py
Funkce por vybírání a spištění jízd.

## Přehled funkcí

### RunRide
`RunRide()`<br>
Funkce pro spouštení vybraných jízd. Funkce jako první vyčistí displej a potom spustí smyčku, která běží dokud se nespustí jízda. 
Jako první ve smyčce se zkontroluje zda se má používat barevný senzor nebo menu. Pokud se má používat barevný senzor, ukáže se na kolečko na displeji pro ukázání používání barevného senzoru, pokud barevný senzor uvidí barvu nástavce kterou má nastavenou, rozsvítí se prstřední talčítko danou barvou, zmáčknutím jakékoliv tlačítka kromě blutoot, se spustí jízda danné bary. Pokud se ale nemá používat barevný senzor, objeví se menu s výběrem jízd, každá jízda má své písmno a barvu, v menu se na displeji objeví písmeno danné jízdy a rozsvítí se podle ní i prostřední tlačítko, šipkami a prostředním talčíkem lze zvolit danu jízdu. Jízdy se v programu nevybýrají podle barvy nebo písmena ale podle jejich indexu. Každý soubor s jízdou má svůj index a položka v menu/barva z barveného snzoru, se přiřazuje k souboru s jízdou pomocí indexu. 

**Použití**<br>
V hlavním menu zvolíte výběr/spuštění jízd. Pokud se na displjeji objeví tlačítko, stačí na robota nasadit nástavec a pokud se objeví na prostředním talčítku stejná barav jakou má naástec, stačí zmáčnkou jakékoliv tláčítko pro spuštění jízdy kromě bluethoot, to slouží pro vypnutí programu. Pokud se na displeji neobjevá kolečko ale písmeno, to znamená je nastaveno že robot nemá baravená senzor pro čtení nastavců. Obejví se menu vekterém se vybere nástavec buď podle jeho barvy ketrá se obejví na prostřeedím tlačítku tak na displeji se obejví písmeno danné jízdy, bývato první písmeno bravy nebo názvu nástavce.


## Použité parametry
Použité paramtery jsou napsané ve formátu.<br>
`NÁZEV_PROMĚNÉ_V_SOUBORU = parameters.NÁZEV_PROMĚNÉ_V_PARAMETERS`<br>

Zda se má používat barevný senzor pro výběr jízd<br>
`USE_COLOR_SENSOR = parameters.USE_COLOR_SENSOR`<br>

<br>

Přiřazení jízd k baravám a písmenům<br>
`MATCH_COLOR_TO_RIDE = parameters.MATCH_COLOR_TO_RIDE`<br>

<br>

Nastavení protu pro horní barevný senzor<br>
`COLOR_SENSOR_PORT = parameters.COLOR_SENSOR_UP_PORT`<br>

<br>

Barvy nástavců<br>
`RIDE_COLORS = parameters.RIDE_COLORS`<br>

