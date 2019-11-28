class: inverse, center, middle

# Clean Code

---

class: inverse, center, middle

# Clean Code bevezetés

---

## Clean Code eredete

* Könyv: Robert C. Martin - Clean Code: A Handbook of Agile Software Craftsmanship
* További könyvek:
   * The Clean Coder
   * Clean Architecture
   * Working Effectively with Legacy Code
* Nincs egyértelmű definíciója

---

## Minőségi jellemzők

* Elegáns és hatékony
* Egyszerű, célratörő
* Könnyen olvasható és megérthető
* A célt fogalmazza meg tömören, nem rejti el
* Kevés függőség
* Teljeskörű hibakezelés
* Nem triviális jobbá tenni
* KISS
* DRY

---

## Clean Code célja

* Kód, mely egyszerű megérteni, egyszerű módosítani, egyszerű tesztelni
* Egy dolgot csinál
* Azt az egy dolgot helyesen
* Rossz kód hátrányai
    * Csökkenő teljesítmény: nehéz olvasni, megérteni, bővíteni (hiba nélkül)
    * Csökkenő motiváció
    * Teljes újraírás igénye
    * Tudni kell nemet mondani
* Megoldás: "Cserkész szabály: hagyd tisztábban a táborhelyet, mint ahogy találtad"
    * Akár apróbb refactoring műveletek
    * Ne vedd személyes ügynek

---

class: inverse, center, middle

# Nevek

---

## Nevekkel kapcsolatos ajánlások

* Tükrözze a szándékaink
    * Kerülendő: `theList`, `aList`, `object`, `anotherObject`, `employee2`
    * Egy betűs változók kizárólag rövid metódus lokális változójaként, ciklusváltozóként
    * Minél szélesebb körben használatos, annál hosszabb lehet
* Rendelkezzen jelentéssel
    * Kerüljük a töltelékszavakat (névelők, `Data`, `Manager`, `Processor`, `Info`)
    * Bűzlő név: `Util`
    * Legyen egyértelmű (hibás: `context`)
* Kiejthető
    * Kerüljük a rövidítéseket


---

## Nevekkel kapcsolatos ajánlások

* Kereshető
    * Nem szükséges a Hungarian notation
    * Kerüljük az előtagok: `_`, `p_` paraméter esetén, `m_` attribútum esetén
    * Kerüljük az interfészeknél az `I` előtagot, implementációknál a semmitmondó `Impl` vagy `Default` szavakat, megkülönböztetés alapvető funkció alapján
* Osztálynevek főnevek, metódusnevek igék
* Kerüljük a fejtörőket!
* Kerüljük a vicces neveket, szójátékokat!
* Ugyanarra a fogalomra ugyanazt a szót használjuk
    * Adott domainben elterjedt fogalmakat
    * Pl. oo paradigma esetén léteznek tervezési minták
    * Rétegekben elhelyezkedő fogalmak (`Repository`, `Service`, `Controller`, `Validator`)
    * Repository metódus prefixek (`save`, `persist`, `insert`, `merge`)

---

## Nevekkel kapcsolatos ajánlások

* Amennyiben a név magában nem értelmezhető, használjunk kontextust, előtagot (pl. `status` szó önmagában nem jelent semmit)
    * Feleslegesen ne használjuk, ha pl. úgyis egy osztályon belül vannak, ami definiálja a kontextust
    * Ne használjunk triviális, széles körben használt előtagokat (pl. alkalmazás rövidítése)
* Domain nyelve?

---

class: inverse, center, middle

# Függvények

---

## Függvényekkel kapcsolatos ajánlások

* Rövid és egyszerű
    * Alacsony cyclomatic complexity
    * Egy dolgot csináljon, helyesen
    * Egyben átlátható
