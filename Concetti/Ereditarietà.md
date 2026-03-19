

> [!info] Definizione
> L'**ereditarietà** è un pilastro della [[Programmazione Orientata agli Oggetti|OOP]] che permette a una [[Classe]] (figlia) di **estendere** un'altra classe (padre), ereditandone [[Campo|campi]] e [[Metodo|metodi]] e potendo aggiungere o sovrascrivere comportamento.

---

## Concetto

- **Classificazione**: un oggetto può appartenere a più classi (es. un `Dog` è anche un `Animal`)
- **Specializzazione**: la classe figlia aggiunge stato e comportamento specifico

---

## Sintassi (anticipazione)

```java
// Classe padre
public class Animal {
    public String name;
    public void speak() {
        System.out.println("...");
    }
}

// Classe figlia: eredita name e speak(), aggiunge fetch()
public class Dog extends Animal {
    @Override
    public void speak() {
        System.out.println("Woof!");
    }

    public void fetch() {
        System.out.println("Fetching!");
    }
}
```

---

## Vedi anche

- [[Programmazione Orientata agli Oggetti]] — i 5 pilastri
- [[Polimorfismo]] — reso possibile dall'ereditarietà
- [[V-Table]] — il meccanismo di dispatch che l'ereditarietà sfrutta
- [[Modificatori di Visibilità]] — `protected` è legato all'ereditarietà
