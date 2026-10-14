![Polymer data, materials, and machine learning](assets/github-cover.png)

# Polymer Data Sources for AI

A curated guide to public datasets, databases, benchmarks, and tools for polymer science and machine learning. It covers experimental properties, synthesis, simulation, spectroscopy, microscopy, and polymer representations.

> Some entries are downloadable datasets; others are portals, papers, or software that help build a dataset. Always check access terms, licenses, and source-data restrictions before reuse.

Browse the [dataset comparison](#dataset-comparison), [additional dataset sizes](#additional-dataset-sizes), [2026 releases](#selected-public-releases-2026), or the [resource catalog](#resource-catalog).

## Start with your task

| Goal | Useful starting points |
| --- | --- |
| Predict measured polymer properties | [OpenPoly](https://www.cjps.org/rc-pub/front/front-article/download/127254462/lowqualitypdf/OpenPoly:%20A%20Polymer%20Database%20Empowering%20Benchmarking%20and%20Multi-property%20Predictions.pdf), [PoLyInfo](https://polymer.nims.go.jp/), [Khazana](https://khazana.gatech.edu/dataset/), [PolyBench26](https://github.com/rlearsch/PolymerBenchmark2026) |
| Model copolymer composition or reactivity | [CoPolDB](https://www.copoldb.jp/copolym/), [CopDDB](https://github.com/hatanaka-lab/CopDDB), [PolySol](https://github.com/cstubb/PolySol/tree/main/data/csvs) |
| Explore virtual polymers or computed properties | [OPoly26](https://arxiv.org/abs/2512.23117), [PolyOmics](https://huggingface.co/datasets/yhayashi1986/PolyOmics), [PI1M](https://github.com/RUIMINMA1996/PI1M), [Open Macromolecular Genome](https://zenodo.org/records/7556992) |
| Identify polymers from spectra | [FTIR-Plastics](https://pmc.ncbi.nlm.nih.gov/articles/PMC11252596/), [VIS–NIR–SWIR library](https://doi.org/10.5281/zenodo.20180898), [NIMS Polymer NMR](https://mits.nims.go.jp/) |
| Study membranes and transport | [Bath permeability + FTIR](https://doi.org/10.15125/BATH-01709), [POINT2](https://github.com/Jiaxin-Xu/POINT2), [packaging water-vapor data](https://doi.org/10.5281/zenodo.18262441) |
| Work with images or environmental plastics | [GFRP/PP FM-SEM](https://pmc.ncbi.nlm.nih.gov/articles/PMC12907714/), [NIST SEM segmentation](https://catalog.data.gov/dataset/detection-limits-for-sem-image-segmentation), [LitChemPlast](https://pubs.acs.org/doi/full/10.1021/acs.estlett.4c00355) |

## Dataset comparison

The comparison below expands the supplied reference table with source links and more explicit size definitions. **Checked: 2026-10-14.** Counts describe the linked publication, release, or dated database snapshot; they are not live totals. `k` = thousand and `M` = million. A structure, sample, property value, trajectory, and document are different counting units, so these numbers must not be added into a single dataset total.

**Modality** describes the available representation; **collection** describes how records were obtained; **annotation** distinguishes experimental, computed, predicted, and absent property labels. **Purpose** lists potential learning uses, rather than promising a ready-made pretraining split. The size groups are browsing aids: a resource can contain both a small labeled set and a large candidate library. Estimates available only in the supplied table are explicitly marked **unverified**; its numbered references were not supplied.

### Small-scale datasets and focused databases

| Dataset | Modality | Collection | Annotation | Scale and counting unit | Purpose | Details and access |
| --- | --- | --- | --- | --- | --- | --- |
| [Crystal16 Solubility](https://github.com/mona2442/Polymer-Solubility-Data_Crystal16) | Polymer/solvent names and SMILES; solubility curves | Turbidity experiments; processed cooling cycles | Experimental solubility labels | Reference table: **<100**, **unverified**; counting unit not specified | Solubility prediction | Repository provides `crystal16_data.csv`, structure lookup tables, and raw data. Curve points must be counted separately from polymer–solvent systems; no dataset license is stated in the README. |
| [PPPdb / 3PDB](https://pppdb.uchicago.edu/) | Names; structured χ, Tg, and cloud-point records | Literature extraction and curation | Property labels; coverage varies by table | Total not stated on the landing page; reference table: **≈500**, **unverified** | Property prediction; phase behavior | CHiMaD database and predictor. The [Tg table](https://pppdb.uchicago.edu/tg) includes source references; sizes of the separate χ, Tg, and cloud-point tables should be reported individually. |
| [RadonPy study dataset](https://doi.org/10.1038/s41524-022-00906-4) | Repeat-unit SMILES; MD structures, trajectories, and properties | Automated all-atom MD | Computed labels | **1,138** target homopolymers; **1,070** with ≥1 successful run; **1,001** with ≥3 successful runs | Property prediction; simulation-to-experiment transfer | The **2022 study calculated 15 properties**. [RadonPy](https://github.com/RadonPy/RadonPy) is the generating software; its capabilities and newer PolyOmics releases are separate from this study's sample count. |
| [CHEMnetBASE — Polymers: A Property Database](https://poly.chemnetbase.com/) | Names, structures, and tabulated properties | Commercial reference compilation | Curated property information | **>1,100 polymers**, per the [publisher](https://librarianresources.taylorandfrancis.com/product-info/digital-products/databases/chemnetbase/) | Property lookup; retrieval | A subscription/reference database; the polymer count does not describe the entire CHEMnetBASE collection or an openly downloadable training set. |
| [ToPoRg-1342](https://doi.org/10.5281/zenodo.10672433) | Coarse-grained topology graphs and single-chain properties | Coarse-grained simulations of diverse architectures | Computed radius-of-gyration labels | **1,342 coarse-grained polymers**, confirmed by the [author's resource page](https://webbgroup.princeton.edu/resources) | Topology-aware property prediction; generative modeling | The dataset supplies simulation labels; the associated VAE is a learning method, not the measurement source. A larger ToPoRg-18k release is listed below. |
| [Polymer Gas Separation Membrane Database](https://research.csiro.au/virtualscreening/membrane-database-polymer-gas-separation-membranes/) | Polymer names; gas-permeability records | Experimental literature; curation | Partially labeled across gases | Historical database: **>1,500 data points**; **1,378 entries** after six-gas filtering in the [2021 study](https://doi.org/10.1016/j.memsci.2021.119207) | Permeability/selectivity prediction; missing-label studies | The filtered snapshot was downloaded on **2020-06-11**. Keep measured and imputed values separate; entries can repeat a polymer under different conditions. |
| [PolyID training data](https://doi.org/10.1021/acs.macromol.3c00994) | Monomer/polymer SMILES, graphs, and properties | Existing databases and experimental literature | Experimental property labels, with incomplete coverage | **1,791 unique training polymers** across **8 properties**; separately **≈1.4M generated screening candidates** | Multi-property prediction; biobased polymer screening | Training data are provided in the paper's XLSX supporting information; [code](https://github.com/NatLabRockies/polyID) and the [predictor](https://polyid.nrel.gov/) are separate resources. The candidate-library size is not an experimental-label count. |

### Medium-scale datasets and hybrid benchmarks

| Dataset | Modality | Collection | Annotation | Scale and counting unit | Purpose | Details and access |
| --- | --- | --- | --- | --- | --- | --- |
| [OpenPoly](https://doi.org/10.1007/s10118-025-3402-y) | PSMILES and structured properties | Literature mining; manual validation | Experimental labels | **3,985 unique polymer–property data points**, spanning **26 properties** | Multi-property prediction; representation benchmarking | [Original paper](https://www.cjps.org/rc-pub/front/front-article/download/127254462/lowqualitypdf/OpenPoly:%20A%20Polymer%20Database%20Empowering%20Benchmarking%20and%20Multi-property%20Predictions.pdf). This is a count of structure–property pairs, not 3,985 polymers each labeled for all 26 properties. |
| [NanoMine](https://materialsmine.org/nm) | Text, images, formulations, properties, and metadata | Experimental literature and curation | Experimental labels; coverage varies by sample | **>7,000 experimental polymer/nanocomposite samples** and **≈16M knowledge-graph triples**, as reported in the [workshop resource listing](https://polymerdataworkshop.nd.edu/info/) | Nanocomposite property prediction; multimodal learning | This differs from the reference table's ≈2.5k; its snapshot and counting basis are unspecified. Samples and graph triples are separate measures of scale; use the portal's version and export terms for a specific study. |
| Glass Transition Datasets (reference-table umbrella entry) | Polymer structures/names and Tg values | Experimental measurements and curation | Experimental Tg labels | Reference table: **≈7k**, **unverified** for the unspecified datasets | Tg prediction | The supplied image cites references 96–97 without bibliographic details, so an exact release cannot be identified. Related resources include [RNN-Tg](https://github.com/figotj/RNN-Tg) and [PoLyInfo](https://polymer.nims.go.jp/); do not treat their subsets as independent datasets without checking overlap. |
| [POINT² / POINT2](https://github.com/Jiaxin-Xu/POINT2) | SMILES, graphs, and property/model outputs | Curated labeled sources plus PI1M-generated structures | Mixed measured, simulated, and predicted labels | Labeled-core total not confirmed; reference table: **≈7k**, **unverified**. Uses **≈1M PI1M virtual structures** | Property prediction; uncertainty and interpretability evaluation; candidate screening | [Paper](https://arxiv.org/abs/2503.23491). Repository links source datasets and says further data/model availability will accompany formal publication. PI1M-derived candidates are shared with PI1M, not an additional million independent structures. |

### Large-scale polymer datasets and corpora

| Dataset | Modality | Collection | Annotation | Scale and counting unit | Purpose | Details and access |
| --- | --- | --- | --- | --- | --- | --- |
| [PoLyInfo](https://polymer.nims.go.jp/) | Structures, names, text, properties, and processing metadata | Experimental literature; curation | Experimental labels; sparse across properties | **19,227 homopolymers; 8,321 copolymers; 2,788 blends; 3,209 composites; 174,968 samples; 552,427 property points; 21,793 literature records** | Property prediction; information retrieval | Official snapshot: **2025-05-29**; about 100 property types. These are different entity counts. Registration required; bulk acquisition, scraping, and unauthorized redistribution are prohibited. |
| [PolyOmics](https://huggingface.co/datasets/yhayashi1986/PolyOmics) | SMILES, MD snapshots, simulation metadata, and properties | RadonPy MD; separate ML-estimated interaction parameters | Computed labels; predicted χ labels in separate files | **>100k polymeric materials** overall; named subsets include **73,045 general polymers**, **50,661 cellulose derivatives**, and **3,821 PFAS-related structures** | Pretraining; simulation-to-experiment transfer; property prediction | Current dataset card, CC BY 4.0. The general-polymer subset has up to **55 calculated properties**. Also lists χ estimates for **93,331 polymers** and **23,361 small molecules**; overlapping subsets and small molecules must not be summed as unique polymers. [Paper](https://arxiv.org/abs/2511.11626). |
| [SMiPoly](https://github.com/PEJpOhno/SMiPoly) | Repeat-unit SMILES; reaction-derived structures | Rule-based virtual polymerization | No experimental property labels | **169,347 unique virtual polymers** from **1,083 monomers**, in the [2023 paper](https://doi.org/10.1021/acs.jcim.3c00329) | Structure pretraining; generative design; candidate enumeration | Seven polymer classes and 22 reaction rules in that study. The software is a generator; library size depends on the monomer set, rules, and deduplication. |
| [PI1M](https://github.com/RUIMINMA1996/PI1M) | Polymer SMILES (p-SMILES/PSMILES) | Generative model trained on ≈12k PoLyInfo polymers | No experimental property labels; v2 includes heuristic SA scores | **≈1M generated polymer structures** | Self-supervised pretraining; representation learning; generative modeling | General polymer-informatics corpus, rather than a polyimide-only property dataset. Repository provides `PI1M.csv` and `PI1M_v2.csv`; MIT license coexists with an academic-use-only note, so clarify terms for other reuse. |
| [Polymer Scholar](https://polymerscholar.org/) | Literature text and extracted property records | NLP/LLM extraction from papers | Automatically extracted labels requiring validation | **>1M property records**, **24 properties**, **>106k unique polymers**, from **≈681k polymer-related articles** in the [2024 paper](https://doi.org/10.1038/s43246-024-00708-9) | Property retrieval; information extraction; language-model applications | **≈2.4M** is the input materials-science article corpus, not the number of polymer records. Earlier abstract-based extraction reported ≈300k records; do not add successive releases without deduplication. |
| [PolyUniverse](https://github.com/ytl0410/PolyUniverse) | PSMILES; monomer and reaction information | Rule-based virtual polymerization | Structures without experimental labels; predictions are separate | Reference table: **≈7M virtual structures**, **unverified**; exact archived-release count needs confirmation | Pretraining; generative modeling; virtual screening | [Paper](https://doi.org/10.1039/D4DD00196F); [full generation archive](https://zenodo.org/records/12585902). GitHub contains code and a small example, not the full library. The workshop lists ≈8M, so rounded totals should not be treated as a verified exact count. |
| [Open Macromolecular Genome (OMG)](https://zenodo.org/records/7556992) | Repeat-unit SMILES and monomer/reaction relationships | Reaction-based enumeration from commercially available monomers | Structure library without experimental property labels | **≈12M synthetically accessible candidate polymers**, reported by the [authors' property-data release](https://zenodo.org/records/13863778) | Pretraining; generative and synthesis-aware design | Specify which OMG release is used. The later quantum-chemistry extension supplies monomer-level data; it does not provide 12M experimentally measured polymers. |

### Related molecular corpus

| Dataset | Modality | Collection and annotation | Scale and counting unit | Purpose and scope |
| --- | --- | --- | --- | --- |
| [MolTextNet](https://huggingface.co/datasets/liuganghuggingface/moltextnet) | Canonical SMILES and text descriptions | ChEMBL35 molecules with model-generated descriptions | **2,474,584 molecule–text pairs** in the dataset card (paper rounds to ≈2.5M) | Molecular multimodal pretraining and retrieval. The [paper](https://arxiv.org/abs/2506.00009) concerns **small molecules**; this is a related transfer-learning resource, not a polymer-specific corpus. |

## Additional dataset sizes

These resources extend the comparison beyond the reference images. Counts below are publication/release-specific and retain their original units. The 2026 release table that follows provides further benchmark and characterization sizes.

| Dataset | Reported scale | Data and learning use | Source and access notes |
| --- | --- | --- | --- |
| [OPoly26](https://arxiv.org/abs/2512.23117) | **>6.57M DFT calculations; >1.2B atoms** in total; clusters up to **360 atoms** | Polymer-derived atomistic structures for model pretraining and evaluation | Paper v2, **2026-03-04**. Calculations and atom totals are not counts of unique polymers; follow the paper's data-release links. |
| [HTP-MD](https://data.matr.io/htp/) | **6,286 MD trajectories** | Amorphous polymer electrolytes; transport analysis | [Platform paper](https://doi.org/10.1063/5.0160937) and [workshop listing](https://polymerdataworkshop.nd.edu/info/). Multiple trajectories can represent the same chemistry. |
| [PolySol / PolySolDB](https://github.com/cstubb/PolySol) | **1,818 homopolymer** and **270 copolymer solubility data points** | Handbook-curated solubility prediction | Author README gives both counts and CSV/PKL paths. The records describe solubility observations, not necessarily unique polymers. |
| [BCDB](https://acdc.alcf.anl.gov/mdf/detail/bcdb_v1.3/) | **>5,300 block-copolymer melt phase measurements** at publication | BigSMILES, phase behavior, and characterization | MDF release v1.3; CC BY 4.0. Count is of measurements, rather than distinct polymer structures. |
| [PolyIE](https://arxiv.org/abs/2311.07715) | **146 full-length articles** with expert annotation | Entities, values, conditions, and N-ary relations for information extraction | The paper links code and annotated data; document count is distinct from entity/relation count. |
| [ToPoRg-18k](https://doi.org/10.5281/zenodo.13619701) | **18,450 coarse-grained polymers** | Single-chain radius-of-gyration distributions; topology-aware learning | Confirmed by the [author's resource page](https://webbgroup.princeton.edu/resources). |
| [Single-chain nanoparticle configurations](https://doi.org/10.34770/a2db-gy35) | **153,600 configurations** across **7,680 simulated nanoparticles**, from **320 precursor chains** | Sequence, morphology, and dispersity learning | Princeton data release, 2023; [author description](https://webbgroup.princeton.edu/resources). Keep configuration and precursor counts separate. |
| [SCNP-Shearflow-10k](https://doi.org/10.5281/zenodo.17203738) | **10,800 coarse-grained MD simulations** | Single-chain nanoparticle morphologies under shear | 2025 release; [author description](https://webbgroup.princeton.edu/resources). |
| [NIMS Polymer NMR](https://polymer.nims.go.jp/) | **154 samples** with assigned **¹H/¹³C NMR** spectra | Spectral characterization and structure assignment | Count is given on the PoLyInfo landing page; subject to NIMS access terms. |
| [OMG quantum-chemistry extension](https://zenodo.org/records/13863778) | **32,529 training-selection geometries** and **15,147 test geometries** of methyl-terminated monomers | Monomer-level computed properties for polymer design | Release v2. Authors report duplicates and **15 overlapping methyl-terminated monomers** between train and test; preserve the release's deduplication warning. |

For portals or datasets without a verified count, record **not reported / release-dependent** instead of estimating from a website's download size, number of files, model outputs, or citation count. MatNavi, CAMPUS, MatWeb, and prediction services do not have one comparable polymer-training-set size.

## Selected public releases (2026)

Recent examples with a public repository or data record. A public download does not always grant permission for commercial use or redistribution.

| Dataset | What it contains | Access and notes |
| --- | --- | --- |
| [PolyBench26](https://github.com/rlearsch/PolymerBenchmark2026) | Nearly 250,000 data points across eight properties, from experimental, DFT, and MD sources; includes multiple polymer architectures | Open benchmark; source data and redistribution terms vary |
| [ADEPT–PolyGraphMT](https://github.com/sobinalosious/PolyGraphMT) | About 62,000 polymer-property values across 28 properties, combining experimental measurements, MD, DFT, and group-contribution estimates | CSV inputs, trained models, and scripts are available in the repository; see the [Digital Discovery article](https://doi.org/10.1039/D6DD00206D). Check repository terms before reuse; a license was not apparent in the public repository. |
| [Polymer membrane permeability and ATR-FTIR](https://doi.org/10.15125/BATH-01709) | 204 dense polymer membranes, up to six gas permeability labels, 860 spectra, and an ML notebook | University of Bath archive; CC BY 4.0 |
| [Nanoplastic disassembly in lipid membranes](https://doi.org/10.5281/zenodo.22936014) | Simulation inputs and final frames for nanoplastics interacting with lipid membranes | Zenodo record; check record for reuse terms |
| [PBLG nanofibrous membrane data](https://doi.org/10.5281/zenodo.22704383) | Optical, Raman, SEM, morphology, and mechanical data for ultrathin poly(γ-benzyl-L-glutamate) membranes | Zenodo; CC BY 4.0 |
| [VIS–NIR–SWIR microplastics library](https://doi.org/10.5281/zenodo.20180898) | 350–2500 nm reflectance spectra for PET, HDPE, PVC, LDPE, PP, and PS, with color and size metadata | Open Zenodo dataset |
| [Multilayer packaging water-vapor data](https://doi.org/10.5281/zenodo.18262441) | Water-vapor permeability data for 27 polymers | Public CSV; values combine new measurements and literature data |
| [RxnChainer generated polymers](https://doi.org/10.5281/zenodo.21878520) | Reaction-guided idealized polymer repeat units and reproducibility data | Non-commercial research use; commercial use needs written permission; structures are not experimentally validated |

## Resource catalog

### Experimental properties and materials databases

- [PoLyInfo](https://polymer.nims.go.jp/) — broad literature-derived property and processing records; **552,427 property points** in the official 2025-05-29 snapshot. Registration is required for use; bulk downloading and scraping are prohibited by its terms.
- [MatNavi](https://mits.nims.go.jp/) — NIMS materials and polymer databases, including characterization data.
- [OpenPoly](https://www.cjps.org/rc-pub/front/front-article/download/127254462/lowqualitypdf/OpenPoly:%20A%20Polymer%20Database%20Empowering%20Benchmarking%20and%20Multi-property%20Predictions.pdf) — curated experimental benchmark with **3,985 polymer–property data points across 26 properties**.
- [Khazana](https://khazana.gatech.edu/dataset/) — computational and curated polymer properties for screening and prediction.
- [Polymer Genome](https://www.polymergenome.org/) — property prediction and design resources; access may require registration.
- [NanoMine](https://materialsmine.org/nm) — polymer nanocomposite data, metadata, and analysis tools; the workshop listing reports **>7,000 experimental samples** (see the comparison above).
- [PPPdb / 3PDB](https://pppdb.uchicago.edu/) — χ, Tg, and cloud-point tables plus phase-diagram tools; a verified aggregate record count is not published on its landing page.
- [CHEMnetBASE — Polymers: A Property Database](https://poly.chemnetbase.com/) — commercial reference information for **>1,100 polymers**; subscription access.
- [Block Copolymer Phase Behavior Database (BCDB)](https://acdc.alcf.anl.gov/mdf/detail/bcdb_v1.3/) — literature-curated phase measurements and characterization records for block copolymers, with simulation phase-diagram data; the MDF record lists CC BY 4.0.
- [CAMPUS Plastics](https://www.campusplastics.com/) and [MatWeb](https://www.matweb.com/) — grade-level engineering data; confirm supplier and use terms.

### Online polymer property-prediction platforms

These services provide interactive prediction or discovery workflows. They are distinct from downloadable datasets; check account requirements, model scope, and terms before using predictions as research data.

| Platform | Link | Predictable properties or tasks | Description |
| --- | --- | --- | --- |
| [CEMP](https://cleanenergymaterials.cn/) | [Open platform](https://cleanenergymaterials.cn/) | Polymer property search and prediction; platform also provides polymer simulation workflows | Integrates polymer records, prediction tools, visualization, and online QC/MD workflows for clean-energy materials. |
| [Polymer Genome](https://polymergenome.org/) | [Open platform](https://polymergenome.org/) | Thermal, mechanical, electronic, and transport properties; exact outputs depend on the selected model | Uses pretrained machine-learning models to predict polymer properties from a repeat-unit representation or SMILES. The platform explicitly describes itself as a prediction platform, not a database. |
| [POLYMAT Polymer Properties Predictor](https://polymatai.pythonanywhere.com/) | [Open predictor](https://polymatai.pythonanywhere.com/) | Copolymer reactivity ratios (r₁, r₂), radical-polymerization propagation rate constant (Kp), polymer glass-transition temperature (Tg), and monomer water solubility (Ws) | Provides machine-learning predictions developed at the POLYMAT research center, University of the Basque Country. |
| [AI Plus Polymers](https://www.aipluspolymers.com/) | [Open platform](https://www.aipluspolymers.com/) | Polymer property prediction, structure generation, and formulation optimization | An AI-driven polymer innovation platform; its public landing page does not enumerate individual prediction targets. |
| [PolyID](https://polyid.nrel.gov/) | [Open predictor](https://polyid.nrel.gov/) | Thermal, transport, and mechanical properties; supports six polymerization classes | Predicts properties from monomer structures using machine learning and supports structure-guided polymer screening. |

### Synthesis, copolymers, and recycling

- [CoPolDB](https://www.copoldb.jp/copolym/) — radical copolymerization systems, feed/composition data, and reactivity ratios.
- [CopDDB](https://github.com/hatanaka-lab/CopDDB) — copolymer descriptors and reactivity-ratio data.
- [PolySol](https://github.com/cstubb/PolySol/tree/main/data/csvs) — **1,818 homopolymer** and **270 copolymer** solubility data points.
- [Crystal16 Solubility](https://github.com/mona2442/Polymer-Solubility-Data_Crystal16) — raw turbidity measurements and processed cooling-cycle solubility curves; verified system/curve-point counts remain unavailable.
- [Block-copolymer SEM data](https://zenodo.org/records/13927939) and [PISA phase-prediction data](https://github.com/marioboley/PISA_ML) — morphology and phase classification.
- [TROPIC](https://pubs.rsc.org/en/content/articlehtml/2026/fd/d5fd00098j) — ring-opening polymerization thermodynamics for chemical-recycling research.
- [RxnChainer](https://doi.org/10.5281/zenodo.21878520) — reaction-guided generated polymers; non-commercial restrictions apply.

### Computation and benchmarks

- [OPoly26](https://arxiv.org/abs/2512.23117) — millions of DFT calculations on polymer-derived structures.
- [PolyGraphMT](https://github.com/sobinalosious/PolyGraphMT) — multi-task, multi-fidelity polymer-property data and graph-neural-network models; the paper reports about 62,000 values across 28 properties from experimental, MD, DFT, and group-contribution sources. See the [Digital Discovery article](https://doi.org/10.1039/D6DD00206D); check repository terms before reuse.
- [PolyOmics](https://huggingface.co/datasets/yhayashi1986/PolyOmics) — **>100k polymeric materials**, with family-specific property tables and MD snapshots; see the dataset comparison for subset counts.
- [HTP-MD](https://data.matr.io/htp/) — polymer-electrolyte molecular-dynamics trajectories and derived transport properties, including systems with Li-TFSI salts.
- [PI1M](https://github.com/RUIMINMA1996/PI1M) — **≈1M generated polymer structures** in p-SMILES; v2 adds heuristic synthetic-accessibility scores. It is a general polymer corpus without experimental property labels.
- [PolyUniverse](https://github.com/ytl0410/PolyUniverse) — rule-generated virtual polymer libraries; the repository includes generation code and a small example dataset, with generation results also archived on [Zenodo](https://zenodo.org/records/12585902).
- [Open Macromolecular Genome](https://zenodo.org/records/7556992) — generated candidates constrained by synthetic accessibility.
- [POINT2](https://github.com/Jiaxin-Xu/POINT2) — hybrid benchmark using labeled sources and **≈1M PI1M virtual structures**; complete data/model availability is still qualified by the repository README.
- [PolyID training data](https://doi.org/10.1021/acs.macromol.3c00994) — **1,791 training polymers** across eight experimental-property targets; paper supporting information includes XLSX data. Its **≈1.4M screening candidates** are a separate generated library.
- [ToPoRg-1342](https://doi.org/10.5281/zenodo.10672433) and [ToPoRg-18k](https://doi.org/10.5281/zenodo.13619701) — **1,342** and **18,450** coarse-grained polymers with radius-of-gyration labels for topology-aware learning.
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

- [PolyIE](https://arxiv.org/abs/2311.07715) — information-extraction dataset from **146 full-length polymer papers**, with expert entity and relation annotations.
- [Polymer Scholar](https://polymerscholar.org/) — **>1M automatically extracted property records** for **>106k polymers** in the 2024 paper; searchable literature-derived data rather than a 2.4M-polymer corpus.
- [ChemProps](https://pmc.ncbi.nlm.nih.gov/articles/PMC7955638/) — polymer name normalization API.
- [Open Polymer Challenge](https://arxiv.org/abs/2512.08896) — competition data and evaluation resources.
- Publisher APIs, [Crossref](https://www.crossref.org/documentation/retrieve-metadata/rest-api/), [PubMed](https://pubmed.ncbi.nlm.nih.gov/), and [arXiv](https://info.arxiv.org/help/api/index.html) can support literature-scale collection; access terms differ.

### Related molecular datasets for transfer learning

- [MolTextNet](https://huggingface.co/datasets/liuganghuggingface/moltextnet) — **2,474,584 small-molecule–text pairs**, combining ChEMBL35 structures and generated descriptions. Useful for molecular multimodal pretraining; polymer adaptation and evaluation require polymer-specific data.

### Data schemas and infrastructure

- [CRIPT](https://www.criptapp.org/) — community platform for capturing and sharing polymer research data; it hosts resources including the BCDB listed above.
- [PolyDAT](https://doi.org/10.1021/acs.jcim.1c00028) — a generic schema for polymer characterization, species, precursors, and transformations; it is a data format rather than a standalone dataset.
- [OFET-db and process ontology](https://doi.org/10.1021/acs.chemmater.3c01842) — a process-aware schema and repository for conjugated-polymer OFET data, covering ordered solution preparation, substrate treatment, deposition, post-processing, and device measurements; the paper describes literature-curated and laboratory records.

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

To suggest a dataset, open an issue or pull request with its source link, scope, access terms, and publication or data record. Include the size, counting unit (unique structures, samples, property observations, trajectories, or documents), release/version, source date, and verification date; mark an unavailable count as not reported. For mixed datasets, report experimental, simulated, predicted, and unlabeled subsets separately. Please distinguish downloadable data from portals, papers, and data-generation software.
