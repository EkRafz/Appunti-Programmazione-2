

> [!info] Definizione
> Il **layout in memoria** descrive come [[Classe|classi]] e [[Oggetto|oggetti]] sono organizzati nelle diverse sezioni della memoria a runtime.

---

## Le 4 sezioni della memoria

| Sezione | Contenuto |
|---|---|
| **[[Code Section]]** | Codice dei metodi (static e non-static), costruttori |
| **[[Read-Only Section]]** | Campi `static` (e `static final`). Una sola copia |
| **[[Stack]]** | Variabili locali, parametri, stack frame |
| **[[Heap]]** | Oggetti allocati con `new`: [[V-Table]] + campi non-static |

---

## Visione d'insieme

```
╔══════════════════════════════════════════════╗
║  CODE SECTION                                ║
║  Codice metodi, costruttori                  ║
╠══════════════════════════════════════════════╣
║  READ-ONLY / STATIC DATA                     ║
║  Campi static (es. EXPLOSION_POWER = 100)    ║
╠══════════════════════════════════════════════╣
║  V-TABLES                                    ║
║  Tabelle dei puntatori ai metodi per classe  ║
╠══════════════════════════════════════════════╣
║  STACK                                       ║
║  Variabili locali (puntatori + primitivi)    ║
╠══════════════════════════════════════════════╣
║  HEAP                                        ║
║  Oggetti: [vtable ptr | campo1 | campo2 ...] ║
╚══════════════════════════════════════════════╝
```

---

## Esempio: layout di un oggetto TNT

```
  t1 ──────► ┌──────────────────┐
             │ → V-TABLE_TNT    │  ← puntatore alla v-table
             │ fuseLength: 80   │  ← campo non-static
             │ isIgnited: false │  ← campo non-static
             └──────────────────┘

  I campi static (EXPLOSION_POWER, DEFAULT_FUSE_LENGTH)
  NON sono nell'oggetto — sono nella Read-Only Section!
```

---

## Vedi anche

- [[Code Section]] — dove risiede il codice
- [[Read-Only Section]] — dove risiedono i campi static
- [[Stack]] — dove vivono le variabili locali
- [[Heap]] — dove vivono gli oggetti
- [[V-Table]] — la tabella dei metodi
