

> [!info] Definizione
> Un **oggetto** (o **istanza**) è un'entità creata a runtime a partire da una [[Classe]]. Ogni oggetto ha il proprio **stato** (valori dei [[Campo|campi]]), **comportamento** ([[Metodo|metodi]]) e **identità** (indirizzo in memoria).

---

## Caratteristiche

- Esiste solo a **runtime** (aspetto dinamico)
- Viene creato con la keyword [[Keyword new|`new`]]
- Ogni oggetto ha la **propria copia** dei campi non-static
- Modificare un oggetto **non** modifica gli altri della stessa classe
- Viene allocato nell'[[Heap]]

---

## Esempio

```java
TNT blockA = new TNT();
TNT blockB = new TNT();

blockA.isIgnited = true;

System.out.println(blockA.isIgnited); // true
System.out.println(blockB.isIgnited); // false — oggetti indipendenti!
```

```
  blockA                    blockB
  ┌────────────────┐        ┌────────────────┐
  │ fuseLength: 10 │        │ fuseLength: 10 │
  │ isIgnited: TRUE│        │ isIgnited:FALSE│  ← indipendenti!
  └────────────────┘        └────────────────┘
```

---

## Stato, Comportamento, Identità

| Proprietà | Descrizione | Esempio |
|---|---|---|
| **Stato** | Valori dei campi | `health = 20`, `isIgnited = false` |
| **Comportamento** | Metodi invocabili | `tnt.ignite()`, `player.damage(5)` |
| **Identità** | Indirizzo unico in memoria | `tnt1 != tnt2` anche se hanno lo stesso stato |

---

## Vedi anche

- [[Classe]] — lo schema da cui viene creato l'oggetto
- [[Keyword new]] — l'operatore di creazione
- [[Heap]] — dove risiedono gli oggetti in memoria
- [[Puntatore]] — il riferimento all'oggetto
