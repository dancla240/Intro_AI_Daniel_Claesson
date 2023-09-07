## Beskriv hur linjär regression fungerar. 

Linjär regression undersöker sambandet mellan en eller flera oberoende variabler och en beroende variabel. Metoden är grundläggande i Machine Learning. 

I vårt fall är husets pris den beroende variabeln och husets storlek, antal rum, läge, skick osv, den eller de oberoende variablerna. 

Man brukar skilja mellan “Simpel” linjär regression och “Multipel” linjär regression (MLR). 

“Simpel” Linjär regression innebär att det endast finns en oberoende variabel, kan då också kallas “linjär regression”. 

Just ordet “linjär” innebär att man försöker beskriva sambandet mellan den oberoende variabeln och den beroende variabeln linjärt (“längs en rät linje”), dvs med räta linjens ekvation, y = k*x + m, där 

K = koefficienten, linjens lutning, även dy/dx 

m = skärningspunkten, y-värdet där x är noll 

Y = beroende variabeln. Andra namn på beroende variabeln är responsvariabel eller “label” på engelska. 

X = oberoende variabeln. Ett annat namn på oberoende variabler är förklarande variabler eller “feature” på engelska. 

Metoden att anpassa värden på koefficienten (k) och skärningspunkten (m), för att erhålla den minsta avvikelsen från observationerna, kallas “minsta kvadratmetoden”. 

 

Multipel linjär regression: Om man har två eller fler oberoende variabler, kallas detta multipel linjär regression (MLR). Multipel regression skiljer sig ganska mycket från simpel linjär regression. 

Första steget i analysen bör vara att fundera kring vilken eller vilka oberoende variabler man ska använda, för att beskriva den beroende variabeln. I vårt fall är den beroende variabeln huspris. Oberoende variabler kan vara husets storlek, antal rum, område, husets skick eller tomtens storlek osv. 

Kategorivariabler: Oberoende variabler som inte är kvantifierbara kallas kategorivariabler. I vårt fall skulle den oberoende variabeln “område” vara av den typen. Andra kategorivariabler kan vara “man/kvinna”, “sant/falskt”, “nord/syd/ost/väst”, “ja/nej” osv. 

Man vill att oberoende variabler ska påverka den beroende variabeln (stark korrelation), men att de valda oberoende variablerna ska ha minimal påverkan sinsemellan. 

Om man identifierar två oberoende variabler som man vill använda i sin analys, så kommer ekvationen se ut som följer: 

Y = m + B1*X1 + B2*X2 + Error, där 

Y = beroende variabeln 

M = skärningspunkten om både X1 och X2 är noll. 

Error = fel 

 

Datainsamling: När man har valt oberoende variabler, så behöver man samla in data från ett antal försäljningar. Datan kan kanske hittas i någon databas över försäljningar? SQL? 

Datan ska samlas i tabellform. I tabellen ska man ha värden på sin beroende variabel, samt värden för den eller de oberoende variablerna som man har valt att undersöka. 

Varje rad i tabellen innebär en observation. 

Datan kan ha sitt ursprung i en databas, en excel-fil eller en csv-fil, tex. 

När man har samlat in data, så ska man göra en del förberedande analys på den. Syftet är att “sanity checka” att man gjort ett bra val av oberoende variabler. 

Testa de oberoende variablernas korrelation till den beroende variabeln. Detta för varje oberoende variabel. Görs genom scatterplots och statistiska verktyg. Sytet är att identifiera om man valt oberoende variabler som har svag korrelation till den beroende variabeln. Oberoende variabler med svag korrelation till den beroende variabelns kan anses vara redundanta, ta bort dessa ur analysen. Behåll endast oberoende variabler som har stark korrelation med den beroende variabeln. 

Testa de oberoende variablernas korrelation till de andra oberoende variablerna. Görs på samma sätt som beskrivits ovan. Här vill man att det ska vara svag korrelation mellan de oberoende variablerna. Baserat på analysen får man avgöra om man vill ta bort någon oberoende variabel. Om man har ett starkt samband mellan valda oberoende variabler kallas detta kolinjäritet, vilket alltså ska undvikas. Tex, i vårt exempel, så kan man tänka sig att det finns en ganska stark korrelation mellan husets storlek och antal rum i huset. Dvs, ju större huset är så finns det troligen också fler rum. 

Parametersättning: Nästa steg är att parametersätta variablerna för 

 

 

Vilka teknologier används i de olika stegen? 

Scatterplots 

Korrelationsanalys: Ett mått på korrelationen mellan den oberoende variabeln och den beroende variabeln R2 (R squared). Ett högt värde betyder hög korrelation. 

I Python finns verktyg för att analysera. 

Hur kan indriftsätta modellen? 
