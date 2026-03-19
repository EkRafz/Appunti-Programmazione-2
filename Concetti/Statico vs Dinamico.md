

> [!info] Definizione
> In programmazione, i termini **statico** e **dinamico** distinguono ciò che accade a **compile time** (quando il codice viene scritto e compilato) da ciò che accade a **runtime** (quando il programma è in esecuzione).

---

## Confronto

| | Statico (Compile Time) | Dinamico (Runtime) |
|---|---|---|
| Cosa si fa | Si scrivono [[Classe|classi]] | Si creano [[Oggetto|oggetti]] |
| Chi agisce | Il programmatore | Il runtime di Java |
| Oggetti? | Non esistono | Vengono creati con `new` |
| Classi? | Vengono definite | Non si scrivono nuove classi |

---

## Regola fondamentale

> Il programmatore scrive **classi** (statico), a runtime queste vengono **istanziate** in oggetti (dinamico).

---

## Esempio

```java
// STATICO: il programmatore scrive la classe TNT
public class TNT {
    public int fuseLength = 10;
    public void ignite() { ... }
}

// DINAMICO: a runtime si creano oggetti
TNT tnt1 = new TNT();    // istanziazione: da classe → oggetto
TNT tnt2 = new TNT();    // un altro oggetto, indipendente
```

---

## Vedi anche

- [[Classe]] — concetto statico (compile time)
- [[Oggetto]] — concetto dinamico (runtime)
- [[V-Table]] — la risoluzione dei metodi può essere statica o dinamica
