

> [!info] Definizione
> La **Programmazione Orientata agli Oggetti** (Object-Oriented Programming, OOP) è un paradigma di programmazione basato sul concetto di **[[Oggetto]]**, che combina dati (**stato**) e comportamento (**metodi**) in un'unica entità.

---

## I 5 Pilastri dell'OOP

| Pilastro | Descrizione |
|---|---|
| **[[Oggetto]]** | Entità con stato + comportamento + identità + locazione |
| **[[Incapsulamento]]** | Interfacce pubbliche, implementazione nascosta |
| **Classificazione** ([[Ereditarietà]]) | Gli oggetti appartengono a più classi |
| **Specializzazione** ([[Ereditarietà]]) | Aggiunta di stato e comportamento |
| **[[Polimorfismo]]** | Stesso oggetto usabile in contesti di tipo diverso |

---

## Esempio

```java
// Una CLASSE definisce lo "schema" (stato + comportamento)
public class Player {
    private int health = 20;        // stato

    public void damage(int amount) { // comportamento
        this.health -= amount;
    }
}

// Un OGGETTO è un'istanza concreta della classe
Player steve = new Player();   // crea un oggetto
steve.damage(5);               // invoca un comportamento
```

---

## Perché OOP?

- **Modularità** → il codice è diviso in classi indipendenti
- **Riuso** → le classi possono essere riutilizzate in contesti diversi
- **Manutenibilità** → modifiche localizzate, non si rompe tutto il progetto

---

## Vedi anche

- [[Classe]] — lo schema per creare oggetti
- [[Oggetto]] — un'istanza concreta di una classe
- [[Incapsulamento]] — nascondere i dettagli implementativi
- [[Polimorfismo]] — usare oggetti in contesti di tipo diverso
- [[Ereditarietà]] — classificazione e specializzazione
