

> [!info] Definizione
> La **firma** (signature) di un [[Metodo]] è la combinazione del suo **nome**, dei **tipi dei parametri** e del **tipo di ritorno**. Serve al compilatore per distinguere metodi con lo stesso nome ma parametri diversi (overloading).

---

## Componenti

```
tipoRitorno nomeMetodo(tipoParam1, tipoParam2, ...)
```

| Componente | Esempio |
|---|---|
| Nome | `damage` |
| Parametri | `(int amount)` |
| Tipo di ritorno | `void` |
| **Firma completa** | `void damage(int)` |

---

## Esempio: Overloading

Più [[Costruttore|costruttori]] o metodi con **lo stesso nome** ma **firme diverse**:

```java
public class TNT {
    // Firma: TNT()
    public TNT() { ... }

    // Firma: TNT(double) — diversa dalla precedente!
    public TNT(double e) { ... }
}
```

---

## Vedi anche

- [[Metodo]] — il blocco di codice con una firma
- [[Costruttore]] — può avere più firme (overloading)
