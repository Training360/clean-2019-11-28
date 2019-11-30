class: inverse, center, middle

.training360-logo[![Training360](resources/training360-logo.svg)]
# Tervezési minták

---

## Tematika

* Tervezési minták háttere
* Tervezési minták jellemzői
* Létrehozási minták
* Viselkedési minták
* Szerkezeti minták

---

## Források

* Erich Gamma, Richard Helm, Ralph Johnson és John Vlissides: Design Patterns: Elements of Reusable Object-Oriented Software (Addison-Wesley Professional; 1 edition (November 10, 1994))
* Eric Freeman,‎ Bert Bates,‎ Kathy Sierra,‎ Elisabeth Robson:  Head First Design Patterns: A Brain-Friendly Guide O'Reilly Media; 1st edition (October 2004)
* https://stackoverflow.com/questions/1673841/examples-of-gof-design-patterns-in-javas-core-libraries

---

class: inverse, center, middle

.training360-logo[![Training360](resources/training360-logo.svg)]
Lecke
## Tervezési minták háttere

---

## OO háttér

* Négy oo alapelv: *A-PIE* (Abstraction, Polymorphism, Inheritance, Encapsulation)
* Objektumorientált alapelvek, high cohesion, low coupling
* Single responsibility, legkisebb felelősségi kör
* Együtt változó részek egységbe zárása, külön változó részek elválasztása
* Programozzunk interfészekkel
* Delegálás

---

## Kompozíció használata az öröklődés helyett

* Plusz viselkedés bevezetésére
* Az öröklődés statikus, futás időben nem cserélhető
* Több programozási nyelven az öröklődés egyszeres
* Kompozíció, és főleg interfészek használatával cserélhető
* Kompozíció lazább kapcsolat, az ősosztály viszont látható a leszármazottnak
* is-a kapcsolat helyett has-a kapcsolat
* Tesztelhető, test double-ök alkalmazásával
* Könnyebb kód újrafelhasználás
* Delegáció plusz kóddal jár

---

## Kompozíció használata az öröklődés helyett - Döntés alapja

* is-a kapcsolat?
* Tényleg bővítésről van szó?
* Ha csak a polimorfizmus miatt kell, interfészeket kell használni

---

## Tervezési tanácsok

* Implementáció elrejtése
* Minimális interfész
* Interfész iteratív fejlesztése
* Design by Contract
* Újrafelhasználhatóság vs. YAGNI

---

## Tervezési tanácsok

* Kiterjeszthetőség
* KISS
* DRY
* Tesztelés az interfészen keresztül
* Demeter törvénye ("csak a közvetlen barátaiddal beszélgess")

---

## S.O.L.I.D. elvek

* Szülőatyja Robert C. Martin, aka. Uncle Bob
* Single Responsibility Principle (SRP): felelősségi kör
* Open/Closed Principle (OCP): nyílt a kiterjesztésre, de zárt a módosításra

---

## S.O.L.I.D. elvek

* Liskov substitution principle (LSP): leszármazott átveheti a szülő szerepét, anélkül, hogy a működés megváltozna
* Interface segregation principle (ISP): a hívó csak azon metódusokról tudjon, amit használ is. Megoldás az interfészt több kisebbre bontani.
* Dependency inversion principle (DIP): függőség <br /> interfészre, csak deklarálja a függőségeket

---

## Inversion of control, AOP

* Keretrendszer hívja a kódot (tipikusan konténer hívja a komponenseket)
* Hollywood Principle: "Ne hívj, majd mi hívunk."
* Gyakran összekapcsolódik a dependency injectionnel
* Aspect Oriented Programming (AOP)

