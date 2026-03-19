

> [!info] Definizione
> I **getter** e **setter** sono [[Metodo|metodi]] pubblici che permettono di **leggere** e **modificare** [[Campo|campi]] `private` di una [[Classe]] in modo controllato.

---

## Sintassi

```java
// Getter: ritorna il valore del campo
public Tipo getCampo() {
    return this.campo;
}

// Setter: modifica il valore del campo
public void setCampo(Tipo valore) {
    this.campo = valore;
}
```

---

## Esempio

```java
public class Player {
    private int health = 20;
    private boolean isPoisoned = false;

    // Getter
    public String getUsername() {
        return this.username;
    }

    // Setter con logica di controllo
    public void setPoisoned(boolean p) {
        this.isPoisoned = p;
    }
}
```

---

## Anti-pattern: getter + setter inutili

> [!warning] Attenzione!
> Creare un campo `private` e poi esporre getter **e** setter senza logica aggiuntiva è **equivalente** a renderlo `public`! I getter/setter hanno senso **solo** quando aggiungono **logica di controllo**.

```java
// ❌ INUTILE: è come avere il campo public
private int x;
public int getX() { return x; }
public void setX(int x) { this.x = x; }

// ✅ UTILE: il setter aggiunge logica
public void damage(int amount) {
    this.health -= amount;
    if (this.health <= 0) System.out.println("Player died!");
}
```

---

## Vedi anche

- [[Campo]] — la variabile d'istanza a cui si accede
- [[Incapsulamento]] — getter/setter permettono accesso controllato
- [[Modificatori di Visibilità]] — il campo è `private`, i metodi sono `public`
