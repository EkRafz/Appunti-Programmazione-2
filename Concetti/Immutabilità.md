

> [!info] Definizione
> L'**immutabilità** è un principio di Ingegneria del Software secondo cui un dato, una volta creato, **non può essere modificato**. In Java si realizza con la keyword [[Keyword final|`final`]].

---

## Perché è importante

La **mutazione** (permettere che i dati cambino) è una delle maggiori fonti di **bug**:
- Se una variabile cambia valore inaspettatamente, il comportamento diventa **imprevedibile**
- Con `final`, possiamo fidarci che lo stato **non cambierà** — né per un errore del programmatore, né per un attacco

---

## Esempio

```java
public enum ToolTier {
    DIAMOND(1561, 8.0f);

    private final int maxUses;       // immutabile
    private final float efficiency;  // immutabile

    ToolTier(int maxUses, float efficiency) {
        this.maxUses = maxUses;
        this.efficiency = efficiency;
    }
}
```

```java
// Il Diamante avrà SEMPRE maxUses=1561 e efficiency=8.0
// Nessun codice può (anche accidentalmente) violare questa proprietà
```

---

## Vedi anche

- [[Keyword final]] — lo strumento per rendere immutabile un campo
- [[Invariante]] — l'immutabilità aiuta a garantire gli invarianti
- [[Costante]] — un valore immutabile
