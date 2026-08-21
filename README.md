# Computational Antibody Design Against the Henipavirus Family

## Project Overview

This project extends my prior research on Henipavirus host attachment mechanisms (Oxford MBiochem thesis) into a computational antibody optimization pipeline. I systematically optimized three known Henipavirus-neutralizing antibodies (HENV-26, 1E5, hu1F5) through structure-guided sequence modifications targeting improved manufacturability, stability, and epitope engagement. I generated eight antibody variants using conservative amino acid substitutions, CDR length optimization, and human germline framework scaffolding. All variants were computationally validated using AlphaFold Multimer structure prediction, with performance compared to parent antibodies using PAE, pLDDT, and buried surface area metrics.

## Motivation
Henipaviruses (Nipah, Hendra) are BSL-4 pathogens with high fatality rates and no approved antivirals. Antibodies targeting conserved epitopes on viral glycoproteins offer a promising therapeutic approach.

## Methods
1. **Structural analysis** — Align Henipavirus glycoproteins, identify conserved regions
2. **Epitope selection** — Use ConSurf conservation scoring + literature
3. **Antibody design** — CDR grafting from human germline (IMGT)
4. **Validation** — AlphaFold Multimer predictions of antibody-antigen complexes
5. **Scoring** — PAE, pLDDT confidence, buried surface area

## Repository Structure

```
henipavirus-antibody-design/
├── README.md
├── PROGRESS.md
├── data/
│   ├── structures/          # PDB files
│   └── sequences/           # FASTA, MSAs
├── notebooks/
│   ├── 01_structural_analysis.ipynb
│   ├── 02_antibody_design.ipynb
│   └── 03_validation_visualization.ipynb
├── results/
│   ├── alignments/
│   ├── predictions/
│   └── visualizations/
├── scripts/
│   ├── download_structures.sh
│   └── colabfold_wrapper.py
└── docs/
    └── methods.md
```      
## Getting Started
1. Clone this repo: `git clone https://github.com/yourusername/henipavirus-antibody-design.git`
2. Install dependencies: `pip install -r requirements.txt`
3. Run notebooks in order (01 → 02 → 03)

## Key Results
(Will update as project progresses)

## Future Directions
- Wet-lab validation (binding assays, neutralization tests)
- Affinity maturation if initial designs show promise
- Exploration of F protein epitopes

## References
- Dong et al. (2020) — Diverse sites on Henipavirus RBP
- Fan et al. (2024) — Cross-neutralizing antibody 1E5
- Dang et al. (2019) — F glycoprotein antibodies

---

**Author:** Jakob Marshall  
**Status:** In Progress (Week 1: Literature review & structural analysis)  
**Last Updated:** August 26, 2026
