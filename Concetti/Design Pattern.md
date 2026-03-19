

> [!info] Definizione
> I **Design Pattern** sono soluzioni standard e riutilizzabili a **problemi comuni** nell'Ingegneria del Software. Racchiudono in una singola metodologia le best practices per risolvere problemi ricorrenti di progettazione.

---

## Caratteristiche

- Non sono codice pronto, ma **schemi concettuali** da adattare
- Hanno un **nome riconoscibile** (Singleton, Factory Method, Observer...)
- Sono **fondanti** nel corso di Programmazione 2 e presenti nei temi d'esame

---

## Pattern visti nel corso

| Pattern | Problema risolto | Keyword usate |
|---|---|---|
| [[Singleton Pattern]] | Garantire **una sola istanza** di una classe | `private static`, costruttore `private` |
| [[Factory Method Pattern]] | Raggruppare la **logica di costruzione** di oggetti complessi | `static`, costruttore package-private |

---

## Esempio: Singleton

```java
public class DragonEgg {
    private static DragonEgg THE_INSTANCE = new DragonEgg();
    private DragonEgg() {}
    public static DragonEgg getInstance() {
        return THE_INSTANCE;
    }
}
```

---

## Vedi anche

- [[Singleton Pattern]] — una sola istanza di una classe
- [[Factory Method Pattern]] — metodi per creare oggetti complessi
