

> [!info] Definizione
> Un **metodo** è un blocco di codice che definisce il **comportamento** di un [[Oggetto]]. Si invoca su un'istanza con la [[Dot Notation]]: `oggetto.metodo(parametri)`.

---

## Caratteristiche

- Appartiene a una [[Classe]] e si invoca su un [[Oggetto]]
- Ha accesso a [[Keyword this|`this`]] (l'oggetto su cui è chiamato)
- Ha una [[Firma di un metodo|firma]]: nome + tipi dei parametri + tipo di ritorno
- Si distingue da un [[Campo]] per la presenza delle **parentesi**: `tnt.ignite()` vs `tnt.fuseLength`

---

## Metodo vs Funzione

| | Metodo | [[Funzione]] |
|---|---|---|
| Si chiama su | un oggetto | nulla (standalone) |
| Accesso a `this` | ✅ Sì | ❌ No |
| Esempio | `tnt.ignite()` | `Math.sqrt(4)` |

> In Java, i metodi [[Keyword static|`static`]] sono concettualmente delle funzioni.

---

## Esempio

```java
public class TNT {
    private int fuseLength = 10;
    private boolean isIgnited;

    // Metodo: definisce comportamento → innesca la TNT
    public void ignite() {
        if (this.isIgnited) {
            System.out.println("Already burning!");
            return;
        }
        this.isIgnited = true;
    }

    // Metodo con parametro e valore di ritorno
    public int getFuseLength() {
        return this.fuseLength;
    }
}
```

```java
TNT tnt = new TNT();
tnt.ignite();                          // invocazione del metodo
int fuse = tnt.getFuseLength();        // metodo con ritorno
```

---

## Principio: la logica va nel chiamato

La logica specifica va nel **metodo** (chiamato), non nel codice che lo invoca (chiamante). Così si evitano duplicazioni e si mantiene l'[[Incapsulamento]].

---

## Vedi anche

- [[Classe]] — dove si dichiarano i metodi
- [[Funzione]] — metodo senza oggetto (static)
- [[Firma di un metodo]] — input/output di un metodo
- [[Dot Notation]] — come si invocano i metodi
- [[Keyword this]] — riferimento all'oggetto corrente
