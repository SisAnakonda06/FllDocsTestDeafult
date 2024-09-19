# Návod a přehled 
## Přehled souborů
[main.py](./main.md)<br>
[movement.py](./movement.md)<br>
[sensors.py](./sensors.md)<br>
[menu.py](./menu.md)<br>
[rideSelect.py](./rideSelect.py)<br>

## Návod
Robot se ovládá pomocí jeho menu. V menu jsou možnosti `R`, `T` `I`. Pro phybování v menu souží šipky a pro potvrzení slouží prostřední tlačítko. Prostřední talčítko svítí podle stavu baterie<br>
Zelená - Nabito<br>
Oranžová - Skoro nabito

## Možnost `R` - Výběr jízd
Možnost `R` slouží pro spuštění výběru jízd.<br>

### Výběr jízd
Pokud po výběru `R` v hlavním menu se objeví kolečko přes celý displej to znamená že program využívá pro výběr jízd barevný senzor, potom stačí na sadit nástavec a pokud barava která se objeví na prostředním tlačítku souhlasí s barvou nástavcu zmáčknutím kterkoliv tlačítka, kromě bluethoot (slouží pro vypnutí programu) se spustí danná jízda. <br>
Pokud se objeví písmeno, to znamená že robot nevyužívá barevný senzor pro výběr jízd, ale využívá menu. V menu je ppotřeba podle písmena které se obejví na displeji a baryv která se rozsvítí na prostředním talčítku. V menu se pohybuje pomocí šipek a povrzuje se pomocí prostředního tlačítka. Pro opouštění menu stačí podržet obě šipky.<br>
**Zastavení jízd**<br>
Robota stačí otočit směrem motorama pro nástavce nahoru, potom se robot automaticky zastaví<br>

## Možnost `T` - Testování robota
Možnost slouží pro testování robota, jeho motorů, senzorů a gyroskopu. <br>

**Průběh testování**
Pokud jsou všchny testování povoleny v parameters.py tak testování jdou za sebou v tomto pořadí: <br>
**1.** Testování motorů<br>
**2.** Testování senzorů (zatím jenom barevných)<br>
**3.** Testování gyroskopu<br>

### Testování motorů
Toto testování je jako první. Ukáže se animace na spodním řádku a potom co se dokončí, spustí se první motor, společně s tím se ukáže animace ryhlostí motoru (podle rychlosti se rozsvítí pixely ve sloupečku). Testování motorů je v pořadí (s jakým sloupečkem se zobrazuje, z leva do prava):<br>
**1.** Pravý motor pro pohyb, sloupeček 1.<br>
**2.** Pravý motor pro nástavce, sloupeček 2.<br>
**3.** Levý  motor pro nástavce, sloupeček 3.<br>
**4.** Levý sloupeček pro nástavce, soupeček 4.<br>
Po otestování každého z motorů, robot vyžaduje potvrzení že se otočil správně.<br>

### Testování senzorů
Testování senzorů je jako druhé po motorech. Je rozděleno na dvě části<br>
**1.** Testování světel v senzoru<br>
**2.** Testování čtení barev <br>

#### Testování světel v barevncýh senzorech
Jako první se na displeji objeví šipka ketrá ukazuje na právě testovaný senzor. V každém barevném senzoru se rozsvítí světlo. Světla se rozsvěcují pomalu, od jasu 0 až do 100 po 10.
Po otestování horního senzoru začne šipka ukazovat "dolů" a to stejné se stane u spodního senzrou.<br>

#### Testování čtení barev
Po testování světel v barevých senzorech se testuje četná barev. Čtení barev se tesutje na Červené, Zelené a Modré v tomto pořadí. Vždy se rozsvítí ten senzor kam se má ukázat barava. První se testuje horní senzor a ptom spodní senzor. Prostřední talčítko se vždy rozsvítí barovu kterou senzor potřebuje vidět, pokud ji viděl tak pípne.<br>

### Testování gyroskopu
Hned po testování senzrů se bude testovat gyroskop, robot počká než se nebude hýbat/bude na stole a vyresetuje gyrokop a připraví se. Po tom co se vyresetuje se otočí na 360 a zpět na 0. Potom co se otočí bude požadovat odshozhlsaení že otočení proběhlo v pořádku. To stjné, ale na druhou stranu, na -360 a zpět 0 a odsouhlasení. Po doknončení tohoto testu je testování robota dokoncčeno

## Možnost `I` - Automatická říprava (initalize)
Po výběru možnosti `I` robot bude požadovat položit na stůl a aby se s ním nehýbalo. Po tom co zaznamená že se nehýbe, spustí resetování gyroskopu, zapisování hodnoty pro intrrupt a zapínání (rzsvěcení) barevných senzorů.
