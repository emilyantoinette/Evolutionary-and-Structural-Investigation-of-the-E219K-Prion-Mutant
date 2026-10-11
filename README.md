# Evolutionary-and-Structural-Determinants-of-Prion-Protein-E219K-Polymorphism

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23299151.svg)](https://doi.org/10.5281/zenodo.23299151)

Evolutionary analysis, structural modelling and molecular dynamics simulations of the protective human PRNP E219K prion protein polymorphism.

Data, input files and analysis outputs for the study **"Evolutionary and Structural Determinants of Prion Resistance: Investigating the E219K Prion Protein Polymorphism"**.

## How to cite

If you use these files, please cite the associated publication:

> [Citation to be added on publication]

All files, including large trajectory files, are archived on Zenodo: https://doi.org/10.5281/zenodo.23299151

## About the study

The PRNP E219K polymorphism (p.Glu219Lys) is associated with reduced susceptibility to sporadic Creutzfeldt–Jakob disease. This study investigated its evolutionary origins and structural effects using three in silico approaches:

1. **Evolutionary analysis**: cross-species comparison of prion protein sequences to assess conservation at codon 219.
2. **Structural analysis**: comparison of wild-type and E219K prion protein structures.
3. **Molecular dynamics (MD)**: 1 ns simulations comparing the stability and flexibility of wild-type and E219K prion protein.

In file names, the E219K mutant is labelled **K219** (or **MUT**).

## Repository contents

### Evolutionary Analysis

| Dataset | Files |
|---|---|
| Preliminary vertebrate dataset (UniProt; human reference P04156 and 39 vertebrate sequences) | Sequences (FASTA), Clustal Omega alignment (.aln), Jalview project (.jvp), conservation export |
| Global mammalian dataset (214 sequences from PrPdex) | Sequences (FASTA), MAFFT alignment (FASTA), Jalview project (.jvp), conservation export |

### Structural Analysis

| File | Description |
|---|---|
| `WT_1QLX.pbd.pdb` | Wild-type prion protein structure (PDB 1QLX) |
| `WT PrP using 1QLX PyMOL pse.pse` | PyMOL session for wild-type |
| `K219 Mutation from PyMOL pbd.pdb` | E219K mutant structure, generated with the PyMOL mutagenesis wizard |
| `K219 Mutation from PyMOL pse.pse`, `K219.pse.pse` | PyMOL sessions for the E219K mutant |

### MD Analysis

| File(s) | Description |
|---|---|
| `ions.mdp`, `minim.mdp`, `nvt.mdp`, `npt.mdp`, `md.mdp` | GROMACS parameter files for each stage |
| `mdout.mdp` | Full parameter list written by GROMACS |
| `topol_WT.top`, `topol_MUT.top` | Topologies for wild-type and mutant systems |
| `*.cpt` | Checkpoint files from NVT, NPT and production runs |
| `*_rmsd.xvg` | Root mean square deviation (backbone) |
| `*_rmsf_ca.xvg` | Root mean square fluctuation per residue (Cα) |
| `*_rg.xvg` | Radius of gyration |
| `*_hbond.xvg` | Protein–protein hydrogen bonds |

### On Zenodo only (too large for GitHub)

| File | Description |
|---|---|
| `WT_md.trr`, `WT_md.xtc` | Production MD trajectory (1 ns), wild-type |
| `K219_md.trr` | Production MD trajectory (1 ns), E219K mutant |

Download from: https://doi.org/10.5281/zenodo.23299151

## Software

| Software | Version | Used for |
|---|---|---|
| GROMACS | 2023.3 | MD simulations and trajectory analysis |
| PyMOL | 3.0 | Structure visualisation and E219K mutagenesis |
| Clustal Omega | Web server, default parameters | Alignment of the vertebrate dataset |
| MAFFT | BLOSUM62, gap opening penalty 1.53, offset 0.0 | Alignment of the 214-species dataset |
| Jalview | 2.11.5.1 | Conservation, consensus and neighbour-joining analysis |
| Microsoft Excel | | Plotting |

MD settings: AMBER99SB-ILDN force field, SPC/E water, cubic box (1.0 nm), Na⁺ neutralisation, steepest-descent minimisation, 100 ps NVT (300 K, V-rescale), 100 ps NPT (1 bar, Parrinello–Rahman), 1 ns production with a 2 fs time step, PME electrostatics, 1.0 nm cutoffs and LINCS constraints. Full details are in the `.mdp` files and the paper's Methods.

## Notes

This was an independent project carried out with limited computing resources. Some intermediate files, including run input (`.tpr`) and structure (`.gro`) files, were not retained. These can be regenerated from the structures, topologies and parameter files provided here, following the Methods in the paper.
