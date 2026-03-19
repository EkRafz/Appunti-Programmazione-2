

> [!info] Definizione
> Un **invariante** è una proprietà che deve essere **sempre vera** durante tutto il ciclo di vita di un [[Oggetto]]. I [[Modificatori di Visibilità]] e le keyword come [[Keyword final|`final`]] e [[Keyword static|`private`]] forniscono gli strumenti per **garantirli**.

---

## Come si ragiona sugli invarianti

Per individuare gli invarianti, ci si chiede: **c'è del comportamento che NON dovremmo permettere?**

---

## Esempio: invarianti di TNT

| Domanda | Risposta | Come si garantisce |
|---|---|---|
| Ha senso far calare il fuso senza innescarla? | **NO** | `tick()` controlla `isIgnited` |
| Si può innescare più volte? | **NO** | `ignite()` controlla se già innescata |
| Il fuso può essere negativo? | **NO** | `fuseLength` è `private`, solo `tick()` lo modifica |
| Si può farla esplodere da fuori? | **NO** | `explode()` è `private` |

```java
public class TNT {
    private int fuseLength;    // private → nessuno scrive fuseLength = -100
    private boolean isIgnited;

    public void ignite() {
        if (this.isIgnited) return;  // invariante: non si innesca 2 volte
        this.isIgnited = true;
    }

    public void tick() {
        if (this.isIgnited && this.fuseLength > 0) {
            this.fuseLength -= 1;    // invariante: decremento controllato
            if (this.fuseLength <= 0) {
                this.explode();
            }
        }
    }

    private void explode() {         // private → solo TNT decide quando
        System.out.println("BOOM!");
        this.isIgnited = false;
    }
}
```

---

## Vedi anche

- [[Incapsulamento]] — il meccanismo che garantisce gli invarianti
- [[Modificatori di Visibilità]] — `private` impedisce accessi non autorizzati
- [[Keyword final]] — impedisce modifiche dopo l'inizializzazione
