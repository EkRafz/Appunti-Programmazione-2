

> [!info] Definizione
> L'istruzione **`import`** rende visibile una [[Classe]] da un altro [[Package]], permettendo di usarla senza il nome completo (fully qualified name).

---

## Sintassi

```java
// Import di una classe specifica
import lecture03.ackages.entities.Player;

// Import di tutte le classi di un package (sconsigliato)
import lecture03.ackages.entities.*;
```

---

## Esempio

```java
// Senza import: bisogna usare il nome completo
lecture03.ackages.entities.Player steve = new lecture03.ackages.entities.Player();

// Con import: si può usare il nome semplice
import lecture03.ackages.entities.Player;
Player steve = new Player();
```

---

## Vedi anche

- [[Package]] — la struttura organizzativa da cui si importa
- [[Namespace]] — l'import risolve i nomi all'interno dei namespace
