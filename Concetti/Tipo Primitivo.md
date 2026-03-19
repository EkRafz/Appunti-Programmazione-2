

> [!info] Definizione
> I **tipi primitivi** in Java sono i tipi di dato fondamentali integrati nel linguaggio. Non sono [[Oggetto|oggetti]], vengono allocati nello [[Stack]] e passati per **[[Passaggio per Copia|copia]]**.

---

## Tipi primitivi di Java

| Tipo | Descrizione | Default | Esempio |
|---|---|---|---|
| `int` | Intero (32 bit) | `0` | `int health = 20;` |
| `boolean` | Vero/falso | `false` | `boolean alive = true;` |
| `double` | Decimale (64 bit) | `0.0` | `double power = 4.0;` |
| `float` | Decimale (32 bit) | `0.0f` | `float speed = 2.0f;` |
| `char` | Carattere (16 bit) | `'\0'` | `char c = 'A';` |
| `long` | Intero lungo (64 bit) | `0L` | `long big = 100L;` |
| `byte` | Intero piccolo (8 bit) | `0` | `byte b = 127;` |
| `short` | Intero medio (16 bit) | `0` | `short s = 1000;` |

---

## Primitivi vs Oggetti

| | Primitivo | [[Oggetto]] |
|---|---|---|
| Allocazione | [[Stack]] | [[Heap]] |
| Passaggio | Per [[Passaggio per Copia|copia]] | Per [[Passaggio per Riferimento|riferimento]] |
| Default | `0`, `false`, etc. | `null` |
| Esempio | `int x = 5;` | `Player p = new Player();` |

---

## Vedi anche

- [[Stack]] — dove risiedono i primitivi
- [[Passaggio per Copia]] — come vengono passati ai metodi
- [[Valore null]] — il default per i tipi non-primitivi
