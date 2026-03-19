

> [!info] Definizione
> I **modificatori di visibilità** (access modifiers) regolano **chi** può accedere a [[Campo|campi]], [[Metodo|metodi]] e [[Classe|classi]]. Sono lo strumento principale per realizzare l'[[Incapsulamento]].

---

## Tabella dei modificatori

| Modificatore | Classe stessa | Stesso [[Package]] | Classi figlie | Tutti |
|---|---|---|---|---|
| `private` | ✅ | ❌ | ❌ | ❌ |
| *(nulla)* — Package-Private | ✅ | ✅ | ❌ | ❌ |
| `protected` | ✅ | ✅ | ✅ | ❌ |
| `public` | ✅ | ✅ | ✅ | ✅ |

> *(nulla)* = se non scrivi nulla, il default è **Package-Private**
> `protected` → importante con l'[[Ereditarietà]]

---

## Esempio

```java
public class Player {
    public String username;          // 🟢 tutti vedono
    int fakeHealth = 10;             // 🔵 solo stesso package
    private int health = 20;         // 🔴 solo Player
    private boolean isPoisoned;      // 🔴 solo Player

    public void damage(int amount) { // 🟢 tutti chiamano
        this.health -= amount;
    }
}
```

```java
// Da un'altra classe in un ALTRO package:
Player steve = new Player();
steve.username = "Steve";     // ✅ public
// steve.fakeHealth = 100;    // ❌ package-private (package diverso!)
// steve.health = 0;          // ❌ private!
steve.damage(5);              // ✅ public
```

---

## Package-Private in azione

```java
// Witch è nello STESSO package di Player
public class Witch {
    public void fakeAttack(Player p) {
        p.fakeHealth = 0;   // ✅ package-private: stesso package!
    }
}
```

---

## Vedi anche

- [[Incapsulamento]] — il principio che i modificatori realizzano
- [[Package]] — i confini di visibilità dipendono dal package
- [[Ereditarietà]] — `protected` si capisce con l'ereditarietà
