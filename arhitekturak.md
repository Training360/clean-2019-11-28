class: inverse, center, middle

# Architektúrák

---

class: inverse, center, middle

# Architektúra fogalma

---

## Mi az az architektúra?

* Nincsenek egzakt definíciók
* Elosztott rendszerek megjelenésével
* Szoftverrendszer magasszintű struktúrája
* És ennek a dokumentálása
* Kommunikáció alapja
* Komponensek, komponensek közötti kapcsolatok, együttműködések
* Döntések és döntés okainak dokumentálása

---

## Architektúra

> "Mikor például az architektúrákról beszélünk, erről hajlamosak vagyunk 
> megfeledkezni: ahogy az épületek szerkezete sem csak azért van, hogy az egy 
> helyben álljon, hanem hogy emberek éljenek és dolgozzanak bennük, úgy a 
> szoftverarchitektúrák sem csak a technikai döntések halmazai, hanem 
> emberek együttműködésének színhelyei."

\- Kevlin Henney

---

## Architektúra által <br /> kiszolgált igények

* Nem funkcionális követelmények
	* Futtatókörnyezet
	* Teljesítmény
	* Üzemeltethetőség
	* Magas rendelkezésre állás, hibatűrés
	* Skálázhatóság, méretezhetőség

---

## Component-based software engineering

* Dekompozíció - komponensekre bontás
* Separation of Concerns - külön feladat, külön komponens
* Single Responsibility - egy jól meghatározott feladat
* Loose coupling - laza kapcsolat
* Valamilyen környezetben futnak (pl. konténer)
* Környezet biztosítja az életciklusukat
* Környezet biztosítja a kapcsolatokat, ezáltal magukban való tesztelhetőségüket
* API-val rendelkeznek, IDL-lel (Interface Definition Language) írható le
* Különböző absztrakciós szinteken megfogalmazott komponensek

---

## Nem-funkcionális <br /> követelmények

* Milyen legyen a rendszer

---

## Nem-funkcinális <br /> követelmények <br />  csoportosítása

* Use cases, operation
* Maintenance
* Development
* Deployment

---

## Minőségi követelmények 1.

* Performance: gyors kiszolgálás
* Availability: rendelkezésre állás, időnek hány százalékában
* Scalability: lehetőség a megnövekedett igény kiszolgálására
* Reliability: képesség az alkalmazás integritásának és konzisztenciájának
  megőrzésére (pl. mainframe kontra PC)
* Manageability: működés közbeni üzemeltethetőség
* Flexibility: változásokra történő érzékenység (pl. standard API-k
  elrejtik az implementációs különbségeket, driverek)
* Capacity: egységnyi idő alatt történő kiszolgálások
* Extensibility: funkcionális bővíthetőség

---

## Minőségi követelmények 2.

* Validity: az adott problémát oldja meg
* Reuseability: komponensek újra felhasználhatósága
* Security: biztonság
* Throughput: áteresztőképesség, művelet/idő
* Useability: felhasználók milyen könnyen veszik használatba
* Serviceability: hiba utáni helyreállítás vagy frissítés erőforrásigénye
* Testability: tesztelhetőség
* Realizatility: mennyi erőfeszítéssel lehet rendszerbe állítani
* Planability: mennyire tervezhető erőforrásilag
* Maintainability: tervezési hiányosság felfedezésének és javításának
  lehetősége
* Portability: különböző infrastruktúrára költöztetés lehetősége

---

## Nagyvállalati <br /> alkalmazással szemben támasztott követelmények

* Perzisztencia
* Többszálúság
* Tranzakció-kezelés
* Távoli elérés
* Névszolgáltatás
* Skálázhatóság
* Magas rendelkezésre állás
* Aszinkron üzenetkezelés
* Biztonság
* Monitorozás és beavatkozás

---

## Architecture decision log

* Döntés: szoftver tervezési választás, mely egy követelményt elégít ki
* Döntések rögzítése
* Döntés környezete, felmerült kérdések, válasz, és következményei
* Döntések elnapolásának az elve (további információkhoz való hozzájutásáig nem napolható-e el)

