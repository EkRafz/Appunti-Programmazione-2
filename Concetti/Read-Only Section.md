

> [!info] Definizione
> La **Read-Only Section** (o data segment) è la sezione della memoria che contiene i [[Campo|campi]] [[Keyword static|`static`]] di una [[Classe]]. Esiste in **una sola copia**, condivisa da tutti gli [[Oggetto|oggetti]].

---

## Cosa contiene

- Campi `static` (es. `TNT.DEFAULT_FUSE_LENGTH = 80`)
- Campi `static final` (es. `TNT.EXPLOSION_POWER = 100`)

> I campi non-static vivono nell'[[Heap]] (dentro l'oggetto), **non** qui.

---

## Esempio

```
  Read-Only Section per TNT:
  ┌──────────────────────────────────────┐
  │ EXPLOSION_POWER = 100    (final)     │
  │ DEFAULT_FUSE_LENGTH = 80             │
  └──────────────────────────────────────┘
```

---

## Vedi anche

- [[Keyword static]] — i campi static risiedono qui
- [[Code Section]] — dove risiede il codice dei metodi
- [[Layout in Memoria]] — il quadro completo
