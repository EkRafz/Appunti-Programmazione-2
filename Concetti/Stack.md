

> [!info] Definizione
> Lo **Stack** è la sezione della memoria dove vengono allocate le **variabili locali**, i **parametri** dei metodi e gli **stack frame** (contesti di esecuzione). Funziona con la logica LIFO (Last In, First Out).

---

## Cosa contiene

| Contenuto | Esempio |
|---|---|
| Variabili locali di [[Tipo Primitivo]] | `int x = 0;` → il valore `0` è nello stack |
| [[Puntatore|Puntatori]] a oggetti | `TNT t = new TNT();` → `t` (riferimento) è nello stack, l'oggetto è nell'[[Heap]] |
| Parametri dei metodi | `void helper(int p)` → `p` è nello stack |
| Stack frame | Un blocco per ogni metodo in esecuzione |

---

## Esempio

```java
private static void example() {
    int x = 0;                // x → nello stack (valore primitivo)
    TNT t = new TNT();        // t → nello stack (puntatore)
                               // l'oggetto TNT → nell'heap
}
```

```
  Stack                            Heap
  ┌──────────────┐          ┌─────────────────┐
  │  x = 0       │          │                 │
  │  t ──────────────────► │  TNT { ... }     │
  └──────────────┘          └─────────────────┘
```

---

## Vedi anche

- [[Heap]] — dove risiedono gli oggetti creati con `new`
- [[Tipo Primitivo]] — i primitivi vivono nello stack
- [[Puntatore]] — i riferimenti agli oggetti sono nello stack
- [[Passaggio per Copia]] — i primitivi vengono copiati fra stack frame
- [[Passaggio per Riferimento]] — i puntatori vengono copiati
