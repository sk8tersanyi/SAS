# Első fejezet - második rész

## SAS programok fordítása

  * mivel javarészt Windows-on fogok dolgozni, ezért nincs benne semmi különös - beviszem az editorba és értelemszerűen futtatom
  * a futtatás történhet a toolbar "futó emberke" ikonjával, vagy a parancs sávba a **SUBMIT** parancsot írva
  * ha minden klappol, akkor az eredmény megjelenik az Output és Log ablakokban, illetve új elem adódik a Results-hoz   
  * ha esetlegesen nem Windows-on kell dolgozni, akkor futtatás után a bevitt program "eltűnik", ezt visszahozni **RECALL** paranccsal lehet, vagy a Run menü Recall Last Submit opciójának kiválasztásával
  * ez mindig az eggyel korábban futtatott programot küldi vissza, így sokszor meghívva vissza tudunk térni a legkezdetibb állapothoz is
 
## A Log értelmezése

  * a Windows-on az az alapértelmezett ( amikor ne központi szerveren dolgozunk ) ha fordítás után a Log, az Output-hoz hasonlóan, felugrik a felületen
  * habár az apróbb programoknál nem feltétlenül hasznos, de mindenképp érdemes átnézni mit is ad meg a kimenetében:
   * az első pár sor mindig az aktuálisan használt SAS paramétereit tartalmazza
   * akár nagyon szétszedve ( a figyelmetetések miatt ) a kódunk sorait megszámozva
   * minden DATA-STEP lépés után ott lesz, hogy milyen névvel jött létre az adattábla, ennek hány sora és hány oszlopa van - így könnyen ellenőrizhető, hogy a programunk tényleges nem dobál ki, illetve generál adatot fölöslegesen
   * ezeken kívül minden lépés után ( DATA-STEP, PROC-STEP ) megkapjuk, hogy az adott rész mennyi időben fut le - ez kis adathalmaz esetén nem tartalmaz sok információt, de mindenképp hasznos ha optimalizálni is akarunk
   * itt kapjuk vissza a figyelmeztetéseket, hibákat és megjegyzéseket

## Az Output ablak

  * mint már korábban említettük a Windows alapértelmezett az ha fordítás után a kimenet az Output ablakban megjelenik ( persze ha nem Windows-on dolgozunk, akkor futtatás után különböző parancsok segítségével lehet elérni a kimenetet - pl.: cat, more )
  * ha a kimenetben több fájl van, akkor ezek struktúráját meg tudjuk tekinteni a Results ablakban
  * ez azért is hasznos, mert előfordulhat, hogy a kimenetnek csak egy rész érdekel minket - ekkor könnyen lekereshető, hogy mely programrészhez melyik eredmény tartozik
  * a kimenetnek, vagy kimenet egy részének elmentése, illetve nyomtatása Windows-on értelemszerűen történik

## HTML Output

  * a legenerált táblázatok megjelenésének és megjelenítésének beállításáról lesz szó az alábbiakban
  * ahhoz hogy ezen lehetőségeket elérjük: *Tools/Options/Preferences.../Results* 
  * legfontosabb opciók: **Create Listing** ( alapértelmezett kimenet ); **Create HTML** ( legyen e HTML kimenet ); **Style** ( milyen kinézetű legyen a HTML output )
  * amennyiben bekapcsoltuk a HTML kimenetet, akkor a futtatás során a kimenet automatikusan meg fog jelenni a Result Viewer ablakban, míg az eredmények struktúrája a Results ablakban

## SAS könyvtárak

  * egy SAS könyvtár egyszerűen nem más, mint SAS adatbázisok és fájlok gyűjtőhelye - ez lehet egy szimpla mappa, vagy akár egy CD
  * habár egy ilyen könyvtár definiálása többféleképp történhet ( programon belül **LIBNAME** paranccsal ), most az interktív módot mutatjuk be
  * ehhez meg kell nyitni a korábban taglalt Explorer ablakot ezen belül pedig a Librarie ikonra kattintva az épp aktív könyvtárakat
  * itt legalább három könytár fog fogadni minket:
   * **Sashelp**: olyan információk melyek segíthetnek a munkaánk közben, továbbá minta adatbázisok
   * **Work**: adatbázisaink ideiglenes tárhelye - ez az alapértelmezett könyvtár, azaz ha létrehozunk egy adatbázist a mentési helyének beállítása nélkül, akkor a SAS automatikusan itt tárolja a munkafolyamat bezárásáig
   * **Sasuser**: itt tároljuk a SAS környezet beállításait; persze ide is lehet adatbázisokat, programokat és további fájlokat menteni
  * egy új könyvtár létrehozásának egyszerű módja, hogy az aktív könyvtárakat tartalmazó ablakban való jobb-klikk után kiválasztjuk a New opciót
  * ekkor a felugró New Library ablakban minen szükséges paraméter értelemszerűen megadható
  * ha nem akarjuk minden session megkezdése előtt definiálni ezt a könyvtárat, akkor pipáljuk az **Enable at startup** opciót a definiálás közben

## SAS Explorer

  * Az Explorer ablak nem csak új könyvtárak definiálására használható, hanem korábbiak tartalmának vizsgálatára is - például egy táblázatot leíró adatok lekérdezésére
  * az aktív könyvtárakat tartalmazó ablakban válasszuk ki a számunkra érdekes könyvtárat, ekkor a tartalma megjelenik 
  * a megfelelő táblázat ikonra kattintva felugrik a Viewtable ablak benne az általunk kiválasztott adathalmaz
  * ennek az adattáblának az adatait jobb egérgombbal az ikonjára kattintva és a *Properties* opciót választva érhetjük el
  * itt lehetőség van megnézni hány sorunk és oszlopunk van, ezek milyen tipusúak, stb. - ez persze egy programon belül a **CONTENTS** paranccsal is elérhető

## SAS rendszer opciók

  * 


