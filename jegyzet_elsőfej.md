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
 * 
