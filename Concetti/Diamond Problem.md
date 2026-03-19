> [!info] Definizione
> Il **Diamond Problem** e un problema dell'ereditarieta multipla tra classi: due percorsi di ereditarieta portano alla stessa superclasse, creando **ambiguita** su quale implementazione usare.

---

## Perche succede

Quando una classe eredita da due classi che ereditano dalla stessa base, si crea un "diamante" nella gerarchia.

---

## Come si evita

- Java evita il problema **vietando** ereditarieta multipla tra classi
- In C++ esiste l'[[ereditarietà virtuale]]
- Le [[interfaccia|interfacce]] non portano stato, quindi non introducono ambiguita

---

## Vedi anche

- [[Ereditarietà]]
- [[ereditarietà virtuale]]
- [[Mixins]]
- [[Traits]]
