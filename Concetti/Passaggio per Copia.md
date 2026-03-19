

> [!info] Definizione
> Il **passaggio per copia** (pass by value) avviene quando un valore di [[Tipo Primitivo]] (`int`, `boolean`, `double`, ...) viene passato come argomento a un [[Metodo]]. Il valore viene **duplicato** nello stack frame del metodo chiamato.

---

## Come funziona

1. Il valore della variabile viene **copiato** nel parametro del metodo
2. Il metodo lavora sulla **copia**
3. Modificare la copia **non** modifica l'originale

---

## Esempio

```java
private static void helper(int p) {
    p = 42;  // modifica solo la COPIA locale
}

public static void main(String[] args) {
    int x = 0;
    helper(x);
    System.out.println(x);  // stampa 0 — x NON è cambiato!
}
```

```
  PRIMA di helper(x):          DENTRO helper():
  Stack                         Stack
  ┌──────────┐                  ┌──────────┐
  │ x = 0    │                  │ x = 0    │  ← invariato
  └──────────┘                  │ p = 42   │  ← copia modificata
                                └──────────┘
```

---

## Vedi anche

- [[Passaggio per Riferimento]] — come vengono passati oggetti e array
- [[Tipo Primitivo]] — i tipi passati per copia
- [[Stack]] — dove vivono le copie
