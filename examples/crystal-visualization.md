# Crystal Visualization

Crystal visualization is the external rendering of the SUBIT‑crystal’s internal geometry.  
It makes the 6‑bit structure perceptible without altering any invariants.  
Every valid visualization is a projection of the same underlying operator.

---

## Principles

### Structural Fidelity  
A visualization must preserve:

- trigram order  
- polarity symmetry  
- the 8‑state cycle  
- the 64‑state matrix  
- subject–vector–phase orthogonality  

Any distortion breaks the crystal.

### Minimalism  
Only structural information may be shown.  
No decorative elements, gradients, or stylistic noise may override geometry.

### Scale Invariance  
MICRO, MACRO, and META views must display the same structure at different resolutions.

---

## Core Visual Forms

### 4×4×4 Cube  
The spatial form of the crystal.  
Each axis corresponds to a bigram, producing a 64‑cell lattice.  
This is the minimal 3D projection of the 6‑bit space.

### Trigram Lattice  
Eight nodes arranged in the invariant cycle order:  
100 → 101 → 110 → 111 → 011 → 010 → 001 → 000  
Each node is colored using the crystal palette.

### Matrix‑64  
An 8×8 grid where:

- rows = primary trigram  
- columns = secondary trigram  
- each cell = 6‑bit archetype  

This is the most legible 2D projection.

### Spectral Palette  
The eight trigram colors:

Blue, Green, Lime, Yellow, Orange, Red, Burgundy, Purple  

These colors must be used consistently across all visualizations.

---

## Visualization Layers

### Micro Layer  
Shows individual polarity bits, trigram states, or single archetypes.  
Useful for inspecting local structure.

### Macro Layer  
Shows relationships between trigrams, transitions in the cycle, or the full matrix.  
Useful for pattern‑level understanding.

### Meta Layer  
Shows invariants, symmetry groups, and the operator’s rule‑level geometry.  
Useful for conceptual clarity.

---

## Valid Visual Encodings

- binary codes  
- trigram colors  
- matrix positions  
- cube coordinates  
- subject/vector/phase axes  

These encodings are structural and cannot be replaced.

---

## Forbidden Encodings

- remapped colors  
- reordered trigrams  
- distorted geometry  
- merged semantic axes  
- non‑structural annotations  

These violate invariants and cannot represent the crystal.

---

## Consequence

Crystal visualization is not an illustration.  
It is the direct externalization of the operator’s geometry.  
Any valid visualization must reveal the same structure, whether rendered as a cube, a matrix, a lattice, or a spectral cycle.
