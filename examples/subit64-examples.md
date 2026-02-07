# SUBIT‑64 Examples

Concrete demonstrations of how SUBIT operates on real inputs.  
Each example shows polarity extraction, trigram resolution, archetype formation, and matrix placement.  
All examples preserve the canonical trigram order and 6‑bit geometry.

---

## Example 1 — Raw Binary Input

**Input**
```
110010
```

**Process**
- Primary trigram: 110 (Lime)
- Secondary trigram: 010 (Red)
- Row index: 2
- Column index: 5

**Output**
```
{
  "code": "110010",
  "primary": "110",
  "secondary": "010",
  "row": 2,
  "col": 5
}
```

---

## Example 2 — Symbolic Input

**Input**
```
"north‑summer"
```

**Process**
- SUBIT extracts polarity pattern → 101111  
- Primary trigram: 101 (Green)  
- Secondary trigram: 111 (Yellow)

**Output**
```
{
  "code": "101111",
  "primary": "101",
  "secondary": "111",
  "row": 1,
  "col": 3
}
```

---

## Example 3 — Sensory Input (Abstracted)

**Input**
```
{ "signal": [0.82, 0.13, 0.44, 0.91, 0.27, 0.05] }
```

**Process**
- SUBIT reduces to polarity → 111001  
- Primary trigram: 111 (Yellow)  
- Secondary trigram: 001 (Burgundy)

**Output**
```
{
  "code": "111001",
  "primary": "111",
  "secondary": "001",
  "row": 3,
  "col": 6
}
```

---

## Example 4 — Textual Input

**Input**
```
"we move toward clarity"
```

**Process**
- SUBIT extracts structural polarity → 011100  
- Primary trigram: 011 (Orange)  
- Secondary trigram: 100 (Blue)

**Output**
```
{
  "code": "011100",
  "primary": "011",
  "secondary": "100",
  "row": 4,
  "col": 0
}
```

---

## Example 5 — Archetype Lookup

**Input**
```
{ "primary": "000", "secondary": "111" }
```

**Process**
- Combine → 000111  
- Row index: 7  
- Column index: 3

**Output**
```
{
  "code": "000111",
  "primary": "000",
  "secondary": "111",
  "row": 7,
  "col": 3
}
```

---

## Example 6 — Matrix Position to Archetype

**Input**
```
row = 0
col = 7
```

**Process**
- Row trigram: 100  
- Column trigram: 000  
- Archetype: 100000

**Output**
```
{
  "code": "100000",
  "primary": "100",
  "secondary": "000"
}
```

---

## Example 7 — Full SUBIT Flow

**Input**
```
"subjective‑shift‑toward‑resolution"
```

**Process**
- Polarity extraction → 001110  
- Primary trigram: 001 (Burgundy)  
- Secondary trigram: 110 (Lime)

**Output**
```
{
  "code": "001110",
  "primary": "001",
  "secondary": "110",
  "row": 6,
  "col": 2
}
```

---

## Consequence

These examples demonstrate that SUBIT always performs the same act:  
extract polarity → resolve trigrams → form archetype → locate in the matrix.  
The input domain may vary, but the structural output is always invariant.
