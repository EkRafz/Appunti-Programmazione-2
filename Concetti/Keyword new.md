

> [!info] Definizione
> La keyword **`new`** crea una nuova istanza ([[Oggetto]]) di una [[Classe]], allocandola nell'[[Heap]] e invocando il [[Costruttore]] specificato.

---

## Sintassi

```java
Tipo variabile = new Tipo(argomenti);
```

---

## Cosa succede quando si usa `new`

1. Viene allocato spazio nell'[[Heap]] per il nuovo oggetto
2. I [[Campo|campi]] vengono inizializzati ai valori di default
3. Viene invocato il [[Costruttore]] corrispondente
4. Viene restituito un [[Puntatore]] all'oggetto creato

---

## Esempio

```java
// Ogni "new" crea un oggetto SEPARATO e indipendente
TNT tnt1 = new TNT();       // primo oggetto
TNT tnt2 = new TNT(10);     // secondo oggetto (costruttore diverso)

// tnt1 e tnt2 sono oggetti diversi in zone di memoria diverse!
```

```
  Stack                          Heap
  ┌──────────┐            ┌──────────────┐
  │ tnt1 ───────────────► │  TNT obj 1   │
  ├──────────┤            └──────────────┘
  │ tnt2 ───────────────► ┌──────────────┐
  └──────────┘            │  TNT obj 2   │
                          └──────────────┘
```

---

## Vedi anche

- [[Oggetto]] — ciò che viene creato con `new`
- [[Costruttore]] — il metodo invocato da `new`
- [[Heap]] — dove viene allocato l'oggetto
- [[Puntatore]] — ciò che la variabile contiene dopo `new`
