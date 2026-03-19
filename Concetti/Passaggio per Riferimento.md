

> [!info] Definizione
> Il **passaggio per riferimento** avviene quando un [[Oggetto]] o un array viene passato come argomento a un [[Metodo]]. Si passa una **copia del [[Puntatore]]**, non dell'oggetto stesso. Entrambi i puntatori (originale e copia) puntano allo **stesso oggetto** nell'[[Heap]].

---

## Come funziona

1. Il **puntatore** all'oggetto viene copiato nel parametro del metodo
2. Chiamante e chiamato puntano allo **stesso oggetto**
3. Modifiche all'oggetto sono **visibili a tutti** i riferimenti

---

## Esempio

```java
private static void reference(TNT t) {
    t.fuseLength = 5;  // modifica l'oggetto puntato → visibile anche fuori!
}

public static void main(String[] args) {
    TNT tnt = new TNT();           // fuseLength = 80
    reference(tnt);
    System.out.println(tnt.fuseLength);  // 5 — modificato dal metodo!
}
```

```
  Stack                              Heap
  ┌──────────────────┐         ┌─────────────────┐
  │ main: tnt ───────────────►│  TNT             │
  │                  │    ┌──►│  fuseLength: 5   │  ← modificato!
  │ reference: t ────────┘    │  isIgnited: false│
  └──────────────────┘         └─────────────────┘
  Due variabili → STESSO oggetto nell'heap
```

---

## I tre tipi di valori in Java

| Tipo | Dove allocato | Come passato |
|---|---|---|
| [[Tipo Primitivo]] (`int`, `boolean`) | [[Stack]] | Per **copia** |
| Tipo [[Classe]] (`Player`, `TNT`) | [[Heap]] | Per **riferimento** |
| Tipo Array (`int[]`, `TNT[]`) | [[Heap]] | Per **riferimento** |

---

## Vedi anche

- [[Passaggio per Copia]] — come vengono passati i primitivi
- [[Puntatore]] — ciò che viene copiato nel passaggio per riferimento
- [[Heap]] — dove risiede l'oggetto condiviso
