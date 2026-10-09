![Polymer data, materials, and machine learning](assets/github-cover.png)

# Polymer Data Sources for AI

A curated guide to public datasets, databases, benchmarks, and tools for polymer science and machine learning. It covers experimental properties, synthesis, simulation, spectroscopy, microscopy, and polymer representations.

> Some entries are downloadable datasets; others are portals, papers, or software that help build a dataset. Always check access terms, licenses, and source-data restrictions before reuse.

## Start with your task

| Goal | Useful starting points |
| --- | --- |
| Predict measured polymer properties | [OpenPoly](https://www.cjps.org/rc-pub/front/front-article/download/127254462/lowqualitypdf/OpenPoly:%20A%20Polymer%20Database%20Empowering%20Benchmarking%20and%20Multi-property%20Predictions.pdf), [PoLyInfo](https://polymer.nims.go.jp/), [Khazana](https://khazana.gatech.edu/dataset/), [PolyBench26](https://github.com/rlearsch/PolymerBenchmark2026) |
| Model copolymer composition or reactivity | [CoPolDB](https://www.copoldb.jp/copolym/), [CopDDB](https://github.com/hatanaka-lab/CopDDB), [PolySol](https://github.com/cstubb/PolySol/tree/main/data/csvs) |
| Explore virtual polymers or computed properties | [OPoly26](https://arxiv.org/abs/2512.23117), [PolyOmics](https://huggingface.co/datasets/yhayashi1986/PolyOmics), [PI1M](https://github.com/RUIMINMA1996/PI1M), [Open Macromolecular Genome](https://zenodo.org/records/7556992) |
| Identify polymers from spectra | [FTIR-Plastics](https://pmc.ncbi.nlm.nih.gov/articles/PMC11252596/), [VIS–NIR–SWIR library](https://doi.org/10.5281/zenodo.20180898), [NIMS Polymer NMR](https://mits.nims.go.jp/) |
| Study membranes and transport | [Bath permeability + FTIR](https://doi.org/10.15125/BATH-01709), [POINT2](https://github.com/Jiaxin-Xu/POINT2), [packaging water-vapor data](https://doi.org/10.5281/zenodo.18262441) |
| Work with images or environmental plastics | [GFRP/PP FM-SEM](https://pmc.ncbi.nlm.nih.gov/articles/PMC12907714/), [NIST SEM segmentation](https://catalog.data.gov/dataset/detection-limits-for-sem-image-segmentation), [LitChemPlast](https://pubs.acs.org/doi/full/10.1021/acs.estlett.4c00355) |

## Selected public releases (2026)

Recent examples with a public repository or data record. A public download does not always grant permission for commercial use or redistribution.

| Dataset | What it contains | Access and notes |
| --- | --- | --- |
| [PolyBench26](https://github.com/rlearsch/PolymerBenchmark2026) | Nearly 250,000 data points across eight properties, from experimental, DFT, and MD sources; includes multiple polymer architectures | Open benchmark; source data and redistribution terms vary |
| [Polymer membrane permeability and ATR-FTIR](https://doi.org/10.15125/BATH-01709) | 204 dense polymer membranes, up to six gas permeability labels, 860 spectra, and an ML notebook | University of Bath archive; CC BY 4.0 |
| [Nanoplastic disassembly in lipid membranes](https://doi.org/10.5281/zenodo.22936014) | Simulation inputs and final frames for nanoplastics interacting with lipid membranes | Zenodo record; check record for reuse terms |
| [PBLG nanofibrous membrane data](https://doi.org/10.5281/zenodo.22704383) | Optical, Raman, SEM, morphology, and mechanical data for ultrathin poly(γ-benzyl-L-glutamate) membranes | Zenodo; CC BY 4.0 |
| [VIS–NIR–SWIR microplastics library](https://doi.org/10.5281/zenodo.20180898) | 350–2500 nm reflectance spectra for PET, HDPE, PVC, LDPE, PP, and PS, with color and size metadata | Open Zenodo dataset |
| [Multilayer packaging water-vapor data](https://doi.org/10.5281/zenodo.18262441) | Water-vapor permeability data for 27 polymers | Public CSV; values combine new measurements and literature data |
| [RxnChainer generated polymers](https://doi.org/10.5281/zenodo.21878520) | Reaction-guided idealized polymer repeat units and reproducibility data | Non-commercial research use; commercial use needs written permission; structures are not experimentally validated |

## Resource catalog

### Experimental properties and materials databases

- [PoLyInfo](https://polymer.nims.go.jp/) — broad literature-derived property and processing records. Registration is required for use; bulk downloading and scraping are prohibited by its terms.
- [MatNavi](https://mits.nims.go.jp/) — NIMS materials and polymer databases, including characterization data.
- [OpenPoly](https://www.cjps.org/rc-pub/front/front-article/download/127254462/lowqualitypdf/OpenPoly:%20A%20Polymer%20Database%20Empowering%20Benchmarking%20and%20Multi-property%20Predictions.pdf) — curated experimental polymer-property benchmark.
- [Khazana](https://khazana.gatech.edu/dataset/) — computational and curated polymer properties for screening and prediction.
- [Polymer Genome](https://www.polymergenome.org/) — property prediction and design resources; access may require registration.
- [NanoMine](https://materialsmine.org/nm) — polymer nanocomposite data, metadata, and analysis tools.
- [CAMPUS Plastics](https://www.campusplastics.com/) and [MatWeb](https://www.matweb.com/) — grade-level engineering data; confirm supplier and use terms.

### Synthesis, copolymers, and recycling

- [CoPolDB](https://www.copoldb.jp/copolym/) — radical copolymerization systems, feed/composition data, and reactivity ratios.
- [CopDDB](https://github.com/hatanaka-lab/CopDDB) — copolymer descriptors and reactivity-ratio data.
- [PolySol](https://github.com/cstubb/PolySol/tree/main/data/csvs) — homopolymer and copolymer solubility records.
- [Block-copolymer SEM data](https://zenodo.org/records/13927939) and [PISA phase-prediction data](https://github.com/marioboley/PISA_ML) — morphology and phase classification.
- [TROPIC](https://pubs.rsc.org/en/content/articlehtml/2026/fd/d5fd00098j) — ring-opening polymerization thermodynamics for chemical-recycling research.
- [RxnChainer](https://doi.org/10.5281/zenodo.21878520) — reaction-guided generated polymers; non-commercial restrictions apply.

### Computation and benchmarks

- [OPoly26](https://arxiv.org/abs/2512.23117) — millions of DFT calculations on polymer-derived structures.
- [PolyOmics](https://huggingface.co/datasets/yhayashi1986/PolyOmics) — large-scale molecular-dynamics simulations and polymer properties.
- [PI1M](https://github.com/RUIMINMA1996/PI1M) — virtual polyimide structures and computed properties.
- [Open Macromolecular Genome](https://zenodo.org/records/7556992) — generated candidates constrained by synthetic accessibility.
- [POINT2](https://github.com/Jiaxin-Xu/POINT2) — multi-property benchmark for thermal, transport, and density prediction.
- [Carbon-m1](https://openreview.net/pdf?id=q6xm6PEhNv) — multimodal synthetic polymer dataset.
- [RadonPy](https://github.com/RadonPy/RadonPy), [ADEPT](https://github.com/sobinalosious/ADEPT), and [pylimer-tools](https://www.sciendo.com/article/10.5334/jors.609) — tools for generating or analyzing simulation data.

### Spectroscopy, microscopy, and environmental data

- [FTIR-Plastics](https://pmc.ncbi.nlm.nih.gov/articles/PMC11252596/) — FTIR spectra for six common plastics.
- [VIS–NIR–SWIR microplastics library](https://doi.org/10.5281/zenodo.20180898) — reflectance spectra and sample metadata.
- [NIMS Polymer NMR](https://mits.nims.go.jp/) — polymer NMR data and measurement metadata.
- [GFRP/PP FM-SEM](https://pmc.ncbi.nlm.nih.gov/articles/PMC12907714/) — SEM data for composite porosity and impregnation analysis.
- [NIST SEM Image Segmentation](https://catalog.data.gov/dataset/detection-limits-for-sem-image-segmentation) — images and segmentation labels.
- [LitChemPlast](https://pubs.acs.org/doi/full/10.1021/acs.estlett.4c00355) — chemicals measured in plastics, including additives and migrants.

### Literature and text mining

- [PolyIE](https://arxiv.org/abs/2311.07715) — information-extraction dataset from polymer materials papers.
- [ChemProps](https://pmc.ncbi.nlm.nih.gov/articles/PMC7955638/) — polymer name normalization API.
- [Open Polymer Challenge](https://arxiv.org/abs/2512.08896) — competition data and evaluation resources.
- Publisher APIs, [Crossref](https://www.crossref.org/documentation/retrieve-metadata/rest-api/), [PubMed](https://pubmed.ncbi.nlm.nih.gov/), and [arXiv](https://info.arxiv.org/help/api/index.html) can support literature-scale collection; access terms differ.

## Choose a polymer representation

| Representation | Good fit | Main limitation |
| --- | --- | --- |
| PSMILES | Regular repeat units and homopolymer models | Limited encoding of stochasticity and complex architectures |
| BigSMILES | Random, block, branched, and stochastic polymers | More complex tooling and canonicalization |
| PSELFIES | Robust generation of repeat-unit structures | Generated structures still need chemistry and feasibility checks |
| HELM | Peptides, oligonucleotides, and designed biomacromolecules | Best suited to biomacromolecule workflows |
| Graphs or 3D structures | Topology- or morphology-sensitive properties | Requires consistent chain construction and simulation metadata |

Keep the original representation alongside normalized structures. Record composition, molecular weight, dispersity, architecture, and processing history as separate fields.

## Before using a dataset

- Confirm license, access limits, and whether redistribution or commercial use is allowed.
- Record source URL, version, publication, extraction date, and processing steps.
- Preserve units, test conditions, uncertainty, and sample preparation details.
- Deduplicate records and prevent related polymers or literature records from leaking across train/test splits.
- Keep failed experiments and negative results when available.

## Contributing

To suggest a dataset, open an issue or pull request with its source link, scope, access terms, and publication or data record. Please distinguish downloadable data from portals, papers, and data-generation software.
