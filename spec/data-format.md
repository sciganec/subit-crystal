# Data Format

The crystal uses a minimal, canonical data format that preserves structural invariants across all layers of representation.  
Every file, table, or mapping is a projection of the same underlying 6‑bit geometry.

---

## Principles

### Minimality  
Only structural information is stored.  
No metadata, annotations, or auxiliary fields are permitted unless they encode invariant structure.

### Determinism  
Every representation must map unambiguously to:

- a trigram (3‑bit)  
- an archetype (6‑bit)  
- a matrix position (row, column)  

### Invariance  
The format must preserve:

- trigram order  
- polarity symmetry  
- subject–vector–phase orthogonality  
- the 8‑state cycle  
- the 64‑state matrix  

Any format that breaks these invariants is invalid.

---

## Core Data Types

### Trigram  
A trigram is represented as:

- a 3‑bit binary string  
- an index 0–7  
- a spectral color  
- an optional symbolic name  

Example:

```
{
  "code": "100",
  "index": 0,
  "color": "Blue",
  "name": "T100"
}
```

### Archetype  
An archetype is represented as:

- a 6‑bit binary string  
- primary trigram (first 3 bits)  
- secondary trigram (last 3 bits)  
- row index 0–7  
- column index 0–7  

Example:

```
{
  "code": "100111",
  "primary": "100",
  "secondary": "111",
  "row": 0,
  "col": 3
}
```

### Matrix  
The 64‑state matrix is represented as an 8×8 array of 6‑bit codes.  
Rows follow trigram order; columns follow the same order.

Example:

```
[
  ["100100","100101","100110","100111","100011","100010","100001","100000"],
  ["101100","101101","101110","101111","101011","101010","101001","101000"],
  ...
]
```

---

## Allowed Formats

### JSON  
Preferred for machine‑readable structures.  
Must use explicit fields for codes, indices, and colors.

### CSV  
Allowed for tabular representations of the 64‑state matrix.  
Each cell contains a 6‑bit code.

### Markdown  
Allowed for documentation, tables, and human‑readable matrices.  
Must preserve trigram order and binary codes exactly.

### Plain Text  
Allowed for minimal lists of codes or mappings.  
Must not introduce ambiguity.

---

## Forbidden Formats

- Any format that reorders trigrams  
- Any format that renames colors or remaps them  
- Any format that collapses subject/vector/phase  
- Any format that introduces non‑structural metadata  
- Any format that alters binary codes  

These violate invariants and cannot represent the crystal.

---

## Structural Guarantees

A valid data format must guarantee:

- 1:1 mapping between binary codes and semantic states  
- stable indexing across all files  
- identical trigram order in every representation  
- reversible transformation between formats  

If a transformation cannot be reversed without loss, it is invalid.

---

## Consequence

The data format is not a convenience layer.  
It is the minimal external expression of the crystal’s internal logic.  
Every valid file is a faithful projection of the same invariant structure.  
Nothing may be added, removed, or rearranged without breaking the operator.
