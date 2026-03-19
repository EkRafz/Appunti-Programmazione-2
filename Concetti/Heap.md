

> [!info] Definizione
> Lo **Heap** è la sezione della memoria dove vengono allocati gli **[[Oggetto|oggetti]]** (creati con [[Keyword new|`new`]]) e gli **array**. A differenza dello [[Stack]], i dati nell'heap vivono finché il **Garbage Collector** non li rimuove.

---

## Cosa contiene

| Contenuto | Dettaglio |
|---|---|
| Oggetti creati con `new` | Ogni oggetto ha: puntatore alla [[V-Table]] + [[Campo|campi]] non-static |
| Array | `new TNT[5]` → l'array e il suo contenuto sono nell'heap |

---

## Layout di un oggetto nell'Heap

| Posizione | Contenuto |
|---|---|
| 1ª parola | Puntatore → [[V-Table]] della classe |
| 2ª parola | Campo 1 (non-static) |
| 3ª parola | Campo 2 (non-static) |
| ... | ... |

> I campi [[Keyword static|`static`]] **non** sono nell'heap — sono nella [[Read-Only Section]].

---

## Esempio

```java
Player p1 = new Player();
Player p2 = new Player();
```

```
  Stack                       Heap
  ┌────────────────┐
  │ p1 ─────────────────────► ┌──────────────────┐
  │                │          │ → V-TABLE_P      │
  │ p2 ──────────────────┐   │ username: null   │
  │                │     │   │ health: 20       │
  └────────────────┘     │   └──────────────────┘
                         └─► ┌──────────────────┐
                             │ → V-TABLE_P      │
                             │ username: null   │
                             │ health: 20       │
                             └──────────────────┘
```

---

## Vedi anche

- [[Stack]] — dove vivono le variabili locali e i puntatori
- [[Keyword new]] — l'operatore che alloca nell'heap
- [[V-Table]] — il primo campo di ogni oggetto nell'heap
- [[Layout in Memoria]] — il quadro completo dell'organizzazione in memoria
