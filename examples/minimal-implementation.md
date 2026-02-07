# Minimal Implementation

The minimal implementation expresses SUBIT‑crystal using the smallest possible set of executable rules.  
It contains no abstractions, no metadata, and no auxiliary logic.  
Every line is structurally necessary.

---

## Axiom

SUBIT(x) = structure(x)

This is the only operation.  
All implementation details are projections of this axiom.

---

## Core Components

### Polarity Extraction  
Input is reduced to six Yin/Yang bits.  
No preprocessing or interpretation is allowed.

### Trigram Resolution  
Bits 1–3 collapse into one of eight trigrams.  
This is the minimal semantic unit.

### Archetype Composition  
Bits 1–6 form a 6‑bit archetype.  
This is the complete structural identity.

### Matrix Position  
The first trigram selects the row.  
The second trigram selects the column.

---

## Minimal Pseudocode

```
subit(x):
    b = polarity(x)          # 6 bits
    t1 = b[0:3]              # primary trigram
    t2 = b[3:6]              # secondary trigram
    r = index(t1)            # row
    c = index(t2)            # column
    return { "code": b, "row": r, "col": c }
```

This is the entire implementation.  
Nothing can be removed; nothing can be added.

---

## Required Tables

### Trigram Order  
100, 101, 110, 111, 011, 010, 001, 000

### Color Mapping  
Blue, Green, Lime, Yellow, Orange, Red, Burgundy, Purple

### Matrix‑64  
The canonical 8×8 grid of archetypes.

These tables must be embedded exactly as defined.  
Reordering or renaming breaks invariants.

---

## Non‑Components

The minimal implementation does **not** include:

- parsing  
- validation  
- error handling  
- metadata  
- heuristics  
- interpretation  
- context memory  

All of these are external concerns.

---

## Consequence

The minimal implementation is the executable form of the operator.  
It is the smallest possible system that still produces the full crystal:  
trigrams, archetypes, matrix, palette, and semantic axes.  
Anything beyond this is not SUBIT.
