

> [!info] Definizione
> La **dot notation** (notazione a punto) è la sintassi usata in Java per accedere ai [[Campo|campi]] e invocare i [[Metodo|metodi]] di un [[Oggetto]]: `oggetto.membro`.

---

## Sintassi

```java
oggetto.campo            // accesso a un campo
oggetto.metodo(args)     // invocazione di un metodo
```

La differenza tra campo e metodo si nota dalle **parentesi**: `tnt.fuseLength` (campo) vs `tnt.ignite()` (metodo).

---

## Esempio

```java
TNT tnt = new TNT();
tnt.fuseLength = 10;     // accesso al campo
tnt.ignite();            // invocazione del metodo
```

Per i membri [[Keyword static|`static`]], si usa il **nome della classe**:

```java
GameConstants.MAX_STACK_SIZE      // campo static
GameConstants.printMOTD()         // metodo static
```

---

## Vedi anche

- [[Campo]] — si accede con `oggetto.campo`
- [[Metodo]] — si invoca con `oggetto.metodo()`
- [[Keyword static]] — `Classe.membro` per accesso a static
