> [!info] Definizione
> In Java, un **metodo `default`** in una interfaccia ha una **implementazione** fornita direttamente nell'interfaccia.

---

## Perche serve

- Permette di **evolvere** un'interfaccia senza rompere le classi esistenti
- Avvicina le interfacce al concetto di **[[Traits]]** (comportamento condiviso)

---

## Esempio

```java
public interface Boss {
    default int getPhase() {
        return 1;
    }
}
```

---

## Vedi anche

- [[interfaccia]]
- [[Traits]]
