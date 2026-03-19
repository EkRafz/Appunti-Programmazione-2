

> [!info] Definizione
> Il **polimorfismo** è uno dei 5 pilastri della [[Programmazione Orientata agli Oggetti|OOP]]. Permette di usare lo **stesso oggetto** in contesti di tipo diverso: un metodo può essere invocato senza conoscere il tipo esatto dell'oggetto a compile time.

---

## Concetto

Il polimorfismo si basa su:
- **[[Ereditarietà]]** → una classe figlia può essere usata dove ci si aspetta la classe padre
- **[[V-Table]]** → il metodo corretto viene selezionato a **runtime** (dispatch dinamico)

---

## Esempio concettuale

```java
// Se Animal fosse una classe padre con il metodo speak():
Animal a = new Dog();   // polimorfismo: Dog è trattato come Animal
a.speak();              // chiama Dog.speak(), NON Animal.speak()!
```

> Il tipo della **variabile** è `Animal`, ma l'**oggetto** è un `Dog`. A runtime, la [[V-Table]] di `Dog` determina quale `speak()` eseguire.

---

## Vedi anche

- [[Programmazione Orientata agli Oggetti]] — i 5 pilastri dell'OOP
- [[Ereditarietà]] — prerequisito per il polimorfismo
- [[V-Table]] — il meccanismo che permette il dispatch dinamico
