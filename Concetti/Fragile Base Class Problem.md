> [!info] Definizione
> Il **Fragile Base Class Problem** descrive il rischio che **modifiche** in una superclasse rompano il comportamento delle sottoclassi, anche senza errori di compilazione.

---

## Perché e un problema

- Le sottoclassi dipendono da dettagli non visibili
- Ogni modifica alla base può introdurre bug nascosti

---

## Mitigazione

- Preferire la [[Composizione]] all'[[Ereditarietà]]
- Separare bene le responsabilità

---

## Vedi anche

- [[Composizione]]
- [[Ereditarietà]]
