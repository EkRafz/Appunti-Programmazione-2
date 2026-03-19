

> [!info] Definizione
> **`null`** rappresenta l'**assenza di un valore**: un [[Puntatore]] che non punta a nessun [[Oggetto]]. È il valore di default per variabili di tipo classe e array non inizializzate.

---

## Quando si incontra `null`

| Contesto | Esempio |
|---|---|
| Campo oggetto non inizializzato | `public String username;` → `null` |
| Campo array non inizializzato | `TNT[] arr;` → `null` |
| Array con celle non riempite | `new TNT[5]` → ogni cella è `null` |

---

## Esempio

```java
public class Player {
    public String username;    // default: null (non inizializzato)
    private int health = 20;   // default: 0, inizializzato a 20
}

Player p = new Player();
System.out.println(p.username);  // null

// p.username.length() → NullPointerException! Non c'è un oggetto!
```

---

## Attenzione

Chiamare un [[Metodo]] su `null` causa un **`NullPointerException`** a runtime:

```java
String s = null;
s.length();   // ❌ NullPointerException!
```

---

## Vedi anche

- [[Puntatore]] — `null` è un puntatore che non punta a nulla
- [[Tipo Primitivo]] — i primitivi hanno default diversi (`0`, `false`)
- [[Heap]] — `null` significa che non c'è nessun oggetto nell'heap