* Egy függvény, egy elvonatkoztatási szint
* Olvasás felülről lefelé: alacsonyabb absztrakciós szint/hívott függvények lejjebb
* Switch - jelzés lehet az egy interfész, több implementáció alkalmazására
* Paraméterek    
    * Ne legyen `boolean`, mely a működést szabályozza (két függvény)    
    * Kevés számú, több esetén paraméter objektum
    * Változó számú paraméterlista: csak ugyanarra használjuk az egyes elemeket
    * Ne legyen mellékhatása
    * Ne legyen kimeneti paraméter, arra a visszatérési érték való    

---

## Függvényekkel kapcsolatos ajánlások

* Command and query separation (ellenpélda: Java 8 `Map` metódusok)
* Használjunk kivételeket hibakódok helyett
* Emeljük ki a try-catch blokkokat!
* Ne használjunk közös `Error` enumokat!

---

## Védekező stratégiák

* Mindig ellenőrizze a paramétereket
* Gondolj a szélsőséges értékekre! (Túl nagy, túl kicsi, `null`)
* Minél előbb jelentkezzen a hiba
* Dokumentáld az elő- és utófeltételeket!
* Ha dokumentálod, attól még nem hagyhatod el az ellenőrzést!
* Fedd le, dokumentáld automata tesztekkel
* KISS
* Jól indokolt esetekben el lehet térni a szabályoktól

---

class: inverse, center, middle

# Megjegyzések

---

## Megjegyzések

* Kód legyen olvasható, minimalizáljuk a megjegyzések számát
* Ne azt, hogy hogyan, hanem hogy miért
* `TODO` megjegyzések: folyamatosan monitorozzuk, tartsuk alacsonyan a számát
* JavaDoc? Publikus API-n.
* Figyelmeztetés a következményekre

---

## További megjegyzésekkel kapcsolatos ajánlások

* Ne ismételd a kódot!
* Könnyen szétcsúszik az implementáció és a megjegyzés
* Kötelező JavaDoc megjegyzések kikényszerítésével nem nő a kód tisztaság
* Változások listája: helye a verziókezelőben
* Blokkok lezárásánál se használjuk (behúzás, és amúgy se legyen nyíl alakú)
* Vezessünk be metódusokat, konstansokat!
* Ne használjunk sormintákat!
* Ne használjuk a saját nevünket területünk kijelöléséhez!
* Ne tegyünk megjegyzésbe utasításokat: helye a verziókezelőben
* Használhatunk külső hivatkozásokat

---

class: inverse, center, middle

# Formázások

---

## Formázások

* Nincs általánosan elfogadott, csapat egyezzen meg, és tartsa magát ahhoz
* Finom granularitás
* Az IDE segít ugrálni
* Üres sor segít az elválasztásban
    * Lehet, hogy érdemes külön metódusba szervezni
* Vertikális sorrend
* Néha a szokás fontosabb, mint a praktikum
    * Javaban előre írjuk az attribútumokat
* Közelség, távolság
    * Ugyanazon absztrakciós szinten lévők közel
    * Ugyanazon fogalommal dolgozók közel
    * Változó közel a felhasználási helyéhez
    * Egymást hívók közel

---

## Formázások

* Rövid sorok
* Ne igazítsunk egymáshoz típusdeklarációt pl.

---

class: inverse, center, middle

# Objektumok és adatszerkezetek

---

## Objektumok és adatszerkezetek

* Megkülönböztethetünk objektumokat és adatszerkezeteket
    * Objektum: encapsulation, viselkedés
        * Polimorfizmus: egyszerű újabb leszármazottat hozzáadni, nehezebb újabb működést
          a meglévő módosítása nélkül (lsd. visitor tervezési minta)
    * Adatszerkezet: csak adatot reprezentál
        * Nehezebb új adatszerkezetet felvenni, könnyebb új működést
* Tipikus példa adatszerkezetre: Data Transfer Object (DTO)
* Demeter törvénye: "csak a közvetlen barátaiddal beszélj!"
    * Vonatroncsok

---

class: inverse, center, middle

# Határok használata

---

## Határok használata

