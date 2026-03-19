

> [!info] Definizione
> L'**aritmetica dei puntatori** è una tecnica disponibile in linguaggi come C e C++ che permette di manipolare direttamente gli indirizzi di memoria. In Java questa tecnica **non esiste**: l'[[Incapsulamento]] è garantito a livello di linguaggio.

---

## Il problema in C++

In C++, i campi `private` possono essere bypassati manipolando i puntatori:

```cpp
class Player {
    int vita = 10;   // private!
public:
    char name = 's';
};

int main() {
    Player* p = new Player();
    int* raw = (int*)p;     // cast del puntatore: accesso diretto alla memoria
    cout << *raw;           // legge il campo private "vita"!
}
```

---

## Java è più sicuro

In Java **non** esiste aritmetica dei puntatori:
- Non si può fare il cast di un riferimento a un indirizzo numerico
- Non si può leggere/scrivere memoria arbitraria
- I [[Modificatori di Visibilità]] sono **rispettati** a livello di linguaggio

---

## Vedi anche

- [[Puntatore]] — Java nasconde i puntatori
- [[Incapsulamento]] — Java lo garantisce senza eccezioni
- [[Dereference]] — Java lo inserisce automaticamente
