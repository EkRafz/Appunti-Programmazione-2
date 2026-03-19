

> [!info] Definizione
> L'**incapsulamento** (encapsulation / information hiding) è il principio OOP che permette di **nascondere** i dettagli implementativi di una [[Classe]], esponendo solo un'**interfaccia pubblica** controllata. Garantisce che lo stato interno sia modificato solo in modo corretto.

---

## A cosa serve

1. **Nascondere** dettagli implementativi → chi usa la classe non vede la logica interna
2. **Definire [[Invariante|invarianti]]**: proprietà che sono **sempre vere** per ogni oggetto

---

## Supporto nei linguaggi

| Linguaggio | Incapsulamento? |
|---|---|
| C | **No** — nessun supporto a livello di linguaggio |
| C++ | Parziale — bypassabile con [[Aritmetica dei puntatori]] |
| **Java** | **Sì** — garantito a livello di linguaggio |
| Rust | Sì — con invarianti ancora più potenti |

---

## Esempio

```java
public class Player {
    private int health = 20;         // nascosto! Solo Player può accedervi
    private boolean isPoisoned;

    // L'unico modo per modificare health dall'esterno
    public void damage(int amount) {
        this.health -= amount;       // logica controllata
        if (this.health <= 0) {
            System.out.println("Player died!");
        }
    }

    // Il veleno non uccide (invariante: health >= 1 dopo poisonDamage)
    public void poisonDamage() {
        if (!this.isPoisoned || this.health < 2) return;
        this.health -= 1;
    }
}
```

```java
Player steve = new Player();
steve.damage(5);               // ✅ OK: usa l'interfaccia pubblica
// steve.health = -100;        // ❌ ERRORE! health è private
```

---

## Strumenti per l'incapsulamento in Java

| Strumento | Ruolo |
|---|---|
| [[Modificatori di Visibilità]] (`private`) | Nascondono lo stato |
| [[Keyword final]] | Impediscono modifiche |
| [[Keyword static]] | Dati condivisi (una sola copia) |
| [[Getter e Setter]] | Accesso controllato ai campi |

---

## Vedi anche

- [[Invariante]] — proprietà garantite dall'incapsulamento
- [[Modificatori di Visibilità]] — `private`, `public`, etc.
- [[Getter e Setter]] — metodi per accesso controllato
