

> [!info] Definizione
> Il **Singleton Pattern** è un [[Design Pattern]] che garantisce che di una [[Classe]] esista **una sola istanza** in tutto il programma, e fornisce un punto di accesso globale ad essa.

---

## I 3 passi del Singleton

1. **Campo `private static`** → salva la singola istanza
2. **[[Costruttore]] `private`** → nessuno può fare `new` dall'esterno
3. **Getter `public static`** → l'unico modo per ottenere l'istanza

---

## Esempio: DragonEgg

```java
public class DragonEgg {
    // 1. Singola istanza, creata al caricamento della classe
    private static DragonEgg THE_INSTANCE = new DragonEgg();

    // 2. Costruttore PRIVATE: nessuno può chiamarlo dall'esterno
    private DragonEgg() {}

    // 3. Getter public static: l'unico modo per ottenere l'oggetto
    public static DragonEgg getInstance() {
        return THE_INSTANCE;
    }

    // L'oggetto si usa normalmente
    public void teleport() {
        System.out.println("Vwoop! The Dragon Egg teleported.");
    }
}
```

```java
DragonEgg egg1 = DragonEgg.getInstance();
DragonEgg egg2 = DragonEgg.getInstance();
System.out.println(egg1 == egg2);  // true — è lo STESSO oggetto!
```

---

## Quando usarlo

- Risorse **uniche** nel programma (settings, connessione al DB, Dragon Egg nel gioco)
- Quando servono **dati condivisi** globalmente con accesso controllato

---

## Vedi anche

- [[Design Pattern]] — la famiglia di soluzioni a cui appartiene
- [[Keyword static]] — usata per il campo e il getter
- [[Costruttore]] — reso `private` per impedire creazione esterna
