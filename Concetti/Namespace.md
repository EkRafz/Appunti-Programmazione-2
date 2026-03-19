

> [!info] Definizione
> Un **namespace** è un meccanismo che previene i **conflitti di nome** raggruppando identificatori sotto un prefisso univoco. In Java, i [[Package]] fungono da namespace.

---

## Problema: conflitti di nome

Senza namespace, due classi con lo stesso nome si confonderebbero:

```java
// ❌ Senza namespace: quale TNT uso?
TNT tnt = new TNT();   // è la TNT della lezione 2 o della 3?
```

---

## Soluzione: namespace tramite package

```java
// ✅ Con namespace: ogni TNT ha un nome univoco
lecture02.v1.TNT        tnt1 = new lecture02.v1.TNT();
lecture03.ackages.blocks.TNT tnt2 = new lecture03.ackages.blocks.TNT();
```

Con l'[[Import]] si può evitare di scrivere il nome completo ogni volta.

---

## Vedi anche

- [[Package]] — il meccanismo Java che implementa i namespace
- [[Import]] — per usare classi senza il nome completo