---

## Irányelvek

* KISS
* YAGNI
* DRY

---

## Architektúra <br /> dokumentáció

* Alapja az architecture decision log
* Több diagramm, pl. component diagram
* Hossza ne legyen több, mint 4-5 A4 oldal

---

class: inverse, center, middle

# Alkalmazás felépítése

---

## Absztrakciós szintek

* Alkalmazás
* Modul
* Unit: osztályok

---

## Use-reuse paradoxon

![Use-reuse paradoxon](http://www.jtechlog.hu/artifacts/posts/2015-08-27-modularizacio/UseReuseParadox.jpg)

---

## Alkalmazás környezete

* Futtatókörnyezet (operációs rendszer, konténer)
* Adatbázis
* Más rendszerek

---

## Rétegelt architektúrák

* Rétegek
  * Felsőbb réteg csak az alatta lévő réteg szolgáltatásait használhatja
  * Csak a közvetlen alatta lévő réteg szolgáltatásait
  * API-n keresztül
* Rétegek
  * Perzisztens réteg
  * Üzleti logika réteg
  * Prezentációs réteg
  * Integrációs réteg

---

## Modul

* Újrafelhasználhatóság közbülső szintje
* Modulok meghatározása tipikusan a következők alapján
    * Üzleti funkciók
    * Rétegek
    
---

## Unit

* Osztályok és interfészek
* OOP fogalmak
* Clean code
* Refactoring

---

class: inverse, center, middle

# Adatbázis

---

## Adatbázis függetlenség

* Eltérő ügyféligények - különböző ügyfelek, különböző adatbázison akarják futtatni
* Tesztelésből adódó követelmények
* Standardok használata
    * Adatbázisspecifikus előnyök kihasználása
    * Nem írunk elágazásokat - interfész, különböző implementációkkal

---

## Adatbázis

* Adatok perzisztenciájára
* Struktúrált tárolás
* Megközelítési módok
    * Egyrétegű
    * Többrétegű (view/stored procedure réteg)
* Adatbázis fontossága
    
---

## Adatmozgatás adatbázis és alkalmazás között

* Adatok mozgatása az adatbázis és alkalmazás között erőforrásigényes
* Végezze az adatbázis azt, ami a feladata
    * Join
    * Aggregálás

---

## Megszorítások

* Adatintegritás
* Véd az alkalmazás programozói hibáitól

---

## Connection pool

* Adatbázissal való kapcsolatfelvétel erőforrásigényes
* Módosított adatbázis objektumok, validation query

---

## Idősorok

* Kezelése relációs adatbázisban körülményes
* Harmadik dimenzió bevezetése
* Mérlegelendő:
    * Egy tábla, több tábla
    * Plusz mezők, érvényesség, indexelés
    * Szülő-gyermek táblák esetén

---

## Auditálás

* Ki és mikor módosította
* Miről mire
* Adatbázis szinten? (Trigger)

---

## Fa ábrázolása <br /> adatbázisban

* Relációs algebra nem alkalmas rá
* Adatbázisfüggő megközelítések
* Nested tree
    * Lekérdezéskor gyors
    * Módosításkor erőforrásigényes
    
---
    
## Nested tree
    
![Nested tree](http://www.jtechlog.hu/artifacts/posts/2009-08-12-fa-abrazolasa-adatbazisban/nested_1_b.png)

---

## Fájltárolás

* Tranzakciókezelés
* Mentés
* Alternatív megoldás: fájlrendszer
    * Hash/könyvtárstruktúra
* Mérés!
* Célmegoldás

---

## Adatbázis séma verziózás

* Adatbázis séma létrehozása (táblák, stb.)
* Változások megadása
* Metadata table alapján

---

## Elvárások

* SQL/XML leírás
* Platform függetlenség
* Lightweight
* Visszaállás korábbi verzióra
* Indítás paranccssorból, alkalmazásból
* Cluster támogatás
* Placeholder támogatás
* Modularizáció
* Több séma támogatása

