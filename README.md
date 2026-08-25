# Deep Learning for Protein--Protein Binding-Site Prediction

A curated resource page for papers, code, webservers, datasets, and benchmarks related to **protein-protein binding-site (PPBS) prediction**.

> This repository accompanies the paper **“Deep Learning for Protein--Protein Binding Site Prediction: Formulations, Representations, and Learning Paradigms.”**  
> The manuscript is currently in preparation; the public paper/preprint link will be added here after release.

---

## Contents

- [Introduction](#scope)
- [Papers and Code](#papers-and-code)
  - [Partner-independent PPBS prediction](#partner-independent-ppbs-prediction)
  - [Partner-aware PPBS prediction](#partner-aware-ppbs-prediction)
  - [Residue-pair contact prediction](#residue-pair-contact-prediction)
  - [Hot-spot and mutation-effect prediction](#hot-spot-and-mutation-effect-prediction)
- [Datasets and Benchmarks](#datasets-and-benchmarks)
- [Citation](#citation)

---

## PPBS

Protein--protein binding-site (PPBS) prediction asks **where one protein binds another**: which residues, atoms, residue pairs, or surface regions participate in an interaction. This repository follows a formulation-centered organization because methods that are all called “interface prediction” often solve different computational tasks.

The list focuses on methods reviewed in the survey and closely related resources. Some tools span multiple formulations or address adjacent tasks such as docking-model scoring, peptide-binding-site prediction, interface validation, or mutation-effect prediction; these are marked where appropriate.

---

## Papers and Code

Code/server links are included when a public repository or webserver could be identified. `TBD` means that a direct public implementation link should be checked before posting the final repository.

### Partner-independent PPBS prediction

| Method | Year | Representation / architecture | Paper | Code / server |
|---|---:|---|---|---|
| **BiMba** | 2026 | Surface patches as 2D multi-channel grids + residue descriptors; bidirectional Vision Mamba | [Paper](https://academic.oup.com/bioinformatics/article/42/Supplement_1/btag243/8726357) | [Code](https://github.com/Azam-Shi/BiMba) |
| **DeepPPISP** | 2020 | Sequence features; CNN with local and global sequence context | [Paper](https://academic.oup.com/bioinformatics/article/36/4/1114/5564115) | [Code](https://github.com/CSUBioGroup/DeepPPISP) |
| **DeepProSite** | 2023 | ESMFold-predicted structures + PLM embeddings; topology-aware Graph Transformer | [Paper](https://academic.oup.com/bioinformatics/article/39/12/btad718/7453375) | [Code](https://github.com/WeiLab-Biology/DeepProSite) |
| **dMaSIF** | 2021 | Surface point cloud; fast differentiable molecular surface learning | [Paper](https://arxiv.org/abs/2012.04070) | [Code](https://github.com/FreyrS/dMaSIF) |
| **EquiPPIS** | 2023 | ESM2 features + E(3)-equivariant GNN on protein structures | [Paper](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1011435) | TBD |
| **GeoPep** | 2026 | ESM3 transfer learning with geometry-aware objectives for peptide-binding sites | [Search](https://scholar.google.com/scholar?q=GeoPep+geometry-aware+masked+language+model+protein-peptide+binding+site+prediction) | TBD |
| **GraphPBSP** | 2024 | ProstT5 embeddings + GAT + CNN + MLP | [Paper](https://pubmed.ncbi.nlm.nih.gov/39471921/) | TBD |
| **GraphPPIS** | 2022 | Residue graph with evolutionary/structural features; deep GCN | [Paper](https://academic.oup.com/bioinformatics/article/38/1/125/6366544) | [Code](https://github.com/biomed-AI/GraphPPIS) |
| **GraphRBF** | 2024 | Interpretable hierarchical geometric DL for protein--protein and protein--nucleic acid sites | [Paper](https://academic.oup.com/gigascience/article/doi/10.1093/gigascience/giae080/7824699) | [Code](https://github.com/Wssduer/GraphRBF) |
| **HCGNet** | 2024 | Hierarchical chemical and geometric feature interaction network | [Paper](https://pubmed.ncbi.nlm.nih.gov/38241104/) | [Code](https://github.com/xmed-lab/HCGNet) |
| **MaSIF-site** | 2020 | Molecular surface fingerprints; geodesic convolution over surface patches | [Paper](https://www.nature.com/articles/s41592-019-0666-6) | [Code](https://github.com/LPDI-EPFL/masif) |
| **PeSTo** | 2023 | Parameter-free geometric Transformer over atomic point clouds | [Paper](https://www.nature.com/articles/s41467-023-37701-8) | [Code](https://github.com/LBM-EPFL/PeSTo) |
| **PITHIA** | 2022 | Sequence/MSA features with attention | [Paper](https://www.mdpi.com/1422-0067/23/21/12814) | [Code](https://github.com/lucian-ilie/PITHIA) |
| **SaLT&PepPr** | 2023 | Fine-tuned ESM2 for interface prediction and peptide-guided degrader design | [Paper](https://www.nature.com/articles/s42003-023-05464-z) | [Code](https://github.com/programmablebio/saltnpeppr) |
| **ScanNet** | 2022 | Interpretable geometric DL over atomic/residue neighborhoods | [Paper](https://www.nature.com/articles/s41592-022-01490-7) | [Code](https://github.com/jertubiana/ScanNet) |
| **SCRIBER** | 2019 | Sequence-derived structural/evolutionary/physicochemical features; partner-type-specific outputs | [Paper](https://academic.oup.com/bioinformatics/article/35/14/i343/5529226) | TBD |
| **Seq-InSite** | 2024 | ProtT5 + MSA Transformer embeddings; MLP + BiLSTM ensemble | [Paper](https://academic.oup.com/bioinformatics/article/40/1/btad738/7517105) | [Code](https://github.com/lucian-ilie/Seq-InSite) / [Server](http://seq-insite.csd.uwo.ca/) |
| **SPPIDER** | 2007 | RSA-derived fingerprints with traditional ML classifiers | [Search](https://scholar.google.com/scholar?q=SPPIDER+prediction-based+fingerprints+protein-protein+interactions) | TBD |
| **xBind** | 2026 | ESM2 + optional AlphaFold2 structure + equivariant GNN; protein/DNA/RNA modes | [Paper](https://academic.oup.com/nar/article/54/W1/W337/8667315) | [Server](https://fusion.cs.vt.edu/xBind/) |

### Partner-aware PPBS prediction

| Method | Year | Representation / architecture | Paper | Code / server |
|---|---:|---|---|---|
| **BIPSPI** | 2019 | Sequence/structure features for a protein pair; XGBoost | [Paper](https://academic.oup.com/bioinformatics/article/35/3/470/5055586) | [Code](https://github.com/bioinsilico/BIPSPI) / [Server](http://bipspi.cnb.csic.es/) |
| **Pair-EGRET** | 2024 | Pair of 3D protein graphs + transformer-derived features; cross-attention | [Paper](https://academic.oup.com/bioinformatics/article/40/10/btae588/7808856) | [Code](https://github.com/1705004/Pair-EGRET) |
| **PAIRpred** | 2014 | Pairwise kernel SVM over sequence and structure kernels | [Search](https://scholar.google.com/scholar?q=PAIRpred+partner-specific+prediction+of+interacting+residues+from+sequence+and+structure) | [Server](http://comet.ucdavis.edu/pairpred/) |
| **PepNN** | 2022 | Reciprocal attention for protein--peptide binding-site prediction | [Paper](https://www.nature.com/articles/s42003-022-03398-4) | TBD |
| **PInet** | 2021 | Partner-specific surface point clouds with geometric, electrostatic, and hydrophobic features | [Paper](https://academic.oup.com/bioinformatics/article/37/17/2580/6162157) | [Code](https://github.com/FTD007/PInet) |
| **Seq2Bind** | 2025 | Fine-tuned PLMs in a Siamese sequence-pair architecture; alanine scanning for critical residues | [Paper](https://academic.oup.com/nargab/article/7/4/lqaf154/8340159) | [Server](https://agrivax.onrender.com/seq2bind/scan) |
| **SPPIDER-seq** | 2026 | ESM2 embeddings + cross-attention for partner-aware residue-level site prediction | [Paper](https://academic.oup.com/bioinformatics/article/42/7/btag388/8707840) | [Code](https://github.com/aporollo-lab/SPPIDER-seq) |

### Residue-pair contact prediction

| Method | Year | Representation / architecture | Paper | Code / server |
|---|---:|---|---|---|
| **CDPred** | 2022 | 2D attention-based residual network for inter-chain distance/contact maps | [Paper](https://www.nature.com/articles/s41467-022-34600-2) | [Code](https://github.com/BioinfoMachineLearning/CDPred) |
| **DeepHomo2.0** | 2023 | DCA + MSA Transformer + monomer structure for homodimer contact prediction | [Search](https://scholar.google.com/scholar?q=DeepHomo2.0+protein-protein+contact+prediction+homodimers) | TBD |
| **DeepInter** | 2023 | PLM-derived features + triangle-aware modules | [Paper](https://www.nature.com/articles/s42256-023-00741-2) | TBD |
| **DeepInteract** | 2022 | Geometric Transformer + dilated ResNet over pairwise interaction tensor | [Paper](https://arxiv.org/abs/2110.02423) | [Code](https://github.com/BioinfoMachineLearning/DeepInteract) |
| **DeepSSInter** | 2026 | ESM2 + SaProt representations; ResNet-Inception and triangle-aware modules | [Paper](https://onlinelibrary.wiley.com/doi/10.1002/pro.70667) | [Code](https://github.com/huang-laboratory/DeepSSInter/) |
| **DRN-1D2D_Inter** | 2023 | Sequence-only PLM features + dimensional hybrid residual networks | [Paper](https://academic.oup.com/bib/article/24/2/bbad039/7033302) | [Code](https://github.com/ChengfeiYan/DRN-1D2D_Inter) |
| **GLINTER** | 2022 | Rotationally invariant graph representation + MSA Transformer information | [Paper](https://academic.oup.com/bioinformatics/article/38/4/947/6424887) | [Code](https://github.com/zw2x/glinter) |
| **IIGRL** | 2024 | GNN with intra-graph mutual information and inter-graph propagation | [Search](https://scholar.google.com/scholar?q=IIGRL+protein+interface+prediction+GNN+intra-graph+mutual+information) | TBD |
| **NeiA** | 2020 | Hybrid GNN + CNN; 2D dense prediction over residue-pair maps | [Paper](https://arxiv.org/abs/2007.09334) | TBD |
| **PLMGraph-Inter** | 2024 | PLM embeddings in geometric graphs with GVP encoders | [Paper](https://elifesciences.org/articles/92184) | [Data](https://github.com/ChengfeiYan/PLMGraph-Inter/tree/main/data) |
| **PPLM / PPLM-PPI / PPLM-Contact** | 2026 | Paired-sequence language model for interaction, affinity, and contact/interface tasks | [Paper](https://www.nature.com/articles/s41467-026-70457-5) | [Code](https://github.com/junliu621/PPLM) / [Server](https://zhanggroup.org/PPLM/) |
| **SASNet** | 2019 | Siamese 3D CNN over voxelized atomic surfacelets | [Paper](https://arxiv.org/abs/1807.01297) | [Code/data](https://github.com/drorlab/DIPS) |

### Hot-spot and mutation-effect prediction

| Method | Year | Representation / architecture | Paper | Code / server |
|---|---:|---|---|---|
| **DDMut-PPI** | 2024 | Interface residue graph with ProtT5 node embeddings; ΔΔG prediction | [Paper](https://academic.oup.com/nar/article/52/W1/W207/7680621) | [Server/API](https://biosig.lab.uq.edu.au/ddmut_ppi) |
| **Embed-1dCNN** | 2023 | Pretrained sequence embeddings + 1D CNN for hot-spot classification | [Search](https://scholar.google.com/scholar?q=Embed-1dCNN+protein+protein+hotspot+prediction+pretrained+embeddings) | TBD |
| **PPI-hotspots with PLMs** | 2024 | ESM2/PLM representations for sparse-data hot-spot prediction | [Search](https://scholar.google.com/scholar?q=Sargsyan+Lim+2024+PPI+hotspots+protein+language+models) | TBD |

---

## Datasets and Benchmarks

| Resource | Role | Link |
|---|---|---|
| **PDB** | Primary archive of experimentally determined structures | https://www.rcsb.org/ |
| **DB3 / DB4 / DB5 / DB5.5** | Protein--protein docking benchmarks with bound/unbound structures | https://zlab.umassmed.edu/benchmark/ |
| **DIPS** | Large-scale pairwise interface dataset mined from PDB complexes | https://github.com/drorlab/DIPS |
| **DIPS-Plus** | Enhanced DIPS with residue- and atom-level features | https://github.com/BioinfoMachineLearning/DIPS-Plus |
| **PINDER** | Large interaction dataset with interface-aware leakage control | https://github.com/pinder-org/pinder |
| **MaSIF-site / MaSIF-search** | Surface-based PPBS and complementarity-search datasets | https://github.com/LPDI-EPFL/masif |
| **Dset series** | Classic residue-level PPBS benchmarks | TBD |
| **SAbDab** | Antibody--antigen structural database | https://opig.stats.ox.ac.uk/webapps/newsabdab/sabdab/ |
| **AlphaFold DB** | Predicted monomer structures | https://alphafold.ebi.ac.uk/ |
| **AlphaFold Atlas** | Predicted protein-complex resource | TBD |
| **SKEMPI 2.0** | Mutation-effect / ΔΔG benchmark | https://life.bsc.es/pid/skempi2/ |
| **PDBsum** | Interface diagrams and structural summaries | https://www.ebi.ac.uk/thornton-srv/databases/pdbsum/ |
| **jsPISA** | Assembly and interface analysis | https://www.ccp4.ac.uk/jsPISA/ |
| **IntAct** | Curated molecular interaction database | https://www.ebi.ac.uk/intact/ |
| **BioGRID** | Curated protein and genetic interaction database | https://thebiogrid.org/ |


