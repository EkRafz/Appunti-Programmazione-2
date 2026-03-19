

> [!info] Definizione
> Una **funzione** è un blocco di codice che esegue un'operazione **senza** essere legata a un [[Oggetto]]. In Java, le funzioni sono implementate come metodi [[Keyword static|`static`]].

---

## Funzione vs Metodo

| | Funzione (static) | [[Metodo]] (non-static) |
|---|---|---|
| Legata a | alla [[Classe]] | a un [[Oggetto]] |
| Accesso a `this` | ❌ No | ✅ Sì |
| Invocazione | `Classe.metodo()` | `oggetto.metodo()` |
| Esempio | `Math.sqrt(4)` | `player.damage(5)` |

---

## Esempio

```java
public class GameConstants {
    // Questa è una FUNZIONE: non ha bisogno di un oggetto
    public static void printMOTD() {
        System.out.println("Welcome to Minecraft!");
    }
}

// Invocazione: tramite il nome della classe
GameConstants.printMOTD();
```

---

## Vedi anche

- [[Metodo]] — comportamento legato a un oggetto
- [[Keyword static]] — la keyword che rende un metodo una funzione
