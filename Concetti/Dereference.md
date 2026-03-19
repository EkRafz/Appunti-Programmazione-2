

> [!info] Definizione
> Il **dereference** (dereferenziazione) è l'operazione di "seguire" un [[Puntatore]] per accedere all'[[Oggetto]] a cui punta. In Java il dereference avviene **automaticamente** ogni volta che si accede a un campo o un metodo di un oggetto.

---

## Esempio

```java
TNT tnt = new TNT();    // tnt contiene un puntatore
tnt.ignite();           // Java fa il dereference automaticamente:
                        // segue il puntatore → trova l'oggetto → chiama ignite()
```

In C/C++ il dereference è esplicito (`*ptr` o `ptr->`), in Java è **implicito** nella [[Dot Notation]].

---

## Vedi anche

- [[Puntatore]] — il riferimento che viene dereferenziato
- [[Aritmetica dei puntatori]] — non disponibile in Java
- [[Dot Notation]] — la sintassi che include il dereference implicito
