# Computational Antibody Optimisation Against the Henipavirus Family

## Project Overview

This project extends my prior research on Henipavirus host attachment mechanisms (Oxford MBiochem thesis) into a computational antibody optimization pipeline. I systematically optimized known Henipavirus-neutralizing antibodies (HENV-26, 1E5, hu1F5) through structure-guided sequence modifications targeting improved stability and predicted binding affinity. I generated seventeen antibody variants using conservative amino acid substitutions at non-epitope-contact positions (stability-focused), selective modifications at epitope-contact residues (epitope-targeting), and combined pairwise testing of top performers. All variants were computationally validated using AlphaFold Multimer structure prediction, with performance compared to parent antibodies using PAE, pLDDT, and buried surface area metrics.

## Motivation
Henipaviruses (Nipah, Hendra) are BSL-4 pathogens with high fatality rates and no approved antivirals. Antibodies targeting conserved epitopes on viral glycoproteins offer a promising therapeutic approach.

## Methods

1. **Structural Analysis** — Align Henipavirus glycoproteins (Nipah G, Hendra G, Nipah F) using MAFFT, identify conserved regions using ConSurf conservation scoring. This analysis (a) validates that literature-identified epitopes are conserved across species, and (b) generates reference data for future structure-guided design iterations (e.g., Rosetta-based optimization).

2. **Epitope Selection** — Identify neutralizing epitopes from literature (Dong et al., Dang et al., Fan et al.). Validate conservation across Nipah/Hendra species using ConSurf analysis.

3. **Antibody Optimization** — Using PDB crystal structures, identify epitope-contact residues (distance < 4 Å from antigen). Design 17 antibody variants in three categories:
   - **Stability-focused (5 variants):** Conservative mutations in non-contact CDR and framework positions to improve predicted fold quality (pLDDT)
   - **Epitope-targeting (5 variants):** Conservative mutations at epitope-contact positions to optimize predicted binding affinity (PAE)
   - **Combined (4 variants):** Pairwise combinations of top-performing stability and epitope variants, designed after initial AlphaFold analysis
   - **Controls (3 variants):** Parent antibodies unmodified

5. **Validation** — AlphaFold Multimer structure predictions of antibody-antigen complexes (51 total predictions: 39 initial + 12 combined)

6. **Scoring** — PAE (predicted aligned error), pLDDT (confidence), buried surface area (BSA), germline identity (%)

## Design Strategy

This project uses an **adaptive, multi-stage validation approach**:

**Stage 1:** Design 13 variants targeting stability, epitope engagement, or as controls. Submit all to AlphaFold Multimer.

**Stage 2:** Analyze predictions. Rank stability variants by pLDDT and epitope variants by PAE. Identify top 2 performers in each category.

**Stage 3:** Design 4 combined variants testing all pairwise combinations of top stability + top epitope mutations. Re-submit to AlphaFold.

**Stage 4:** Compare combined variants to controls. Document which combinations synergize, which conflict, and mechanistic insights.

## Repository Structure

```
henipavirus-antibody-optimization/
├── data/
│   ├── pdb_structures/
│   ├── alignments/
│   └── conservation_scores/
├── notebooks/
│   ├── 01_literature_analysis.ipynb
│   ├── 02_structural_analysis.ipynb
│   └── 03_variant_design.ipynb
├── results/
│   ├── alphafold_predictions/
│   └── visualizations/
├── scripts/
│   ├── design_variants.py
│   └── parse_alphafold.py
└── docs/
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
