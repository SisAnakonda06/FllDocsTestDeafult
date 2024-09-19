# menu.py
Soubor který se stará o menu a spoštění akcí zvolené v menu.

## Přehled funkcí

### ShowMenu()
`ShowMenu(Rides:bool, interrupt:bool)`<br>
Funkce pro výběr toho co má robot dělat dál. Jako první se spustí smyčka ve které jsou podmínky které čekají na stisknutí talčítek (vpravo, vlevo, prostřední tlačítko). Pokud se stiskno pravé tlačítko tak se zkontroluje zda v proměné pageIndex která slouží pro ukládání aktuální stránky není už moc velká, pokud ano tak pípne. To stejné se děje i když se stiskne levé tlačítko. Pokud se stiskne prostřední talčítk, smyčka se ukončí a spustí to co si uživatel vybral.


**Parametry**<br>
- Rides - Pokud se má zobrazit menu pro výběr jízd (deafult:False)<br>
- interrupt - Pokud se muze menu ukoncit (deafult:True)<br>

<br>
<br>

### RunByIndex()
`RunByIndex(index:int)`<br>
Funkce slouží pro spouštění věcí které byli vybrány ve funkci ShowMenu. Tato funkce se využívá pouze pro normální menu, ale ne pro menu na výběr jízd.

**Parametry**<br>
- index - Index věvi ktrá byla vybrána ve funkci ShowMenu()
<br>
<br>
<br>

## Použité parametry


Použité paramtery jsou napsané ve formátu.<br>
`NÁZEV_PROMĚNÉ_V_SOUBORU = parameters.NÁZEV_PROMĚNÉ_V_PARAMETERS`<br>

<br>
Obsah normálního menu<br>
`MENU_CONTENT = parameters.MENU_CONTENT_LETTER`<br>

<br>
Obsah menu pro výběr jízd<br>
`DEAFULT_DISPLAY_ORINTATION = parameters.DEAFULT_DISPLAY_ORINTATION`<br>

<br>
Základní hlasitost<br>
`DEAFULT_VOLUME = parameters.DEAFULT_VOLUME`<br>

<br>
Základní tlačítko pro zastavení programu<br>
`DEAFULT_STOP_BUTTON = parameters.DEAFULT_STOP_BUTTON `<br>

<br>
Tlačítk pro zastavení menu<br>
`MENU_INTERRUPT_BUTTONS = parameters.MENU_INTERRUPT_BUTTONS
`