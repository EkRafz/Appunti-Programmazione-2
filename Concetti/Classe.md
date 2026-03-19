

> [!info] Definizione
> Una **classe** è un tipo definito dall'utente che funge da "schema" (blueprint) per creare [[Oggetto|oggetti]]. Definisce la **forma dello stato** ([[Campo|campi]]) e il **comportamento** ([[Metodo|metodi]]) comuni a tutte le istanze.

---

## Caratteristiche

- Una classe è un concetto **statico** (esiste a compile time)
- Non è un oggetto: è lo "stampino" con cui si creano oggetti
- Può contenere: [[Campo|campi]], [[Metodo|metodi]], [[Costruttore|costruttori]], [[Enum|enums]] interne
- Ogni file `.java` contiene tipicamente **una classe pubblica** con lo stesso nome del file

---

## Esempio

```java
// Definizione di una classe: aggiunge un NUOVO TIPO al programma
public class TNT {
    // Campi (stato)
    public int fuseLength = 10;
    public boolean isIgnited;

    // Costruttore (inizializzazione)
    public TNT() {
        this.isIgnited = false;
    }

    // Metodo (comportamento)
    public void ignite() {
        this.isIgnited = true;
    }
}
```

```java
// Uso: creare oggetti dalla classe
TNT tnt1 = new TNT();  // prima istanza
TNT tnt2 = new TNT();  // seconda istanza (indipendente!)
```

---

## Analogia

> La classe è come lo **stampino dei biscotti**: definisce la forma. Gli [[Oggetto|oggetti]] sono i biscotti: hanno la stessa forma ma decorazioni (stato) diverse.

---

## Vedi anche

- [[Oggetto]] — un'istanza di una classe
- [[Campo]] — lo stato definito dalla classe
- [[Metodo]] — il comportamento definito dalla classe
- [[Costruttore]] — il metodo speciale per inizializzare gli oggetti
- [[Keyword new]] — l'operatore per creare istanze
