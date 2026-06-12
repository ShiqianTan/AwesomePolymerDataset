# AI for Polymer Data Source Collection

This repository curates data sources that can support AI and machine-learning work in polymer science. It merges the previous database list with the expanded survey report and reorganizes the material into a practical, English-language reference.

The collection covers experimental property data, synthesis and formulation records, spectroscopy and characterization data, computational datasets, literature/text corpora, image and microstructure datasets, copolymer-specific resources, commercial databases, and tools for data generation or integration.

> Note: Some entries are direct downloadable datasets, while others are database portals, commercial products, papers with supplementary data, or starting points for data extraction. Always verify the current license, API terms, access limits, and redistribution rights before using a resource in a model-training pipeline.

## How to Use This Collection

Start from the modeling task, not from the database name:

| AI task | Best starting categories |
| --- | --- |
| Polymer property prediction | Core property databases, computational datasets, handbooks |
| Reverse design and generative modeling | Computational datasets, Polymer Genome/Khazana, Open Macromolecular Genome, polyBART |
| Copolymer reactivity or phase prediction | Copolymer datasets, synthesis/process datasets |
| Synthesis optimization | Synthesis/process datasets, reaction-specific datasets, literature extraction |
| Spectral identification | Spectroscopy and characterization datasets |
| Microstructure or defect analysis | Image and microstructure datasets |
| Literature mining and knowledge graphs | NLP/text datasets, literature APIs |
| Polymer representation design | BigSMILES, PSMILES, PSELFIES, HELM, ChemProps, CRIPT |
| Industrial formulation and processing optimization | MatWeb, UL Prospector, Total Materia, Polymerize, PolymRize, MatCloud+ |
| Environmental safety or degradation | LitChemPlast, TROPIC, microplastics datasets, sustainability-focused literature |

## Resource Tiers

| Tier | Typical resources | When to use |
| --- | --- | --- |
| Open and free-registration resources | PoLyInfo, MatNavi, OpenPoly, Khazana, PI1M, OMG, CopDDB, CoPolDB, FTIR-Plastics, PolyIE | Baseline academic modeling, benchmarking, exploratory data collection |
| AI-ready benchmark datasets | OpenPoly, POINT2, OPoly26, Open Polymer Challenge, Carbon-m1, PolyIE, selected Kaggle/GitHub datasets | Fast model prototyping, reproducible comparisons, transfer learning |
| Commercial or institution-licensed resources | Total Materia, SpectraBase premium access, SciFinder-n, Reaxys, KnowItAll, ACD/Labs NMR, Landolt-Bornstein, CAMPUS, UL Prospector, MatCloud+ enterprise services | Industrial-grade data, larger exports, proprietary test data, workflow integration |
| Data-generation and integration tools | ADEPT, RadonPy, SPACIER, PolyMetriX, pylimer-tools, MatCloud+, RDKit, literature APIs | Filling data gaps, standardizing heterogeneous records, automated updates |
| Representation and governance infrastructure | BigSMILES, PSMILES, PSELFIES, HELM, CRIPT, dataset cards, DVC/DataLad | Polymer-specific structure encoding, provenance, FAIR data management |

## 1. Core Polymer Property and Materials Databases

These databases are the main starting points for polymer structure-property modeling. They usually contain thermal, mechanical, electrical, optical, rheological, solution, processing, or compositional information, often with literature provenance and test-condition metadata.

