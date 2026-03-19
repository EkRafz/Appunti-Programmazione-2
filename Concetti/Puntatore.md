

> [!info] Definizione
> Un **puntatore** (reference) è un **indirizzo di memoria** che indica dove si trova un [[Oggetto]] nell'[[Heap]]. In Java, quando una variabile "contiene" un oggetto, in realtà contiene un puntatore ad esso.

---

## Java nasconde i puntatori

- Non esiste [[Aritmetica dei puntatori]] in Java (a differenza del C/C++)
- Java inserisce automaticamente i [[Dereference]] quando lavoriamo con oggetti
- Un puntatore occupa tipicamente **un registro** (una parola di memoria)

---

## Esempio

```java
TNT tnt1 = new TNT();   // tnt1 contiene un PUNTATORE all'oggetto
TNT tnt2 = tnt1;        // tnt2 contiene lo STESSO puntatore!

tnt2.fuseLength = 5;     // modifica l'oggetto puntato da entrambi
// Ora anche tnt1.fuseLength == 5 — puntano allo stesso oggetto!
```

```
  Stack                       Heap
  ┌──────────┐          ┌──────────────┐
  │ tnt1 ───────────┬──►│  TNT { ... } │
  │ tnt2 ───────────┘   └──────────────┘
  └──────────┘
  Due variabili → STESSO oggetto!
```

---

## Confronto con `==`

L'operatore `==` su oggetti confronta gli **indirizzi** (puntatori), non lo stato:

```java
TNT a = new TNT();
TNT b = new TNT();
TNT c = a;

System.out.println(a == b);  // false — oggetti diversi
System.out.println(a == c);  // true — stesso oggetto!
```

---

## Vedi anche

- [[Heap]] — dove risiedono gli oggetti puntati
- [[Stack]] — dove risiede il puntatore (variabile locale)
- [[Passaggio per Riferimento]] — si passa una copia del puntatore
- [[Dereference]] — seguire il puntatore per accedere all'oggetto
- [[Valore null]] — un puntatore che non punta a nulla
