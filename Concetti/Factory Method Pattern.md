

> [!info] Definizione
> Il **Factory Method Pattern** è un [[Design Pattern]] che raggruppa la logica di costruzione di [[Oggetto|oggetti]] complessi in metodi [[Keyword static|`static`]] dedicati, separati dalla classe dell'oggetto stesso.

---

## Struttura

```
┌────────────────────┐        ┌────────────────────────┐
│   Classe target    │        │   Classe Factory       │
│   (es. Tree)       │        │   (es. TreeFactory)    │
├────────────────────┤        ├────────────────────────┤
│ costruttore:       │◄───────│ static createDarkOak() │
│ PACKAGE-PRIVATE    │  crea  │ static createBirch()   │
│ (solo la factory   │        │ static createJungle()  │
│  può chiamarlo)    │        │                        │
└────────────────────┘        └────────────────────────┘
```

---

## Esempio

```java
// La classe target: costruttore PACKAGE-PRIVATE
public class Tree {
    public enum Type { DarkOak, Birch, Jungle }
    public final Type type;
    private int height;

    // Solo classi nello stesso package possono usarlo!
    Tree(Type type, int height) {
        this.type = type;
        this.height = height;
    }

    public int getHeight() { return height; }
}
```

```java
// La factory: metodi static che creano gli oggetti
public class TreeFactory {
    public static Tree createDarkOak() {
        return new Tree(Tree.Type.DarkOak, 5);
    }
    public static Tree createBirch() {
        return new Tree(Tree.Type.Birch, 7);
    }
    public static Tree createJungle() {
        return new Tree(Tree.Type.Jungle, 20);
    }
}
```

```java
// Uso: si creano alberi SOLO tramite la factory
Tree t1 = TreeFactory.createDarkOak();
Tree t2 = TreeFactory.createBirch();
System.out.println(t1.type);  // DarkOak
```

---

## Vantaggi

- La logica di costruzione è **separata** e **organizzata**
- Il costruttore package-private **impedisce** la creazione diretta
- Facile aggiungere nuovi tipi di alberi senza modificare `Tree`

---

## Vedi anche

- [[Design Pattern]] — la famiglia di soluzioni a cui appartiene
- [[Keyword static]] — i factory methods sono static
- [[Package]] — il costruttore package-private limita l'accesso
