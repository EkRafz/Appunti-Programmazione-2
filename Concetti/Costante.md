

> [!info] Definizione
> Una **costante** è un valore che, una volta assegnato, **non può più essere modificato**. In Java si realizza con la keyword [[Keyword final|`final`]] (e spesso combinato con [[Keyword static|`static`]] per costanti globali).

---

## Convenzioni

Le costanti globali (`static final`) si scrivono in **UPPER_SNAKE_CASE**:

```java
public class TNT {
    private static final double EXPLOSION_POWER = 100;
    private static int DEFAULT_FUSE_LENGTH = 80;
}
```

---

## Esempio

```java
public class GameConstants {
    public static final int MAX_STACK_SIZE = 64;

    // MAX_STACK_SIZE = 128;  // ❌ ERRORE! è final
}
```

---

## Vedi anche

- [[Keyword final]] — la keyword per dichiarare costanti
- [[Keyword static]] — `static final` per costanti di classe
- [[Immutabilità]] — principio connesso
