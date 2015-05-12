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