| Resource | Access | Main data types | Best use |
| --- | --- | --- | --- |
| [PoLyInfo](https://polymer.nims.go.jp/) | Free web search; some features may require registration | Homopolymers, copolymers, chemical structures, about 100 property types, literature provenance, test metadata | General polymer property prediction and literature-grounded structure-property analysis |
| [MatNavi / NIMS Materials Database](https://mits.nims.go.jp/) | Free search; registration for deeper access | Materials properties, polymer sub-databases, NMR data, test-condition metadata | Property and characterization data with standardized measurement context |
| OpenPoly | Open academic resource | Standardized polymer-property records extracted and validated from literature | AI-ready benchmark data for multi-property prediction |
| [Khazana](https://khazana.gatech.edu/dataset/) | Public dataset portal | Computed and curated polymer properties, including bandgap, dielectric constant, density, solubility parameter, glass-transition temperature | Property modeling and virtual polymer screening |
| [Polymer Genome](https://www.polymergenome.org/) / [AI plus Polymers](https://polymergenome.ecust.edu.cn/) | Registration or application may be required | Experimental and computational polymer property data, descriptor-driven prediction workflows | Polymer informatics, property prediction, inverse design |
| [Polymer Property Predictor and Database](https://pppdb.uchicago.edu/) | Public web portal | Flory-Huggins parameters, glass-transition temperature, cloud points and solution properties | Polymer solution thermodynamics and mixture modeling |
| [CROW Polymer Properties Database](https://polymerdatabase.com/) | Public web portal with curated pages | Physical, thermal, mechanical, optical, and chemical properties | Quick lookup and educational/reference use |
| [PolymerDatabase / ChemNetBase](https://poly.chemnetbase.com/) | Commercial or institution access | Polymer property database based on reference works | Handbooks-style property lookup and engineering reference |
| [Total Materia](https://www.totalmateria.com/) | Commercial; trials or institutional access may be available | Industrial material properties, standards-based test data, polymers and other materials | Engineering-grade property data and industrial model development |
| [MatWeb](https://www.matweb.com/) | Public search with account features | Mechanical, thermal, physical, chemical, and processing properties | Engineering material selection and baseline property comparison |
| UL Prospector | Commercial/free-account engineering portal depending on access mode | Supplier technical data sheets, safety data sheets, melt-flow rate, molding shrinkage, processing windows, grade-level properties | Industrial resin selection, formulation screening, and process-aware modeling |
| [MakeItFrom](https://www.makeitfrom.com/) | Public web portal | Mechanical, thermal, electrical, and physical properties across material classes | Fast comparison across polymers, metals, and ceramics |
| [CAMPUS Plastics](https://www.campusplastics.com/) | Public and supplier-linked data | Thermoplastics, grades, mechanical, thermal, electrical, fire, and processing properties | Commercial resin grade selection and application screening |
| [Landolt-Bornstein / SpringerMaterials](https://materials.springer.com/) | Commercial or institution access | Curated physical, thermodynamic, rheological, mechanical, thermal, and electrical data | High-quality reference data with literature provenance |
| SciFinder-n / CAS Registry | Commercial or institution access | Chemical substance records, polymer entries, CAS identifiers, literature links, synthesis and property references | Polymer entity normalization, literature backtracking, and structure-cleaning pipelines |
| Reaxys | Commercial or institution access | Chemical reactions, synthesis routes, catalysts, basic physical properties, and extracted literature data | Polymer synthesis mining, degradation-route analysis, and retrosynthesis support |
| [Dortmund Data Bank](https://ddbst.com/) | Commercial and selected public data | Thermodynamic and phase-equilibrium data | Polymer solution, phase equilibrium, and process modeling |
| [Polymer Scholar](http://polymerscholar.org/) | Public web portal | Glass-transition temperature, melting point, tensile strength, conductivity, molecular weight, solubility parameter | Literature-oriented property search |
| [NanoMine](https://materialsmine.org/nm) | Public platform | Polymer nanocomposite data, metadata, characterization records, and analysis tools | Nanocomposite informatics and multi-objective materials design |
| [HTPMD](https://www.htpmd.matr.io/) | Public/project portal | High-throughput polymer material design data and workflow outputs | Simulation-assisted polymer screening |
| [LitChemPlast](https://pubs.acs.org/doi/full/10.1021/acs.estlett.4c00355) | Open database described in publication | Chemicals measured in plastics, additives, migrants, degradation-related chemical records | Environmental safety, exposure, degradation, and toxicity-oriented modeling |

## 2. Synthesis, Processing, Formulation, and Recycling Data

These sources are useful when the model needs reaction conditions, recipes, monomer ratios, catalysts, processing history, or recycling thermodynamics rather than only final measured properties.

| Resource | Access | Main data types | Best use |
| --- | --- | --- | --- |
| [TROPIC: Thermodynamics of Ring-Opening Polymerisation Informatics Collection](https://pubs.rsc.org/en/content/articlehtml/2026/fd/d5fd00098j) | Publication and associated data | Ring-opening polymerization thermodynamics | Chemical recycling, depolymerization, and circular polymer design |
| [CoPolDB](https://www.copoldb.jp/copolym/) | Public web database | Radical copolymerization systems, reactivity ratios, feed/composition data | Copolymerization modeling and reactivity-ratio prediction |
| [CopDDB](https://github.com/hatanaka-lab/CopDDB/tree/main) | Public GitHub repository | Copolymer descriptors and reactivity-ratio related data | Copolymer machine learning and descriptor benchmarking |
| RAFT dispersion polymerization literature datasets | Publication/supplementary data | RAFT polymerization conditions and formulation records | Experimental design for controlled polymerization |
| Open-ring and nitroxide-mediated polymerization literature data | Publication/supplementary data | Reaction conditions, monomer/catalyst systems, kinetics | Small, task-specific synthesis models |
| [MatCloud+](https://www.matcloudplus.com.cn/) | Commercial platform with limited/free resources depending on account | High-throughput modeling workflows, simulation results, managed data | Process-integrated data generation and industrial workflow management |
| Predici | Commercial software | Polymerization kinetics and process simulation data | Industrial polymerization process modeling |
| Polymerize | Commercial SaaS platform | Polymer R&D records, formulations, LIMS-style experiment data, recipe variables, and guided regression workflows | Enterprise formulation optimization and laboratory-to-pilot-scale learning loops |
| PolymRize / Matmerize | Commercial SaaS platform | Active-learning workflows, private materials data management, uncertainty-guided candidate recommendation | Enterprise polymer design, design-of-experiments planning, and secure model deployment |
| Polymer synthesis handbooks | Books or institution access | Recipes, mechanisms, reaction examples, processing notes | Manual curation of synthesis datasets and baseline process knowledge |

## 3. Copolymer and Block Copolymer Datasets

Copolymer datasets deserve their own section because sequence, composition, architecture, monomer feed, block length, and processing pathway often dominate the property labels.

| Dataset or resource | Availability | Core content | Link |
| --- | --- | --- | --- |
| PoLyInfo copolymer records | Registration may be required for full use | Experimental property data for homopolymers and copolymers | [PoLyInfo](https://polymer.nims.go.jp/) |
| Polymer Genome copolymer resources | Registration or application may be required | Copolymer property prediction and descriptor workflows | [Polymer Genome](https://www.polymergenome.org/copg) |
| Copolymer Informatics with Multitask Deep Neural Networks | Code/data availability may be limited | Copolymer informatics models and multitask learning workflows | [GitHub](https://github.com/Ramprasad-Group/copolymer_informatics) |
| Khazana Polymer Dataset | Public | Homopolymer and copolymer property data from the Ramprasad group ecosystem | [Khazana](https://khazana.gatech.edu/dataset/) |
| CopDDB | Public; published in 2025 | Descriptor database for copolymers; supports reactivity-ratio prediction | [GitHub](https://github.com/hatanaka-lab/CopDDB/tree/main) |
| CoPolDB | Public | Radical copolymerization systems and reactivity-ratio data | [CoPolDB](https://www.copoldb.jp/copolym/) |
| Block copolymer self-assembly SEM dataset | Public data repository | SEM images for data-driven design of block copolymer self-assembly | [Zenodo record](https://zenodo.org/records/13927939) |
| Multi-objective Bayesian optimization for copolymerization | Public GitHub repository | Styrene-methyl methacrylate experimental-design data and MOBO workflow | [GitHub](https://github.com/MI-Lab-NAIST/Multi-objective_Bayesian_optimization_for_experimental_design_in_copolymerization) |
| Universal phase identification of block copolymers | Public GitHub data | SAXS data for block-copolymer phase identification | [GitHub](https://github.com/UncertaintyQuantification/automated_polymer_phase_identification/tree/main/data) |
| High-throughput block copolymer libraries | Public repository search | Automated chromatography data for di-block and tri-block polymers | [Dryad search](https://datadryad.org/search?utf8=%E2%9C%93&q=Block+Copolymer+Libraries) |
| Antibacterial block copolymer activity dataset | Public spreadsheet | Antibacterial activity labels for block copolymers | [GitHub](https://github.com/varunkundi/polymerML/blob/main/dataset_ML_Polymer.xlsx) |
| PISA phase-prediction data | Public GitHub repository | Polymerization-induced self-assembly phase data and interpretable ML workflows | [GitHub](https://github.com/marioboley/PISA_ML) |
| Protein-targeting amphiphilic copolymer supplementary data | Supplementary ZIP | Sequence-based design data for high-affinity amphiphilic copolymers | [ACS supplementary file](https://pubs.acs.org/doi/suppl/10.1021/acs.macromol.5c01112/suppl_file/ma5c01112_si_002.zip) |
| PolySol | Public GitHub data | Homopolymer and copolymer solubility data in CSV format | [GitHub](https://github.com/cstubb/PolySol/tree/main/data/csvs) |
| Radical copolymerization reactivity-ratio ANN | Web tool; data availability may be limited | Reactivity-ratio prediction for radical copolymerization | [PolyMatAI](https://polymatai.pythonanywhere.com/search) |

## 4. Spectroscopy and Structural Characterization Data

Spectroscopy datasets are useful for polymer identification, chemical-structure recognition, microplastic classification, crystallinity estimation, and multimodal modeling.

| Resource | Access | Main data types | Best use |
| --- | --- | --- | --- |
| [FTIR-Plastics](https://pmc.ncbi.nlm.nih.gov/articles/PMC11252596/) | Open dataset | FTIR spectra for PET, HDPE, PVC, LDPE, PP, and PS | Microplastic identification and spectral classification |
| NIMS MatNavi Polymer NMR Database | Free registration may be required | Polymer NMR spectra and test-condition metadata | Polymer structural identification and NMR-based modeling |
| [SpectraBase](https://spectrabase.com/about) | Free lookup; paid bulk/premium access | NMR, FTIR, Raman, UV/Vis and other spectra | Spectral search, structure identification, and model training with licensed exports |
| NMRExtractor / NMRBank | Open academic resource | NMR data extracted from open-access chemical literature | Literature-scale NMR data mining and structure-spectrum modeling |
| Shanghai Institute of Organic Chemistry spectral databases | Institution/account access may be required | NMR, IR, Raman, and related organic/polymer spectra | China-based spectral reference and curation |
| [ACD/Labs NMR Databases](https://www.acdlabs.com/products/dbs/nmr_db) | Commercial | NMR spectral libraries and prediction tools | Industrial-grade NMR prediction and validation |
| [Polymer Science Learning Center](https://pslc.uwsp.edu/) | Public educational portal | Basic polymer and chemical information, some spectral resources | Teaching, lightweight lookup, and seed data |
| [NIST Synthetic Polymer MALDI Recipes Database](https://maldi.nist.gov/) | Public NIST resource | MALDI mass-spectrometry recipes for synthetic polymers | Polymer mass-spectrometry method selection |
| KnowItAll / Bio-Rad | Commercial | IR, Raman, NMR, and spectral analysis tools | Standard spectral matching and commercial spectral workflows |

## 5. Computational, Simulation, and Virtual Polymer Datasets

Computational resources are especially useful when experimental labels are scarce, when high-throughput screening is needed, or when models must learn quantum, electronic, transport, or morphology descriptors.

| Resource | Access | Main data types | Best use |
| --- | --- | --- | --- |
| OPoly26 / Open Polymers 2026 | Public or project-linked release | Large-scale polymer quantum-chemistry and DFT-style computed properties; associated benchmark tasks | Foundation-model training, transfer learning, and large-scale property prediction |
| POINT2 | Research benchmark dataset | Multi-task polymer labels for glass-transition temperature, melting temperature, thermal conductivity, fractional free volume, density, and gas permeability | Multi-task learning, uncertainty quantification, transport-property prediction, and model interpretability |
| [PI1M](https://github.com/RUIMINMA1996/PI1M) | Public GitHub repository | Virtual polyimide structures and computed properties | Polyimide screening and generative-design benchmarks |
| [Open Macromolecular Genome](https://zenodo.org/records/7556992) | Public data repository | Synthetically accessible generated polymer candidates | Reverse polymer design and generative modeling |
| PolyOmics | Project/database resource | Molecular-dynamics-derived polymer properties and standardized simulation outputs | MD-driven polymer informatics |
| ADEPT | Open or research workflow depending on release | Automated polymer MD workflow from monomer SMILES to amorphous chains, equilibration, DFT monomer descriptors, and property extraction | High-throughput physical-property generation and surrogate-model training |
| [RadonPy](https://github.com/RadonPy/RadonPy) | Open-source software | Automated polymer modeling, force-field assignment, MD simulation, property extraction | Generating standardized high-throughput simulation datasets |
| SPACIER | Open-source workflow | Automated all-atom MD workflows for polymer design | Bayesian optimization and closed-loop simulation screening |
| SimPoly | Publication/project resource | Machine-learning force-field simulations from first-principles data | Scalable polymer simulation and surrogate modeling |
| Radical polymer computed-property datasets | Publication/supplementary data | Isotropic g-values and related radical-polymer properties | Radical polymer electronic-property modeling |
| Polymer-drug interaction datasets for MIP design | Publication/project resource | MD, MM-PBSA, and DFT data for molecularly imprinted polymer design | Biomedical polymer interaction modeling |
| National scientific data resources for polyimides | National data platform | Polyimide-related computed or experimental records | Domain-specific polyimide model development |
| [Materials Project](https://materialsproject.org/) | Public platform and API | Computed inorganic crystal structures and properties | Transfer learning, descriptor comparison, and broader materials-informatics baselines |
| [RCSB Protein Data Bank](https://www.wwpdb.org/) and [RCSB APIs](https://data.rcsb.org/index.html) | Public APIs | 3D structures of proteins, nucleic acids, and macromolecular assemblies | Biomacromolecule/polymer interface studies and bio-polymer structure data |

## 6. Literature, NLP, and Text-Mining Resources

These resources help turn unstructured papers, abstracts, patents, and reports into machine-readable polymer facts.

| Resource | Access | Main data types | Best use |
| --- | --- | --- | --- |
| [PolyIE](https://ar5iv.labs.arxiv.org/html/2311.07715) | Public academic dataset | Labeled polymer literature for information extraction | Named-entity recognition, relation extraction, and polymer knowledge graphs |
| MaterialsBERT-style materials corpora | Model/data availability depends on project | Materials-science titles, abstracts, and full-text corpora | Domain-adaptive pretraining for polymer/materials NLP |
| polyBERT | Research model/resource | PSMILES-based polymer language model and dense polymer fingerprints | Self-supervised polymer representation learning and downstream property prediction |
| [polyBART](https://arxiv.org/html/2506.04233v1) | Research model/dataset release | Polymer language-model pretraining data and structure-property pairs | Generative polymer design and text/structure modeling |
| TransPolymer | Research model/resource | Transformer-based polymer sequence pretraining on augmented PI1M-style structures | Transfer learning for electrolyte, crystallinity, optoelectronic, and transport-property tasks |
| HELM-BERT-style biomacromolecule models | Research model/resource | HELM-tokenized peptide, oligonucleotide, and complex biomacromolecule sequences | Peptide permeability, protein interaction, and therapeutic polymer modeling |
| Open Polymer Challenge dataset | Competition/project dataset | Polymer property labels, computational records, and extracted metadata | Benchmarking and multimodal model development |
| [ChemProps](https://pmc.ncbi.nlm.nih.gov/articles/PMC7955638/) | RESTful API resource | Composite polymer name standardization | Entity normalization before data integration |
| [Kaggle Open Polymer Prediction resources](https://www.kaggle.com/) | Public competition platform | Competition datasets, notebooks, post-competition analyses | Reproducible modeling baselines and feature-engineering examples |
| Literature platform APIs | API access varies by publisher | Metadata, abstracts, references, and sometimes full text | Custom corpus construction and incremental updates |
| [rcsb-api](https://pypi.org/project/rcsb-api/0.3.0/) and pypdb | Open-source Python tools | Programmatic access to RCSB PDB metadata and structure records | Bio-polymer literature and structure metadata extraction |

Common literature platforms with APIs include Elsevier ScienceDirect, Wiley Online Library, Springer Nature, ACS Publications, RSC Publications, Crossref, PubMed, and arXiv. Access terms vary significantly.

## 7. Image, Morphology, and Microstructure Datasets

Image datasets support computer-vision tasks such as phase recognition, segmentation, defect detection, morphology quantification, and multimodal structure-property prediction.

| Resource | Access | Main data types | Best use |
| --- | --- | --- | --- |
| [GFRP/PP Composite FM-SEM Dataset](https://pmc.ncbi.nlm.nih.gov/articles/PMC12907714/) | Open for non-commercial research according to dataset terms | Field-emission SEM images and porosity/impregnation-related annotations for woven glass-fiber-reinforced polypropylene | Composite microstructure quantification and property prediction |
| [NIST SEM Image Segmentation Dataset](https://catalog.data.gov/dataset/detection-limits-for-sem-image-segmentation) | Open government dataset | SEM images, segmentation labels, and detection-limit examples | SEM segmentation, robustness testing, and benchmark training |
| [Carbon-m1](https://openreview.net/pdf?id=q6xm6PEhNv) | Public research dataset | Multimodal polymer data, including microstructure images and associated property/structure metadata | Vision-language and multimodal polymer property modeling |
| Polymer microstructure image datasets from academic groups | Availability varies | SEM/TEM/AFM images with compatibility, morphology, or defect labels | Polymer blend compatibility and defect prediction |
| Microplastics and nanoplastics image datasets | Publication/supplementary data | Optical/SEM images for particle detection and morphology classification | Environmental polymer particle detection |
| OPoly26 visualizations and simulated structures | Project-linked data | Molecular conformations, crystal/amorphous structures, generated images or trajectories | Multimodal models linking computed structures and properties |
| Figshare, Zenodo, Dryad, and institutional repositories | Open or restricted by dataset | Supplemental microscopy and characterization images | Task-specific dataset expansion |
| Publisher figure exports | License-dependent | Figures and image panels from articles | Manual curation, with strict copyright review |

## 8. Domain-Specific and Application-Focused Sources

These sources are narrower than the core databases but can be more valuable for a specific research question.

| Domain | Representative sources | Data value |
| --- | --- | --- |
| Environmental safety and plastic chemicals | LitChemPlast, microplastics FTIR/image datasets, EPA/NIST resources | Additives, migrants, degradation products, environmental identification |
| Chemical recycling and depolymerization | TROPIC, ring-opening polymerization literature, degradation studies | Reaction thermodynamics and circularity-oriented polymer design |
| Conductive and bioelectronic polymers | Reviews and supplementary datasets on conductive polymer composites, bioelectronic hydrogels, neural-interface materials | Functional labels, conductivity, biocompatibility, degradation behavior |
| Biodegradable polymers | Reviews, sustainability datasets, domain-specific literature extractions | Degradation, environmental behavior, biomedical or packaging applications |
| Biomedical polymers and molecular imprinting | Polymer-drug interaction datasets, PDB/RCSB, molecularly imprinted polymer studies | Binding, interaction, recognition, and bio-interface data |
| Industrial resin grades | CAMPUS, MatWeb, Total Materia, supplier datasheets | Grade-level processing, mechanical, thermal, and compliance data |
| Process-aware materials R&D | CRIPT, Polymerize, PolymRize, laboratory notebooks, LIMS exports | Links between formulation, synthesis, processing history, characterization, and final properties |

## 9. Books, Handbooks, and Reference Works

These sources are not always machine-readable, but they remain important for manual validation, unit checks, and filling gaps in sparse datasets.

| Reference | Data value |
| --- | --- |
| Polymer: A Property Database | Solution and bulk properties, manufacturing procedures, processing and application context |
| Handbook of Polymers | Polymer information for plastics, electronics, pharmaceutical, medical, aerospace, and general research use |
| Prediction of Polymer Properties | Fundamental models and derived properties such as van der Waals volume, cohesive energy, heat capacity, glass-transition temperature, density, solubility parameter, and modulus |
| Polymer Synthesis: Theory and Practice | Synthesis recipes and examples from conventional to functional polymers |
| Polymer Handbook | Comprehensive polymer molecule, solid-state, and solution information |
| Handbook of Phase Equilibria and Thermodynamic Data of Aqueous Polymer Solutions | Thermodynamic data for polymer solutions |
| Properties of Polymers by van Krevelen and te Nijenhuis | Group-contribution methods and semi-empirical baselines for thermal, solubility, and transition-property prediction |
| CRC Handbook of Chemistry and Physics | Standard physical constants, including common polymer constants useful for calibration |
| Encyclopedia of Polymer Science and Technology / Mark's Encyclopedia | Mechanistic background on synthesis, characterization, properties, and applications; useful for RAG systems and expert curation |
| Handbook of Polymers by George Wypych | Structured comparisons of physical, mechanical, thermal, and chemical properties for common industrial polymers |
| Landolt-Bornstein / SpringerMaterials | Curated reference tables for material properties |

## 10. Polymer Representation Standards

Polymer AI usually fails when the structure representation silently collapses polymer-specific information. Choose the representation by polymer class and modeling task:

| Representation | Best for | Strengths | Watch-outs |
| --- | --- | --- | --- |
| Conventional SMILES | Monomers, additives, oligomers, small-molecule fragments | Mature cheminformatics tooling and descriptor support | Does not naturally encode repeat units, stochastic chains, end groups, dispersity, or copolymer statistics |
| PSMILES | Regular homopolymers and repeat-unit models | Simple CRU notation with polymer connection points; common in polymer language models | Limited for random, branched, graft, crosslinked, or architecture-rich polymers |
| PSELFIES | Generative homopolymer and repeat-unit design | SELFIES-style robustness can reduce invalid generated strings | Still needs polymer-specific validation for synthetic feasibility and topology |
| BigSMILES / BigSMARTS | Random copolymers, block copolymers, branched/graft polymers, and stochastic macromolecules | Encodes stochastic objects, bonding descriptors, end groups, and repeat-unit sets | Canonicalization and descriptor extraction are more complex than small-molecule SMILES |
| HELM | Peptides, oligonucleotides, antibody-drug conjugates, complex biomacromolecules, and modified monomer libraries | Hierarchical representation from complex polymer to monomer and atom levels | Best suited to biomacromolecules and monomer-library workflows rather than commodity plastics |
| Graph representations | GNN and topology-aware property prediction | Captures atom/bond topology and can include stereochemistry or edge features | Needs careful pooling and repeat-unit conventions for molecular-weight and dispersity effects |
| 3D conformer and trajectory representations | Morphology-sensitive thermal, mechanical, dielectric, and transport properties | Captures chain packing, entanglement, density, and conformation | Expensive to generate and sensitive to force fields, equilibration, and sampling protocol |

Practical guidance:

1. Use PSMILES or PSELFIES for fast homopolymer pretraining and generative search.
2. Use BigSMILES when composition, stochasticity, end groups, or architecture matter.
3. Use HELM for engineered biomacromolecules and monomer-library systems.
4. Store the original representation and a normalized representation side by side.
5. Keep monomer feed, measured composition, molecular weight, dispersity, tacticity, branching, and processing history as separate metadata instead of forcing everything into one string.

## 11. AI-Ready Benchmarks and Model Families

The newer AI-for-polymer literature increasingly separates raw data sources from benchmark datasets and pretrained model families. These resources are useful for comparing algorithms, testing transfer learning, or deciding whether a model needs 1D sequence, 2D graph, 3D physics, or multimodal inputs.

| Resource or model family | Type | Main role |
| --- | --- | --- |
| OpenPoly | AI-ready curated property benchmark | Small-data and missing-label multi-property prediction |
| POINT2 | Multi-task benchmark | Thermal, transport, density, and gas-permeability prediction with uncertainty and interpretability tests |
| PI1M | Virtual polymer structure pool | Self-supervised pretraining, generative exploration, and polymer embedding development |
| OMG | Synthesis-aware virtual polymer space | Inverse design constrained by purchasable precursors and reaction templates |
| OPoly26 / Open Polymers 2026 | Large computed dataset | Foundation-model training and large-scale computed-property learning |
| polyBERT | Sequence representation model | Dense polymer fingerprints from PSMILES-style strings |
| polyBART | Encoder-decoder/generative model | Bidirectional structure-property translation and constrained polymer generation |
| TransPolymer | Transformer property model | Transfer learning across polymer property tasks |
| polyGNN-style graph models | Graph neural networks | Atom/bond topology learning for polymer property prediction |
| MMPolymer-style multimodal models | 1D/3D contrastive pretraining | Aligning sequence information with spatial conformations for small-label property prediction |

Model-selection notes:

1. Tree ensembles with Morgan, RDKit, MACCS, or atom-pair fingerprints can remain strong baselines in small-data settings.
2. GNNs are often better suited to transition temperatures and topology-sensitive properties when graph construction is reliable.
3. MLPs with robust handcrafted descriptors can perform well for transport or free-volume-related properties.
4. General-purpose LLM few-shot prediction should be treated as a weak baseline for quantitative polymer properties unless it is grounded in curated data or tools.
5. Multimodal pretraining is most valuable when morphology, 3D packing, chain entanglement, or process history controls the target property.

## 12. Data Governance and Industrial R&D Platforms

For polymer materials, a property value is rarely meaningful without the process history that produced the sample. Good data infrastructure should connect chemical structure, formulation, synthesis, processing, characterization, computation, and final performance.

| Platform or concept | Role | Why it matters |
| --- | --- | --- |
| CRIPT | Polymer data model and relational graph architecture | Links projects, collections, experiments, processes, materials, data, and computations with persistent identifiers |
| LIMS and electronic lab notebooks | Internal R&D data capture | Preserves negative results, failed formulations, batch history, and process deviations that rarely appear in papers |
| Polymerize | Commercial polymer R&D SaaS | Standardizes formulation and experiment records and supports guided property optimization |
| PolymRize / Matmerize | Commercial active-learning platform | Uses uncertainty-aware recommendation loops for candidate selection and design-of-experiments planning |
| Dataset cards and model cards | Documentation practice | Makes dataset scope, license, splits, limitations, and intended use explicit |
| DVC, DataLad, checksums, and immutable snapshots | Version-control layer | Keeps training data, preprocessing scripts, and model evaluations reproducible |

Minimum data model for process-aware polymer AI:

1. Material: repeat-unit representation, monomer composition, additives, filler, molecular weight, dispersity, tacticity, branching, and supplier grade.
2. Process: synthesis route, catalyst, solvent, temperature, time, atmosphere, purification, extrusion, molding, annealing, shear, and thermal history.
3. Characterization: instrument, protocol, raw files, calibration, temperature, humidity, strain rate, frequency, and uncertainty.
4. Computation: force field, charge model, chain length, number of chains, equilibration protocol, simulation length, DFT settings, and random seed.
5. Outcome: property value, unit, uncertainty, failure mode, pass/fail label, and link to the exact sample or batch.

## 13. Data Integration and Expansion Strategy

Use a layered approach when building a training dataset:

1. Define the model target first: property, test condition, polymer class, representation, input modality, and acceptable uncertainty.
2. Start with standardized sources: PoLyInfo, MatNavi, OpenPoly, Khazana, Polymer Genome, OPoly26, PolyIE, and Carbon-m1 are good first-pass sources depending on the task.
3. Add task-specific resources: for example, LitChemPlast for safety/degradation, TROPIC for recycling, CopDDB/CoPolDB for copolymerization, and FTIR-Plastics for spectral identification.
4. Fill gaps with simulation: use ADEPT, RadonPy, SPACIER, MatCloud+, pylimer-tools, or custom workflows to generate consistent computed data.
5. Normalize identifiers: align records by canonical SMILES, PSMILES, BigSMILES, HELM, repeat-unit representation, InChIKey, CAS number, polymer name, monomer composition, and measurement conditions.
6. Standardize units and metadata: keep test standards, temperature, humidity, molecular weight, polydispersity, processing history, sample morphology, and uncertainty whenever available.
7. Track provenance: record source URL, publication, extraction date, license, processing script, and version.
8. Validate before modeling: deduplicate records, flag outliers, compare against handbooks or trusted measurements, and split datasets to avoid polymer-family leakage.

## 14. Recommended Tool Stack

| Need | Suggested tools |
| --- | --- |
| Structure parsing and descriptors | RDKit, SELFIES, PSMILES/PSELFIES tooling, BigSMILES tooling, HELM tooling, mordred, polymer-specific repeat-unit featurizers |
| Simulation data generation | ADEPT, RadonPy, SPACIER, LAMMPS, GROMACS, Psi4, ASE, pymatgen, MatCloud+ |
| Data cleaning and integration | pandas, polars, numpy, pydantic, DuckDB, SQLite/PostgreSQL, CRIPT-style schemas |
| Literature and web extraction | requests, httpx, BeautifulSoup, lxml, publisher APIs, Crossref, PubMed, arXiv |
| Spectra and image processing | scipy, scikit-learn, scikit-image, OpenCV, PyTorch, torchvision |
| Versioning and provenance | Git, DVC, DataLad, checksums, dataset cards |

## 15. Quality, Licensing, and FAIR Checklist

Before training or publishing a dataset, check:

- License: confirm whether the source allows academic use, commercial use, redistribution, or derivative datasets.
- Provenance: keep citations, source URLs, extraction dates, and processing history.
- Units: normalize units and retain the original units when possible.
- Conditions: preserve measurement temperature, pressure, humidity, frequency, strain rate, sample preparation, and processing history.
- Structure representation: record how repeat units, end groups, copolymer composition, branching, stereochemistry, and molecular weight were represented.
- Synthetic feasibility: keep SA Score, SCScore, precursor availability, reaction template, or retrosynthetic pathway when available.
- Negative results: preserve failed syntheses, poor-performing formulations, out-of-spec batches, and invalid simulation runs with clear labels.
- Duplicates: identify repeated records from the same paper, handbook, or database mirror.
- Uncertainty: retain reported standard deviations, ranges, and measurement methods.
- Leakage: avoid train/test splits that place near-identical polymers, copolymers, or replicated literature records in both sets.
- Accessibility: document whether the source is open, registration-based, institution-licensed, or commercial.

## 16. Key References and Starting Points

- Cao, X., Zhang, Y., Sun, Z., Yin, H. & Feng, Y. Machine learning in polymer science: A new lens for physical and chemical exploration. *Progress in Materials Science* 156, 101544 (2026). https://doi.org/10.1016/j.pmatsci.2025.101544
- Long, T. et al. Recent Progress of Artificial Intelligence Application in Polymer Materials. *Polymers* 17 (2025). https://doi.org/10.3390/polym17121667
- Polymer Data Challenges in the AI Era: Bridging Gaps for Next-Generation Energy Materials. https://arxiv.org/pdf/2505.13494
- Machine Learning in Polymer Research. https://advanced.onlinelibrary.wiley.com/doi/10.1002/adma.202413695
- NIMS polymer database PoLyInfo: an overarching view of half a million data points. https://www.tandfonline.com/doi/full/10.1080/27660400.2024.2354649
- OpenPoly: A Polymer Database Empowering Benchmarking and Multi-property Predictions. https://www.cjps.org/rc-pub/front/front-article/download/127254462/lowqualitypdf/OpenPoly:%20A%20Polymer%20Database%20Empowering%20Benchmarking%20and%20Multi-property%20Predictions.pdf
- Thermodynamics of Ring-Opening Polymerisation Informatics Collection (TROPIC). https://pubs.rsc.org/en/content/articlehtml/2026/fd/d5fd00098j
- LLNL and Meta polymer-chemistry dataset announcement. https://www.llnl.gov/article/54146/llnl-meta-co-develop-groundbreaking-polymer-chemistry-dataset-training-ai-models
- LitChemPlast: An Open Database of Chemicals Measured in Plastics. https://pubs.acs.org/doi/full/10.1021/acs.estlett.4c00355
- FTIR-Plastics dataset. https://pmc.ncbi.nlm.nih.gov/articles/PMC11252596/
- CopDDB: a descriptor database for copolymers and its applications to machine learning. https://pubs.rsc.org/en/content/articlehtml/2025/dd/d4dd00266k
- PolyIE: A Dataset of Information Extraction from Polymer Material Scientific Literature. https://ar5iv.labs.arxiv.org/html/2311.07715
- Carbon-m1: a Massive, Multi-Modal Synthetic Dataset for Complex Polymeric Materials. https://openreview.net/pdf?id=q6xm6PEhNv
- GFRP/PP FM-SEM dataset. https://pmc.ncbi.nlm.nih.gov/articles/PMC12907714/
- Detection Limits for SEM Image Segmentation. https://catalog.data.gov/dataset/detection-limits-for-sem-image-segmentation
- Open Macromolecular Genome. https://pmc.ncbi.nlm.nih.gov/articles/PMC10416319/
- RadonPy. https://github.com/RadonPy/RadonPy
- PolyMetriX. https://pypi.org/project/polymetrix/
- pylimer-tools. https://www.sciendo.com/article/10.5334/jors.609
- BigSMILES. https://bigsmiles.org/
- CRIPT. https://criptapp.org/
