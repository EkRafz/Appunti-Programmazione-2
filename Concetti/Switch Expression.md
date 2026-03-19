

> [!info] Definizione
> Una **switch expression** è un costrutto Java che, a differenza dello switch statement classico, **ritorna un valore**. Usa la sintassi con `->` e deve essere **esaustiva** (coprire tutti i casi possibili).

---

## Switch Statement vs Switch Expression

| | Statement | Expression |
|---|---|---|
| Ritorna un valore? | ❌ No | ✅ Sì |
| Sintassi | `case X:` (con `break`) | `case X ->` |
| Esaustività | Non richiesta | **Obbligatoria** |

---

## Esempio con [[Enum]]

```java
private static void movePlayerEnum(Direction dir) {
    // Switch EXPRESSION: ritorna un valore, usa ->
    String dirName = switch (dir) {
        case NORTH -> "NORTH";
        case EAST  -> "EAST";
        default    -> "UP";     // necessario per esaustività
    };
    System.out.println("Moving " + dirName);
}
```

---

## Expression vs Statement

> Un'**expression** produce un **valore** (es. `2 + 3`), uno **statement** no (es. `if/else`, `for`).

---

## Vedi anche

- [[Enum]] — le switch expression sono particolarmente utili con le enum
