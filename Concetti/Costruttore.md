

> [!info] Definizione
> Un **costruttore** è un metodo speciale usato per **inizializzare** i [[Campo|campi]] di un [[Oggetto]] al momento della sua creazione. Si riconosce perché ha lo **stesso nome della classe** e **non ha tipo di ritorno**.

---

## Regole

1. Ha lo **stesso nome** della [[Classe]]
2. **Non** ha tipo di ritorno (nemmeno `void`)
3. Viene chiamato con [[Keyword new|`new`]]: `new TNT()`
4. Una classe può avere **più costruttori** (con firme diverse → overloading)
5. Si può usare `this()` per chiamare un altro costruttore della stessa classe (constructor chaining)

---

## Costruttore di default

Se **non** si dichiara alcun costruttore, il compilatore genera automaticamente un **costruttore di default** (senza parametri) che inizializza tutti i campi ai loro valori di default.

> [!warning] Attenzione
> Se si dichiara **anche un solo** costruttore, il compilatore **non** genera più il costruttore di default!

---

## Esempio

```java
public class TNT {
    public int fuseLength;
    public double explosionPower;
    public boolean isIgnited;

    // Costruttore 1: senza parametri
    public TNT() {
        this.isIgnited = false;
        this.explosionPower = 4;
    }

    // Costruttore 2: con parametro
    public TNT(double e) {
        this();                    // chiama il costruttore sopra
        this.explosionPower = e;   // sovrascrive il valore
    }
}
```

```java
TNT t1 = new TNT();       // usa costruttore 1
TNT t2 = new TNT(10);     // usa costruttore 2
```

---

## Constructor Chaining

Con `this(...)` si può delegare a un altro costruttore della stessa classe:

```java
public FinalPlayer(String name) {
    this.name = name;
}

public FinalPlayer() {
    this("Steve");   // delega al costruttore sopra
}
```

---

## Vedi anche

- [[Classe]] — dove si dichiarano i costruttori
- [[Keyword new]] — l'operatore che invoca il costruttore
- [[Keyword this]] — per riferirsi all'oggetto corrente e per il chaining
- [[Campo]] — i campi che il costruttore inizializza
