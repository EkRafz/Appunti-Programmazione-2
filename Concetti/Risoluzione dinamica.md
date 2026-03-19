

> [!info] Definizione
> La **risoluzione dinamica** (dynamic dispatch) è il meccanismo per cui il [[Metodo]] da eseguire viene determinato **a runtime** in base al tipo effettivo dell'[[Oggetto]], non al tipo della variabile. Avviene tramite la [[V-Table]].

---

## Come funziona

1. L'oggetto viene dereferenziato ([[Dereference]])
2. Si accede alla [[V-Table]] tramite il primo campo dell'oggetto
3. Si cerca il metodo all'[[Offset]] corretto nella V-Table
4. Si esegue il codice puntato

---

## Statico vs Dinamico

| | Risoluzione statica | Risoluzione dinamica |
|---|---|---|
| Quando | Compile time | Runtime |
| Per | Metodi [[Keyword static\|`static`]] | Metodi non-static |
| Meccanismo | Il compilatore sa già quale codice | Usa la [[V-Table]] |

---

## Vedi anche

- [[V-Table]] — la struttura che permette la risoluzione dinamica
- [[Polimorfismo]] — reso possibile dalla risoluzione dinamica
- [[Ereditarietà]] — rende la risoluzione dinamica necessaria
