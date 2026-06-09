# Structural Phylogenetic Signal in the Transeurasian Languages

Data and code for the study testing whether dependency-based structural 
features carry recoverable genealogical signal in the Transeurasian 
languages (Turkic, Mongolic, Tungusic, Japonic, Koreanic) at deep time depth.

## Summary
Across 28 languages (25 Transeurasian + 3 outgroups), 29 structural features 
were extracted from Universal Dependencies treebanks, tested for phylogenetic 
signal under four competing reference topologies, and used for Bayesian 
(MrBayes) and Neighbor-Joining tree inference. At this time depth the signal 
separates broad typological profiles but does not reconstruct the family's 
internal genealogy.

## Files

### scripts/
- `extract_features.py` — extract 29 structural features from UD treebanks
- `make_nexus.py` — discretize features (B=4) and write MrBayes NEXUS files
- `signal_and_trees.R` — phylogenetic signal tests (Pagel's λ, Blomberg's K) 
  under four topologies, and Neighbor-Joining trees

### data/
- `features_final_29.csv` — the 29-feature matrix (28 languages)
- `signal_H1.csv`–`signal_H4.csv` — signal-test results under topologies H1–H4

### trees/
- `mb_strict_B4.nex`, `mb_relaxed_B4.nex` — MrBayes input (discretized matrices)
- `mb_strict_B4.nex.con.tre`, `mb_relaxed_B4.nex.con.tre` — Bayesian consensus trees
- `tree_strict.nwk`, `tree_relaxed.nwk` — Neighbor-Joining trees

## Reproducing
1. `python extract_features.py` → features_final_29.csv
2. `Rscript signal_and_trees.R` → signal_H1–H4.csv + NJ trees
3. `python make_nexus.py` → mb_strict_B4.nex, mb_relaxed_B4.nex
4. `mb mb_strict_B4.nex` / `mb mb_relaxed_B4.nex` → Bayesian consensus trees

## Treebanks
The 15 existing UD treebanks are available from https://universaldependencies.org.
The 13 newly built (GDUD) treebanks for Tungusic and Mongolic languages are 
scheduled for release in UD v2.19 (November 2026).

## Citation
Li, W. & Liu, H. (2026). Structural Phylogenetic Signal Fails at Deep Time: 
A Bayesian Treebank Analysis of the Transeurasian Languages.
