> [!info] Definizione
> Un **metodo astratto** e un [[Metodo]] dichiarato con `abstract` **senza corpo**. Definisce un obbligo per le sottoclassi concrete.

---

## Regola

Una classe concreta che estende una classe astratta **deve** implementare tutti i metodi astratti ereditati.

---

## Esempio

```java
public abstract class Entity {
    public abstract void attack();
}

public class Zombie extends Entity {
    @Override
    public void attack() {
        System.out.println("Bite");
    }
}
```

---

## Vedi anche

- [[Classi Astratte]]
- [[Metodo]]
