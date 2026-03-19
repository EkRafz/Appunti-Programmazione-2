

> [!info] Definizione
> Un **offset** è la distanza (in parole di memoria) dall'inizio di una struttura dati a un suo specifico elemento. Nell'ambito degli [[Oggetto|oggetti]] Java, l'offset indica la posizione di un [[Campo]] o di un metodo nella [[V-Table]] rispetto all'inizio dell'oggetto o della tabella.

---

## Esempio: offset nei campi di un oggetto

```
  Oggetto Player nell'heap:
  ┌────────────┬────────┐
  │ Offset 0   │ → V-TABLE (puntatore alla tabella dei metodi) │
  │ Offset 1   │ username: null │
  │ Offset 2   │ health: 20 │
  │ Offset 3   │ isPoisoned: false │
  │ Offset 4   │ fakeHealth: 10 │
  └────────────┴────────┘
```

## Esempio: offset nella V-Table

```
  V-TABLE di Witch:
  ┌────────────┬──────────────────┐
  │ Offset 0   │ → fakeAttack()   │
  │ Offset 1   │ → attack()       │
  └────────────┴──────────────────┘
```

Il compilatore conosce gli offset a compile time e li usa per accedere efficientemente ai campi e ai metodi.

---

## Vedi anche

- [[V-Table]] — gli offset indicano la posizione dei metodi
- [[Layout in Memoria]] — come sono organizzati gli oggetti
- [[Heap]] — dove risiedono gli oggetti con i loro offset
