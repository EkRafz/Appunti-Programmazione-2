

> [!info] Definizione
> La keyword **`this`** è un riferimento all'**[[Oggetto]] corrente**: l'istanza su cui è stato invocato il [[Metodo]] o che si sta creando nel [[Costruttore]].

---

## Usi principali

| Contesto | Significato | Esempio |
|---|---|---|
| In un **metodo** | L'oggetto su cui è chiamato il metodo | `this.health -= amount;` |
| In un **costruttore** | L'oggetto che si sta creando | `this.name = name;` |
| **`this()`** | Chiama un altro costruttore della stessa classe | `this("Steve");` |

---

## Disambiguazione parametro/campo

```java
public class Player {
    private String name;

    public Player(String name) {
        // "name" (parametro) nasconde il campo "name"
        // this.name si riferisce al CAMPO dell'oggetto
        this.name = name;
    }
}
```

---

## Constructor Chaining con `this()`

```java
public class FinalPlayer {
    public final String name;

    public FinalPlayer(String name) {
        this.name = name;
    }

    public FinalPlayer() {
        this("Steve");   // chiama FinalPlayer(String)
    }
}
```

---

## Vedi anche

- [[Metodo]] — `this` si riferisce all'oggetto su cui è chiamato
- [[Costruttore]] — `this` si riferisce all'oggetto in fase di creazione
- [[Campo]] — `this.campo` accede ai campi dell'oggetto corrente
