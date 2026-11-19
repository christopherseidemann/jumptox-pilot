# Tox21 × JUMP: a Cell Painting pilot

Work in progress. Phase 1 (linking compound identities) is done; Phase 2 (a
structure-only baseline model) follows.

This project follows the question: how many Tox21 compounds carrying a mitochondrial-toxicity label
(SR-MMP) also appear in the JUMP Cell Painting dataset, and how much does the
matching criteria change the answer?

## Phase 1 result

Of 5,730 Tox21 compounds with an SR-MMP label, 1,625 appear in JUMP
when matching on the InChIKey connectivity block, and 1,050 when the full key
must agree. 240 of the 1,625 are active in SR-MMP (14.8%, against 15.9% across all
labelled compounds, so the matched subset is not enriched).

I first assumed the 575-compound difference came from salt forms, but it does not!
Standardising the JUMP side the same way as the Tox21 side changes the count by
zero. The difference is 519 compounds where Tox21 specifies stereochemistry and
JUMP records none, and 56 that differ only in protonation state.

Counting note: the raw file has 5,914 usable records, but 184 of them are duplicate
structures, so compounds are de-duplicated before matching. "Active in SR-MMP" means
the compound disturbed the mitochondrial membrane potential in that assay -> not that
it is toxic.

## Data

Downloaded by the notebook, not committed:

- Tox21: DeepChem mirror (`deepchem/deepchem`, `datasets/tox21.csv.gz`)
- JUMP compound metadata (`jump-cellpainting/datasets`, `metadata/compound.csv.gz`)

Both are pulled from the repositories default branch, so numbers can shift if those
files are updated. The results above were produced on 18 November 2026.


## Run

```
pip install -r requirements.txt
```

Then open `tox21_jump_pilot.ipynb` and run it top to bottom

Self-directed pilot project, Claude was used for code review and exploring RDKit best practices.