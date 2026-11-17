# Tox21 × JUMP: a Cell Painting pilot

Work in progress. Phase 1 (data matching) done; Phase 2 (a structure-only
baseline model) to follow.

The question was how many Tox21 compounds with a mitochondrial-toxicity label
(SR-MMP) also appear in the JUMP Cell Painting dataset, and how carefully the compunds have to be matched.

**Phase 1 result:** Of ~5,900 SR-MMP-labelled Tox21 compounds, 1,685 appear
in JUMP when matching on the InChIKey connectivity block, but only 1,087 on
the full key. The gap comes from stereochemistry and salt forms recorded
differently in the two databases. Of the 1,685 matches, 249 are labelled
toxic.

## Data (downloaded in the notebook, not committed)
- Tox21 (DeepChem mirror)
- JUMP compound metadata (jump-cellpainting/datasets)
