

> [!info] Definizione
> La keyword **`final`** applicata a un [[Campo]] lo rende una **[[Costante]]**: il suo valore può essere assegnato **una sola volta** (nella dichiarazione o nel [[Costruttore]]) e non può più essere modificato.

---

## Regole

1. Un campo `final` **deve** essere inizializzato **esattamente una volta**
2. Può essere inizializzato nella dichiarazione **oppure** in **ogni** costruttore
3. Dopo l'inizializzazione, qualsiasi tentativo di scrittura causa un **errore di compilazione**

---

## Esempio: campo `final`

```java
public class FinalPlayer {
    public final String name;   // final: si assegna una sola volta

    public FinalPlayer(String name) {
        this.name = name;       // ✅ OK: prima (e unica) assegnazione
    }

    public FinalPlayer() {
        this("Steve");          // ✅ OK: delega al costruttore sopra
    }
}
```

```java
FinalPlayer fp = new FinalPlayer("Alex");
// fp.name = "Steve";  // ❌ ERRORE DI COMPILAZIONE! name è final
```

---

## `private final` nelle Enum

Combinare `private` e `final` rende i [[Campo|campi]] **immutabili e nascosti**: lo stato non cambia e non è accessibile dall'esterno.

```java
public enum ToolTier {
    DIAMOND(1561, 8.0f);

    private final int maxUses;       // nessuno lo modifica
    private final float efficiency;  // nessuno lo modifica

    ToolTier(int maxUses, float efficiency) {
        this.maxUses = maxUses;
        this.efficiency = efficiency;
    }

    public int getMaxUses() { return this.maxUses; }
}
```

---

## Vedi anche

- [[Costante]] — un valore che non cambia mai
- [[Immutabilità]] — principio di Ing. del Software legato a `final`
- [[Costruttore]] — dove si può inizializzare un campo final
- [[Modificatori di Visibilità]] — `private final` per massima protezione
