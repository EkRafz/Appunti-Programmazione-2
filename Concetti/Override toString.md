

> [!info] Definizione
> L'**override di `toString()`** permette di personalizzare la rappresentazione testuale di un [[Oggetto]] quando viene stampato o concatenato a una stringa.

---

## Come funziona

Ogni classe in Java eredita il metodo `toString()` da `Object`. Il default stampa il nome della classe e l'indirizzo in memoria. Con l'override si può fornire una rappresentazione **leggibile**.

---

## Esempio

```java
public enum ToolTier {
    WOOD(59, 2.0f),
    DIAMOND(1561, 8.0f);

    private final int maxUses;
    private final float efficiency;

    ToolTier(int maxUses, float efficiency) {
        this.maxUses = maxUses;
        this.efficiency = efficiency;
    }

    @Override
    public String toString() {
        return "Material: " + this.name() +
               "\nDurability: " + this.maxUses +
               "\nSpeed: " + this.efficiency;
    }
}
```

```java
System.out.println(ToolTier.DIAMOND);
// Stampa:
// Material: DIAMOND
// Durability: 1561
// Speed: 8.0
```

---

## Vedi anche

- [[Metodo]] — `toString()` è un metodo
- [[Oggetto]] — ogni oggetto ha un `toString()`
- [[Ereditarietà]] — `toString()` viene ereditato da `Object`