* Külső, 3rd party kódok elrejtése, beburkolása
    * Akár `java.util.Collection` is, hiszen módosulhat, vagy mi akarunk más implementációt választani
    * Vonatroncs: `School.getTrainers().add("John Doe")`
    * Tanuló tesztek alkalmazása

---

class: inverse, center, middle

# Kivételkezelés

---

# Kivételkezelés

* Ne használjunk hibakódokat!
* Használjunk környezetet, kivételben szerepeljenek a releváns adatok!
* Használjunk unchecked kivételeket!
* A kivételeket is a hívó szemszögéből definiáljuk (publikus API része)
* Tekintsünk rá, mint a fő folyamattól független ág
* Amennyiben változtatja az üzleti logikát, fedjük el egy metódusban, és használjunk feltételt
* Burkoljuk be a 3rd party kivételeket!
* Ne térjünk vissza `null` értékkel speciális értékek jelzésére! (`Optional`, empty object)

---

class: inverse, center, middle

# Osztályok

---

## Osztályok szervezése

* Egységbe zárás
* Finom granularitás
* Single responsibility (SRP)
    * Legyen kicsi, de ne a sorok száma alapján
    * Ha a leírásában _és_, _de_, _vagy_ szavakat használsz, jelezhet valamit
* Cohesion: kis számú attribútum, és minden metódus legalább egyet használ
    * Minél többet használ, annál nagyobb a cohesion
* Együtt változókat egy osztályba, külön változókat külön osztályba
* Interfészekkel leválasztani az implementációt, dependency inversion (DIP)

---

class: inverse, center, middle

# Rendszerek

---

## Rendszerek

* Komponensek közötti függőségek
* Legyenek laza kapcsolatok
* Egyik ne példányosítsa a másikat (erős kapcsolat)
* Abstract factory, factory method (felelősségi kör - példányosítás)
* Dependency injection
* Folyamatosan változik: felelősségi körök szétválasztása
* Cross cutting concerns
* AOP
* Döntések elhalasztása az utolsó lehetséges pillanatig: döntés meghozatala a tudás birtokában
* DSL fontossága

---

class: inverse, center, middle

# Fejlődés

---

## Fejlődés

* Induljunk egy egyszerű felépítéssel, és fejlesszük, ahogy többet tudunk
* Hogyan maradjunk egyszerűek?
* Kent Beck: Simple Design
    * Legyenek unit tesztek (funkcionális helyesség, csak jól felépített kód unit tesztelhető)
    * Ne tartalmazzon kódismétlést (unit tesztek miatt refaktorálható)
    * Kifejezze a fejlesztő szándékát
    * Osztályok és metódusok számának alacsonyan tartása

---

class: inverse, center, middle

# Statikus kódellenőrzés és Code review

---

## Kódminőség ellenőrzése <br /> és fenntartása

* Clean Code elvek betartásának automatizált ellenőrzése a forráskódon
* Bugok, kódolási konvenciók felfedezése
* Funkcionális ellenőrzésre nem alkalmas
* Performancia ellenőrzésre korlátozottan alkalmas

---

## Statikus kódellenőrzés

* Automatizált ellenőrzés
* Minnél hamarabb kijön a hiba, annál olcsóbban javítható
* Teljes kód átnézhető
* Folyamatosan futtatható (IDE, build, CI/CD)
* `@SuppressWarnings`
* Hisztorikusan figyelhető
* Technical dept

---

## Code review további előnyei

* Elegáns megoldás bemutatása, feedback, elismerés
* Tudásátadás, fejlődési lehetőség

---

## Code review a módszertanban

* Legyen a scope előre rögzített
* Scope: teljes változás vagy csak problémásabb részek?
* Bővítsük a saját konvencióink
* Legyen standardizált a folyamat és az eredménye

---

## Tanácsok

