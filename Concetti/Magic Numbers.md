# (Anti-pattern)

> [!info] Definizione
> I **Magic Numbers** sono valori numerici usati direttamente nel codice per rappresentare categorie o costanti, senza un nome che ne spieghi il significato. È un **anti-pattern** perché il compilatore non può verificare la correttezza dei valori.

---

## Problema

```java
// ❌ CON MAGIC NUMBERS
movePlayer(0);     // Cosa significa 0? North? East?
movePlayer(99);    // 99 non è una direzione! Ma COMPILA!
```

I bug vengono scoperti solo a **runtime** → difficili da trovare.

---

## Soluzione: usare [[Enum]]

```java
// ✅ CON ENUMS
movePlayer(Direction.NORTH);    // chiaro e leggibile
movePlayer(Direction.PIPPO);    // ❌ ERRORE DI COMPILAZIONE!
```

I bug vengono scoperti a **compile time** → il compilatore ti avvisa subito.

---

## Vedi anche

- [[Enum]] — la soluzione ai magic numbers
- [[Costante]] — dare un nome ai valori
