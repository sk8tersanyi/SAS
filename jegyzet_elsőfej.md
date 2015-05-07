# Első fejezet

## A SAS nyelv
 * az egyes parancsok kiértékelése a megadás sorrendjéban történik
 * FONTOS - minden parancs/kijelentés végén pontosvessző kell álljon
 * maga a szöveg szerkeztése ( pontosvesszők használata mellett ) mindegy, de célszerű különböző sorokra tördelni
 * a program megértése kommentek használatával fokozható
 * kétfajta komment van - mind a kettővel lehet többsoros kommenteket írni
  * * _komment szövege_ ;
  * /* _komment szövege_ */ - ezt néha a fordító nem szereti ( OP rendszer függő )
 
## SAS adathalmazok
 * a SAS nagyon rugalmasan és felhasználóbarát módon kezeli a megadott nyers adatot - csak az elérhetőséget kell megadni neki
 * mint ahogyan azt elvárhatjuk egy SAS adatbázis változók ( oszlopok ) és megfigyelések (sorok ) táblázata
 * két adattípus létezik:
  * numerikus - itt lehet plusz, mínusz, tizedes pont, illetve E a tudományos izéke
  * karakter - ebbe megy minden más, továbbá ez csak 32767 karakter hosszú lehet
 * ha egy adat betűt, vagy speciális karaktert tartalmaz, akkor automatikusan karakter tipusú lesz
 * különben nekünk van lehetőségünk eldönteni, hogyan kezeljük a megadott adatot
 * SAS-ban a hiányzó numerikus adatot ponttal, míg a hiányzó karakter adatot üres mezővel reprezentáljuk
 * egy ilyen táblában legfeljebb 32767 változónk lehet, de megfigyelésből annyit vehetünk fel amennyit a gép elbír
 * a változók neveire teljesülnie kell, hogy: legfeljebb 32 karakter husszúak; betűvel, vagy alulvonással kezdődnek; csak betűket, számjegyeket, vagy alulvonásokat tartalmaznak; lehet bennük kicsi és nagybetű is ( habár ez lényegtelen! )
 * FONTOS - változók nevében sincs különbség kicsi- és nagybetű között
 * annyi történik, hogy mikor kiíratjuk az eredményt, akkor az adott változót az első feltűnésének megfelelően írja ki a program
 * egy ilyen SAS adatbázis alapinformációkat tárol az adathalmaz összességéről ( név, dátum) és az egyes változókról külön külön ( típus, hossz, pozíció az adatbázison belül )
 
## SAS programok két része
 * minden SAS program két különböző programblokk tipust felhasználva épül fel
 * az egyik az úgynevezett DATA-step, mellyel SAS adatbázist tudunk generálni, míg a másik a PROC-step, amivel pedig adott adatbázison tudunk eljárásokat futtatni
 * az ezen blokkokban futtatható SAS parancsok - pont az alkalmazásbeli eltérésük miatt - áltlában csak az egyikben, illetve csak a másikban használhatóak
 * **DATA-step**:
  * egy ilyen blokk a DATA paranccsal kezdődik, és ezt követi az aktuálisan használt SAS adatbázis neve
  * adatok beolvasása és módosítása; SAS adatbázis készítése
  * mivel itt adatot olvasunk be, a blokkon belül lehet DO ciklus, IF-THEN/ELSE logikai kapcsolat és rengeteg numerikus, illetve karakter függvény
 * **PROC-step**:
  * egy ilyen blokk a PROC paranccsal kezdődik, majd, hogy mit akarunk csinálni és, hogy mely SAS adatbázissal
  * ilyen lépésben lehet rendezni a megfigyeléseinket, elemzéseket generálni, vagy ábrázolni
 * az egyes blokkokat a RUN paranccsal zárhatjuk le, ekkor ez azt jelenti a programnak, hogy az adott blokk sorait/parancsait olvassa és hajtsa végre
 * ha egymás után jönnek a blokkok, akkor nem feltétlenül szükséges a RUN parancsot kiírni, de célszerű, mert lehetséges, hogy csak egy egy blokkot akarunk futtatni
 * az eddigiekből úgy tűnhet, hogy egy SAS program felépítése csak olyan lehet, hogy a DATA-step-pek mindig megelőzik a PROC-step-pekket, de ez persze nem igaz - sőt annyira nem igaz, hogy az is kijelenthető ( az eddigieknek ellentmondva ), hogy a két blokk közti különbségek homályosak

## A DATA-step beépített ciklusa
 * egy DATA-step blokkon belül a parancsok kiértékelése, illetve adatbázisok beolvasása soronként történik
 * FONTOS - ugyanez igaz egy adabázisra is, azaz úgy számolunk egy DATA-step blokkon belül, hogy vesszük az adatbázis első sorát, ezt kiértékeljük a parancssoroknak megfelelően, utána tvoábbugrunk a következő megfigyelésre és ott ugyanez ... így iterálva tovább
 * az iterált folyamat i. lépése: **az adatbázis i. megfigyelése ( INPUT )** -> **DATA-step parancssorainak végrehajtása soronként** -> **az adatbázis i. megfigyelése ( OUTPUT )**
 
## Lehetőségek a SAS programunk szerkeztésére/futtatására
 * **SAS windowing environment**: alapfelület, ha futtatjuk a SAS-t - interaktív; EZ!
 * **SAS Enterprise Guide**: már nem igazán van ilyen, de itt csak futtatni lehet a programjainkat
 * **nem interaktv mód**: amikor a SAS programunk külön fájlban van és terminálból futtatjuk a *SAS* parancs segítségével
 * **batch, avagy háttér mód**: evvel be tudjuk ütemezni a a program futtatását a gépünk egyéb teendői közé - nem minden rendszeren elérhető
 * **távoli futtatás**: lokálisan írjuk és egy távoli szervergépen futtatjuk, ami az eredményt visszaküldi
 * **interaktív soronkénti mód**: NE!!!!! - nem lehet visszaugrani ha hiba van, előről kell az egészet

## SAS Windowing Environmnet ablakai és parancsai
 * anno nem volt lehetőség ezen felület megjelenésének beállítására/módosítására, de mára ez megváltozott és teljesen flexibilis lett
 * öt különböző alap SAS ablak típust különböztetünk meg: **Results**, **Explorer**, **Editor**, **Log**, **Output** ( utóbbi három a programozási ablakok ):
  * **Editor**: ez egy feltúrbózott szövegszerkeztő ( szintaxisra érzékeny színes kódsorok ), mellyel a programunkat könnyen tudjuk módosítani, illetve az egyes ciklusokat bezárni, stb.
  * **Log**: a program futtatása után az aktuális fordítással megjelenő hibák és figyelmeztetések jegyzékét, illetve egyéb értelemszerű adatokat tartalmaz
  * **Output**: ha van a kimenetben adatkiírás, akkor az itt jelenik meg
  * **Results**: annak a táblázatba szedése, hogy mi szerepel az előbbi ablakban
  * **Explorer**: hozzáférést biztosít a SAS könyvtárjainkhoz és fáljainkhoz
 * persze ezeken felül további típusok is léteznek - például a **Help**, **Options** és ilyenek
 * hasonlóan a megszokott interaktív programozói felületekhez, a SAS ugyanúgy tartalmaz egy parancs sort, ahol lehetőségünk van menük elérésére ( például Help, kivágás, másolás ), a toolbar használatára ( gyorsgombok )