* Ne legyen offenzív, személyeskedő
* Koncentráljunk a célokra (funkcionális)
* Kérdezzünk
    * Tiszta-e a cél, a megoldásra összpontosít?
    * Megfelel-e a Clean Code-nak és a saját konvencióinknak?
    * Le van-e tesztekkel fedve?
    * Minden ág kezelve lett-e?
    * Nem lenne-e egyszerűbb megoldás, nem lett-e túl magas szintű absztrakció bevezetve? (YAGNI)
    * Tudtál-e arról, hogy már van ilyen belső/3rd party megoldás?
    * Performancia szempontjából megfelelő-e?
    * Megfelel a nem-funkcionális követelményeknek? (Biztonság, naplózás, stb.)
* Ne mondjunk véleményt
* Objektív legyen, szakmailag alátámasztott

---

## Code review formái

* Pair programming
* Ad-hoc véleménykérés
* Push előtt
* Pull request
* Pull után
* Csoportos

---

class: inverse, center, middle

# Code smells

---

## Code smells

* Jel, hogy refaktorálásra van szükség
* Bármi, ami megtöri a Clean Code elveket

---

## Megjegyzések

* C1: Nem megfelelő helyen lévő információ (Inappropriate information)
    * Vagy váltózó- és metódusnevekben, verziókezelőben
* C2: Elavult megjegyzés (Obsolete comment)
* C3: Felesleges megjegyzés (Redundant comment)
* C4: Rosszul megírt megjegyzés (Poorly written comment)
* C5: Megjegyzésbe tett kód (Commented out code)

---

## Környezet

* E1: Egynél több lépést igénylő build (Build requires more than one step)
* E2: Egynél több lépést igénylő tesztek (Tests require more than one step)

---

## Függvények

* F1: Túl sok paraméter (Too Many Arguments)
* F2: Kimeneti paraméterek (Output Arguments)
* F3: Jelzőparaméterek (Flag Arguments)
* F4: Nem hívott függvény (Dead Function)

---

## Általános szagok

* G1: Több nyelv egyetlen forrásállományban (Multiple Languages in One Source File)
* G2: Nyilvánvaló működés implementálásának mellőzése (Obvious Behavior Is Unimplemented)
    * Ha nem implementálod a névből kikövetkeztethető működést, elvesztik a bizalmat a hívók
    * "Legkisebb meglepetés elve"
* G3: Helytelen viselkedés határeseteknél (Incorrect Behavior at the Boundaries)
* G4: Szabályok megsértése (Overridden Safeties)
    * Pl. `@SuppressWarnings` használata
* G5: Kódismétlés (Duplication)
* G6: Rossz absztrakciós szinten lévő kód (Code at Wrong Level of Abstraction)
* G7: Leszármazottaktól függő ősosztályok (Base Classes Depending on Their Derivatives)
* G8: Túl sok információ (Too Much Information)
    * Túl nagy API

---

## Általános szagok

* G9: Nem használt kód (Dead Code)
* G10: Túl nagy függőleges távolság (Vertical Separation)
* G11: Következetlenség (Inconsistency)
* G12: Lomok (Clutter)
    * Nem használt kódrészletek, megjegyzések
* G13: Mesterséges csatolás (Artificial Coupling)
    * Nem összetartozó dolgok függőségbe kerülnek (pl. enumok osztályon belül)
* G14: Máshol lévő metódusok túlzott használata (Feature Envy)
    * Metódus túl sokat használja másik osztály metódusát: lehet, hogy inkább abban lenne a helye
* G15: Több viselkedés, melyek közül paraméter választ (Selector Arguments)
* G16: Rejtett szándék (Obscured Intent)
* G17: Rossz helyre tett felelősség (Misplaced Responsibility)
* G18: Rosszul választott statikus metódusok (Inappropriate Static)

---

## Általános szagok

* G19: Köztes, magyarázó változók hiánya (Use Explanatory Variables)
* G20: Nem beszédes függvénynév (Function Names Should Say What They Do)
* G21: Nem értjük meg az algoritmust (Understand the Algorithm)
    * Tippeljük a feltételekben a logikai kifejezést
