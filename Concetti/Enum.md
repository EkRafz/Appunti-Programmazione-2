

> [!info] Definizione
> Una **enum** è un tipo speciale in Java con un numero **fisso** di valori possibili (varianti), scritti per convenzione in `UPPER_CASE`. In Java le enum sono **classi vere e proprie**: possono avere [[Campo|campi]], [[Metodo|metodi]] e [[Costruttore|costruttori]].

---

## Caratteristiche

- Le varianti sono **oggetti singleton** (esiste una sola istanza per variante)
- Il [[Costruttore]] è **implicitamente privato** → non si possono aggiungere varianti dall'esterno
- Risolvono il problema dei [[Magic Numbers]]
- Si analizzano tipicamente con [[Switch Expression|`switch`]]

---

## Enum semplice

```java
public enum Direction {
    NORTH,
    EAST,
    SOUTH,
    WEST,
    UP,
    DOWN
}
```

```java
Direction dir = Direction.NORTH;    // ✅ solo valori validi
// Direction.PIPPO → ❌ ERRORE DI COMPILAZIONE!
```

---

## Enum con campi e metodi

```java
public enum ToolTier {
    WOOD(59, 2.0f),
    STONE(131, 4.0f),
    IRON(250, 6.0f),
    DIAMOND(1561, 8.0f),
    GOLD(32, 12.0f);

    private final int maxUses;
    private final float efficiency;

    // Costruttore: implicitamente privato
    ToolTier(int maxUses, float efficiency) {
        this.maxUses = maxUses;
        this.efficiency = efficiency;
    }

    public int getMaxUses() { return this.maxUses; }
    public float getEfficiency() { return this.efficiency; }
}
```

```java
ToolTier tier = ToolTier.DIAMOND;
System.out.println(tier.getMaxUses());      // 1561
System.out.println(tier.getEfficiency());   // 8.0
```

---

## Attenzione: le varianti sono singleton!

```java
ToolTier a = ToolTier.GOLD;
ToolTier b = ToolTier.GOLD;
// a e b puntano allo STESSO oggetto!
System.out.println(a == b);  // true
```

---

## Vedi anche

- [[Magic Numbers]] — il problema che le enum risolvono
- [[Switch Expression]] — come analizzare le varianti
- [[Keyword final]] — `private final` per campi enum immutabili
- [[Singleton Pattern]] — le varianti sono singleton
