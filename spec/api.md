# API

The API exposes the crystal as a minimal, invariant interface.  
Every endpoint is a direct projection of the operator and preserves the full structural geometry of SUBIT.

The API does **not** introduce interpretation, heuristics, or metadata.  
It only transmits structure.

---

## Principles

### Minimality  
Each endpoint performs exactly one structural action.  
No endpoint may combine or decorate operations.

### Determinism  
Identical input always yields identical output.  
No randomness, no context dependence, no hidden state.

### Invariance  
All API responses preserve:

- trigram order  
- polarity symmetry  
- subject–vector–phase orthogonality  
- the 8‑state cycle  
- the 64‑state matrix  

Any endpoint that violates these invariants is invalid.

### Format Independence  
The API accepts and returns JSON, but the structure is medium‑independent.  
The JSON is only a container for invariant geometry.

---

## Endpoints

### `/subit`  
Reduces raw input to its invariant structural form.

**Input**
```
{
  "input": <any>
}
```

**Output**
```
{
  "trigram": "XYZ",
  "index": n,
  "color": "Color"
}
```

### `/archetype`  
Combines two trigrams into a 6‑bit archetype.

**Input**
```
{
  "primary": "XYZ",
  "secondary": "ABC"
}
```

**Output**
```
{
  "code": "XYZABC",
  "row": r,
  "col": c
}
```

### `/matrix`  
Returns the full 8×8 crystal matrix.

**Output**
```
{
  "matrix": [
    ["100100","100101", ...],
    ["101100","101101", ...],
    ...
  ]
}
```

### `/trigrams`  
Returns the canonical trigram list.

**Output**
```
{
  "trigrams": [
    {"code":"100","index":0,"color":"Blue"},
    ...
  ]
}
```

### `/colors`  
Returns the canonical color→trigram mapping.

**Output**
```
{
  "colors": [
    {"color":"Blue","trigram":"100","index":0},
    ...
  ]
}
```

### `/axes`  
Returns the semantic axes of the crystal.

**Output**
```
{
  "subject": ["ME","WE","YOU","THEY"],
  "vector": ["EAST","SOUTH","WEST","NORTH"],
  "phase": ["SPRING","SUMMER","AUTUMN","WINTER"]
}
```

### `/cycle`  
Returns the invariant 8‑state trigram cycle.

**Output**
```
{
  "cycle": ["100","101","110","111","011","010","001","000"]
}
```

---

## Error Conditions

The API rejects:

- invalid binary codes  
- reordered trigram lists  
- remapped colors  
- collapsed semantic axes  
- malformed matrix structures  
- any input that breaks invariants  

Errors return a minimal structural message:

```
{
  "error": "invalid-structure"
}
```

---

## Consequence

The API is not an application layer.  
It is the external surface of the operator itself.  
Every endpoint is a direct exposure of SUBIT’s internal geometry, ensuring that all clients—human or machine—interact with the same invariant crystal.
