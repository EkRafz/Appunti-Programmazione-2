

> [!info] Definizione
> Un **package** in Java è un meccanismo che combina tre concetti: **[[Namespace]]** (previene conflitti di nome), **struttura delle cartelle** (directory su disco) e **unità di visibilità** (i [[Modificatori di Visibilità]] dipendono dal package).

---

## I 3 ruoli di un Package

| Ruolo | Descrizione | Esempio |
|---|---|---|
| **Namespace** | Previene conflitti di nome | `lecture03.blocks.TNT ≠ lecture02.v1.TNT` |
| **Directory** | Corrisponde a cartelle su disco | `lecture03/ackages/entities/Player.java` |
| **Visibilità** | Confine per i modificatori di accesso | package-private = visibile solo nello stesso package |

---

## Sintassi

```java
// Dichiarazione del package (prima riga del file)
package lecture03.ackages.entities;

// Import di classi da altri package
import lecture03.ackages.blocks.TNT;
```

---

## Struttura su disco

```
lecture03/
├── Lecture3.java               ← package lecture03
├── ackages/
│   ├── entities/
│   │   ├── Player.java         ← package lecture03.ackages.entities
│   │   └── Witch.java          ← package lecture03.ackages.entities
│   └── blocks/
│       └── TNT.java            ← package lecture03.ackages.blocks
```

---

## Vedi anche

- [[Namespace]] — previene conflitti di nome
- [[Import]] — rendere visibili classi da altri package
- [[Modificatori di Visibilità]] — i confini di accesso dipendono dal package