* G22: Logikai függőség fizikai függőség nélkül (Make Logical Dependencies Physical)
* G23: Ugyanazon feltétel alapján többször használt elágazások (Prefer Polymorphism to If/Else or Switch/Case)
* G24: Konvenciók figyelmen kívül hagyása (Follow Standard Conventions)
* G25: Mágikus számok (Replace Magic Numbers with Named Constants)
* G26: Pontatlan, elnagyolt kód (Be Precise)
* G27: Konvenciókhoz való túlzott ragaszkodás (Structure over Convention)
* G28: Bonyolult feltételek feltételes szerkezetekben (Encapsulate Conditionals)

---

## Általános szagok

* G29: Negatív feltételes szerkezetek (Avoid Negative Conditionals)
* G30: Egy metódus több feladatot végez (Functions Should Do One Thing)
* G31: Rejtett függőségek (Enforce Temporal Couplings)
    * Pl. metódusokat bizonyos sorrendben kell meghívni, mert beállít egy attribútumot (adja át paraméterként/visszatérési értékként)
* G32: Önkényes döntések (Don’t Be Arbitrary)
    * Pl. belső osztály használata, mikor nem belső is lehetne
* G33: Határértékek ismétlése (Encapsulate Boundary Conditions)
    * Pl. több helyen használunk egy kifejezést arra, hogy meddig menjen a ciklus
* G34: Egy függvény több absztrakciós szinttel (Functions Should Descend Only One Level of Abstraction)
* G35: Globális paraméter alacsony absztrakciós szinten (Keep Configurable Data at High Levels)
* G36: Tranzitív navigáció (Avoid Transitive Navigation)
    * Demeter törvényének megsértése

---

## Java

* J1: Sok import ugyanazon csomagból (Avoid Long Import Lists by Using Wildcards)
* J2: Állandók az öröklődési hierarchia tetején (Don’t Inherit Constants)
    * Inkább statikus import
* J3: Állandók interfészekbe (Constants versus Enums)
    * Használjunk enumokat

---

## Nevek

* N1: Nem leíró nevek (Choose Descriptive Names)
* N2: Név nem felel meg az adott absztrakciós szintnek (Choose Names at the Appropriate Level of Abstraction)
* N3: Nem a szabványos név használata (Use Standard Nomenclature Where Possible)
    * Ugyanarra több név
* N4: Nem egyértelmű név (Choose Unambiguous Names)
* N5: Nincs összhangban a hatókör és a név hossza (Use Long Names for Long Scopes)
* N6: Típuskódolás a nevekben (Avoid Encodings)
    * Pl. Hungarian notation, interfészek
* N7: Rejtett funkció (Names Should Describe Side-Effects)
    * A név nem írja le, hogy plusz dolgok is történnek

---

## Tesztek

* T1: Kevés teszt (Insufficient Tests)
* T2: Nincs lefedettség (Use a Coverage Tool!)
* T3: Nincs triviális esetre teszteset (Don’t Skip Trivial Tests)
* T4: Nem tiszta követelményeknek megfelelés (An Ignored Test Is a Question about an Ambiguity)
    * Jelezzük nem futtatott tesztesettel
* T5: Határesetekre nincs teszt (Test Boundary Conditions)
* T6: Kevés teszteset azon területen, ahol sok hiba jelentkezik (Exhaustively Test Near Bugs)
* T7: Figyelmen kívül hagyjuk a hibák mintázatait (Patterns of Failure Are Revealing)
    * Ha pl. negatív paraméterrel elbukik két metódushívás, lehet, hogy a többi metódus is ugyanúgy fog viselkedni
* T8: Figyelmen kívül hagyjuk a lefedettségi mintázatokat (Test Coverage Patterns Can Be Revealing)
    * Lásd előző példa
* T9: Lassú tesztek (Tests Should Be Fast)
