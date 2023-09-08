## Linjär Regression

### Introduktion
Linjär regression är en grundläggande metod i Machine Learning. Metoden bygger en modell som förklarar sambandet mellan en eller flera oberoende variabler och en beroende variabel.  
  
Scenariot i vår uppgift är att förutspå huspris baserat på olika "features" såsom antalet rum, läge, husets storlek med mera. I detta scenario är husets pris den ***beroende variabeln*** och husets storlek, antal rum, läge, skick osv, de ***oberoende variablerna***.  
Man brukar skilja mellan “Simpel” linjär regression och “Multipel” linjär regression (MLR).  
  
### “Simpel” Linjär regression
Simpel Linjär regression innebär att det endast finns endast en (1) oberoende variabel, kan då också kallas “linjär regression”. 

#### Ekvationen
Just ordet “linjär” innebär att man försöker beskriva sambandet mellan den oberoende variabeln och den beroende variabeln linjärt (“längs en rät linje”), dvs med räta linjens ekvation, y = k*x + m, där 

k = koefficienten, linjens lutning, även dy/dx 

m = skärningspunkten, y-värdet där x är noll 

y = beroende variabeln. Andra namn på beroende variabeln är responsvariabel eller “label” på engelska. 

x = oberoende variabeln. Ett annat namn på oberoende variabler är förklarande variabler eller “feature” på engelska. 

Metoden att anpassa värden på koefficienten (k) och skärningspunkten (m), för att erhålla den minsta avvikelsen från observationerna, kallas ***minsta kvadratmetoden***.  
![Linjär Regression](/assets/LinjärRegression.png)

### Multipel linjär regression
Om man har två eller fler oberoende variabler, kallas detta multipel linjär regression (MLR). Multipel linjär regression skiljer sig ganska mycket från (simpel) linjär regression. 

Första steget i analysen bör vara att fundera kring vilken eller vilka oberoende variabler man ska använda, för att beskriva den beroende variabeln. I vårt fall är den beroende variabeln huspris. Oberoende variabler kan vara husets storlek, antal rum, område, husets skick eller tomtens storlek osv. 

#### Kategorivariabler
Oberoende variabler som inte är kvantifierbara kallas kategorivariabler. I vårt fall skulle den oberoende variabeln “område” vara av den typen. Andra kategorivariabler kan vara “man/kvinna”, “sant/falskt”, “nord/syd/ost/väst”, “ja/nej” osv. Kategorivariabler "översätts" till numeriska värden för att kunna hanteras matematiskt. Tex kan "ja" ha värdet 1 och "nej" värdet 0.

#### Ekvationen
Om man identifierar två oberoende variabler som man vill använda i sin analys, så kommer ekvationen se ut som följer: 

y = β<sub>0</sub> + β<sub>1</sub>*x<sub>1</sub> + β<sub>2</sub>*x<sub>2</sub> + Ω, där:

y = beroende variabeln

x<sub>1</sub> och x<sub>2</sub> = oberoende variablerna

β<sub>0</sub> = skärningspunkten om både X1 och X2 är noll.

β<sub>1</sub> och β<sub>2</sub> = koefficienterna för var och en av de oberoende variablerna

Ω = residual, error term

### Datainsamling: 
När man har valt oberoende variabler, så behöver man samla in data från ett antal försäljningar. Datan kan kanske hittas i någon databas över försäljningar? SQL?

Innan man kan göra analys på datan behöver den ordnas i tabellform. Varje rad i tebellen innebär en observation. I tabellen ska man ha värden på sin beroende variabel, samt värden för den eller de oberoende variablerna som man har valt att undersöka. Datan kan sparas i en databas, en excel-fil eller en csv-fil, tex. Ett krav bör vara att den enkelt kan läsas in i Python. Datan kan också manuellt skrivas in som en variabel i Python, tex som en lista.
![Tabell MLR, två oberoende variabler](/assets/multbyHand1.png)

### Analys av data:
När man har samlat in data, så ska man göra en del förberedande analys på den. Syftet är att förstå om man gjort ett bra val av oberoende variabler. Man vill att oberoende variabler ska påverka den beroende variabeln (stark korrelation), men att de valda oberoende variablerna ska ha minimal påverkan sinsemellan. I vårt exempel, kan man misstänka att det finns ett samband mellan de oberoende variablerna "husets strolek" och "antal rum". Dvs, ju större huset är, desto fler rumm har det troligen.

Testa de oberoende variablernas korrelation till den beroende variabeln. Detta för varje oberoende variabel. Görs genom ***scatterplots*** och ***statistiska verktyg***. Sytet är att identifiera om man valt oberoende variabler som har svag korrelation till den beroende variabeln. Oberoende variabler med svag korrelation till den beroende variabelns kan anses vara redundanta, ta bort dessa ur analysen. Behåll endast oberoende variabler som har stark korrelation med den beroende variabeln. 

Testa de oberoende variablernas korrelation till de andra oberoende variablerna. Görs på samma sätt som beskrivits ovan. Här vill man att det ska vara svag korrelation mellan de oberoende variablerna. Baserat på analysen får man avgöra om man vill ta bort någon oberoende variabel. Om man har ett starkt samband mellan valda oberoende variabler kallas detta ***kolinjäritet***, vilket alltså ska undvikas.

### Parametersättning
Nästa steg är att parametersätta koefficienterna för de oberoende variablerna. Eftersom det är två (eller fler) variabler, är det inte lika "enkelt" som för en variabel. Man använder dator i detta steget, involverar mycket matrisberäkningar.

### Utvärdera modellen
När modellen är parametersatt kan man utvärdera den i syfte att försöka förstå om den är "rimlig". Viktiga metrics att ha koll på och lära sig om verkar vara R<sup>2</sup> (R-squared), variance, modellfel med flera. Utvärdera även modellen genom att prova mata den med test data för att kvantifera modellfel.

### Driftsätt modellen och börja gör prediktioner
Nästa steg är att göra använda modellen för att göra prediktioner. Om antalet oberoende variabler är litet, säg 5-10 stycken, så bör man enkelt kunna driftsätta detta tex i en
-  Excel-"snurra"
-  En funktion i Python med inputargument som motsvarar de oberoende variablerna
-  En app i en mobiltelefon
 


