

> [!info] Definizione
> Un **campo** (o **variabile d'istanza**) è una variabile dichiarata all'interno di una [[Classe]] che rappresenta una parte dello **stato** di un [[Oggetto]]. Ogni oggetto ha la propria copia dei campi.

---

## Sintassi

```java
modificatore tipo nome = valoreDefault;
```

```java
public class Player {
    public String username;           // campo pubblico
    private int health = 20;          // campo privato con valore di default
    private boolean isPoisoned = false;
}
```

---

## Valori di default dei tipi primitivi

Se un campo non viene inizializzato esplicitamente:

| Tipo | Default |
|---|---|
| `int` | `0` |
| `boolean` | `false` |
| `double` | `0.0` |
| Oggetti / Array | `null` |

---

## Campo vs Variabile locale

| | Campo | Variabile locale |
|---|---|---|
| Dichiarato in | una [[Classe]] | un [[Metodo]] o blocco |
| Vive in | [[Heap]] (dentro l'oggetto) | [[Stack]] (nello stack frame) |
| Inizializzazione | Automatica (default) | Obbligatoria prima dell'uso |
| Accesso | `this.campo` o `oggetto.campo` | Direttamente per nome |

---

## Esempio

```java
public class TNT {
    public int fuseLength = 10;    // campo
    public boolean isIgnited;      // campo (default: false)

    public void tick() {
        int remaining = this.fuseLength;  // variabile locale
        this.fuseLength -= 1;             // accesso al campo con this
    }
}
```

---

## Vedi anche

- [[Classe]] — dove si dichiarano i campi
- [[Oggetto]] — ogni oggetto ha la propria copia dei campi
- [[Keyword this]] — per riferirsi ai campi dell'oggetto corrente
- [[Modificatori di Visibilità]] — `public`, `private`, etc.
- [[Keyword final]] — per rendere un campo costante
- [[Keyword static]] — per campi condivisi tra tutti gli oggetti
