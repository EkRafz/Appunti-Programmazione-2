

> [!info] Definizione
> La **V-Table** (Virtual Method Table) è una tabella contenente **puntatori alle implementazioni** dei [[Metodo|metodi]] di una [[Classe]]. Ogni oggetto nell'[[Heap]] contiene come primo campo un puntatore alla V-Table della propria classe.

---

## Struttura

Ogni entry della V-Table contiene un indirizzo che punta al codice del metodo nella [[Code Section]]:

| Indice | Indirizzo | Metodo |
|---|---|---|
| offset 0 | `0x000010` | → `fakeAttack` |
| offset 1 | `0x000040` | → `attack` |

---

## Cosa NON va nella V-Table

| Elemento | Nella V-Table? | Perché |
|---|---|---|
| Metodi non-static | ✅ Sì | Devono essere risolti dinamicamente |
| Metodi `static` | ❌ No | Risolti a compile time (staticamente) |
| [[Costruttore|Costruttori]] | ❌ No | Non vengono dispatched dinamicamente |

---

## Come viene invocato un metodo

Quando si chiama `w1.fakeAttack(p)`:

1. Prendi l'indirizzo dell'oggetto `w1`
2. La prima parola contiene il puntatore alla **V-Table**
3. Segui il puntatore e arrivi alla V-Table
4. Vai all'**offset** del metodo (es. offset 0 per `fakeAttack`)
5. Ottieni il puntatore al **codice** del metodo → eseguilo

---

## Esempio: V-Table di Player

```
  V-TABLE di Player:
  ┌─────────────────┐
  │ → setPoisoned   │   offset 0
  │ → getUsername    │   offset 1
  │ → damage        │   offset 2
  │ → isAlive       │   offset 3
  │ → poison        │   offset 4
  │ → poisonDamage  │   offset 5
  └─────────────────┘
```

---

## Vedi anche

- [[Heap]] — ogni oggetto ha un puntatore alla V-Table
- [[Code Section]] — dove risiede il codice dei metodi
- [[Layout in Memoria]] — il quadro completo
- [[Polimorfismo]] — la V-Table è fondamentale per il dispatch dinamico
