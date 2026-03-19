

> [!info] Definizione
> La **Code Section** è la sezione della memoria che contiene il **codice eseguibile** dei [[Metodo|metodi]] (sia static che non-static) e dei [[Costruttore|costruttori]]. È condivisa tra tutti gli [[Oggetto|oggetti]] della stessa [[Classe]].

---

## Cosa contiene

- Codice dei metodi non-static (referenziati dalla [[V-Table]])
- Codice dei metodi [[Keyword static|`static`]]
- Codice dei [[Costruttore|costruttori]]

---

## Esempio

```
  Code Section per TNT:
  ┌──────────────────────────────────────┐
  │ TNT()       (costruttore)  { ... }   │
  │ ignite()                   { ... }   │
  │ tick()                     { ... }   │
  │ explode()   (private)      { ... }   │
  └──────────────────────────────────────┘
```

> Il codice è **unico** per classe: non viene duplicato per ogni oggetto. Quando si chiama un metodo su un oggetto, la [[V-Table]] punta alla stessa Code Section.

---

## Vedi anche

- [[V-Table]] — tabella di puntatori ai metodi nella code section
- [[Read-Only Section]] — dove risiedono i campi static
- [[Layout in Memoria]] — il quadro completo
