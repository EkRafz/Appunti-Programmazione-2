

> [!info] Definizione
> Il **memory footprint** di una [[Classe]] è la quantità di memoria che ogni [[Oggetto]] di quel tipo occupa nell'[[Heap]]. Dipende dal numero e dal tipo dei [[Campo|campi]] non-static della classe.

---

## Cosa contribuisce al footprint

| Elemento | Contribuisce? | Dettaglio |
|---|---|---|
| Puntatore alla [[V-Table]] | ✅ Sì | Sempre presente (1 parola) |
| Campi non-static | ✅ Sì | Ogni campo occupa spazio |
| Campi [[Keyword static\|static]] | ❌ No | Sono nella [[Read-Only Section]] |
| Codice dei metodi | ❌ No | È nella [[Code Section]] |

---

## Esempio

```
  Oggetto Witch: footprint minimo (solo vtable, nessun campo)
  ┌──────────────┐
  │ → V-TABLE    │  1 parola
  └──────────────┘

  Oggetto Player: footprint maggiore (vtable + 4 campi)
  ┌──────────────┐
  │ → V-TABLE    │  1 parola
  │ username     │  1 parola (riferimento)
  │ health       │  1 parola (int)
  │ isPoisoned   │  1 parola (boolean)
  │ fakeHealth   │  1 parola (int)
  └──────────────┘
```

---

## Vedi anche

- [[Layout in Memoria]] — organizzazione completa in memoria
- [[Heap]] — dove risiedono gli oggetti
- [[V-Table]] — sempre presente nel footprint
