

> [!info] Definizione
> Un linguaggio è **fortemente tipato** (strongly typed) quando il [[Compilatore]] verifica rigorosamente la compatibilità dei tipi a compile time, impedendo operazioni tra tipi incompatibili.

---

## Java e la tipizzazione forte

- Ogni variabile ha un **tipo dichiarato** che il compilatore verifica
- Non si può assegnare un valore di tipo incompatibile
- Gli errori di tipo vengono catturati a **compile time**, non a runtime

```java
int x = "hello";    // ❌ ERRORE DI COMPILAZIONE: String ≠ int
Player p = new TNT(); // ❌ ERRORE: TNT non è un Player
```

> [!note] Limitazione
> Java ha dei limiti nella tipizzazione degli array (array covariance), ma in generale è fortemente tipato.

---

## Vedi anche

- [[Java]] — linguaggio fortemente tipato
- [[Compilatore]] — verifica i tipi a compile time
- [[Tipo Primitivo]] — i tipi base di Java
