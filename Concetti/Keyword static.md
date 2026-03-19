

> [!info] Definizione
> La keyword **`static`** indica che un [[Campo]] o [[Metodo]] appartiene alla **[[Classe]]** stessa, non a un singolo [[Oggetto]]. Esiste in **una sola copia**, condivisa da tutte le istanze.

---

## Static vs Non-static

| | Non-static | Static |
|---|---|---|
| Appartiene a | un **oggetto** | la **classe** |
| Copie | una **per oggetto** | **una sola** in totale |
| Accesso | `oggetto.campo` | `Classe.campo` |
| Usa `this`? | ✅ Sì | ❌ No |
| Può accedere a | tutto | solo altri `static` |

> Un metodo `static` è concettualmente una [[Funzione]].

---

## Casi d'uso principali

| Caso d'uso | Esempio |
|---|---|
| **Costanti globali** | `GameConstants.MAX_STACK_SIZE` |
| **[[Singleton Pattern]]** | `DragonEgg.getInstance()` |
| **[[Factory Method Pattern]]** | `TreeFactory.createBirch()` |

---

## Esempio

```java
public class GameConstants {
    // Campo static: UNA sola copia per tutti
    public static int MAX_STACK_SIZE = 64;

    // Metodo static: non ha bisogno di un oggetto
    public static void printMOTD() {
        System.out.println("Welcome to Minecraft!");
    }
}
```

```java
// Accesso tramite nome della classe (non serve un oggetto!)
System.out.println(GameConstants.MAX_STACK_SIZE);  // 64
GameConstants.printMOTD();
```

---

## Dove risiedono in memoria

| Cosa | Dove |
|---|---|
| Campi `static` | [[Read-Only Section]] (data segment) |
| Metodi `static` | [[Code Section]] |
| Campi non-static | [[Heap]] (dentro l'oggetto) |

---

## Vedi anche

- [[Funzione]] — un metodo static è una funzione
- [[Keyword final]] — `static final` per costanti immutabili
- [[Singleton Pattern]] — usa `static` per garantire un'unica istanza
- [[Factory Method Pattern]] — usa metodi `static` per creare oggetti
