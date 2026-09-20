# Protein Structure Prediction and Structural Bioinformatics Analysis

Course project completed for **Macromolecular Structure Prediction** at **Amirkabir University of Technology (Tehran Polytechnic)**.

This repository documents a comparative structural-bioinformatics analysis of two viral proteins. The work combines sequence-level characterization, domain and motif annotation, homology modeling, AlphaFold2 structure prediction, comparison with experimentally resolved PDB structures, structural alignment, geometric validation, and structure-function interpretation.

The project was originally prepared as a detailed technical report in Persian. This README provides a complete English overview so that the methodology, scope, and main findings can be evaluated independently of the report language.

## Project Scope

The analysis was organized around two proteins with substantially different structural properties:

- **Protein A:** a comparatively compact viral nucleoprotein with predominantly alpha-helical architecture.
- **Protein B:** a coronavirus nucleocapsid protein with distinct N-terminal and C-terminal domains, RNA-binding function, and substantial intrinsically disordered regions.

Rather than relying on a single prediction tool, the project compared evidence from sequence analysis, domain databases, homology modeling, AlphaFold2, experimental structures, and structure-quality assessment.

## Analysis Workflow

### 1. Sequence characterization

Both proteins were first analyzed at the sequence level using physicochemical and topology-oriented tools.

The workflow included:

- sequence length and amino-acid composition;
- molecular weight and theoretical isoelectric point;
- charged-residue composition;
- Kyte-Doolittle hydropathy profiling;
- transmembrane-topology prediction;
- motif scanning and interpretation of candidate post-translational modification sites.

**Tools:** ExPASy ProtParam, ExPASy ProtScale, DeepTMHMM, ScanProsite.

### 2. Family, domain, and structural annotation

Sequence-based annotation was used to determine protein-family membership, domain organization, and potentially disordered regions.

For Protein B, the analysis identified the characteristic coronavirus nucleocapsid domains:

- **CoV N-terminal RNA-binding domain (NTD)**
- **CoV C-terminal dimerization/oligomerization domain (CTD)**

The analysis also considered intrinsically disordered regions and functional annotations associated with RNA binding and viral nucleocapsid activity.

**Resources:** InterProScan, InterPro, MobiDB annotations, CATH, SCOP.

### 3. Homology modeling

Homology models were generated with **SWISS-MODEL**.

Template selection was assessed using:

- sequence identity;
- alignment coverage;
- GMQE;
- QMEANDisCo;
- QMEAN Z-score;
- local model-quality profiles.

Protein A had a high-identity, high-coverage template and was therefore well suited to homology modeling. Protein B had strong template support only for part of the sequence, particularly the N-terminal domain, illustrating the limitation of template-based modeling for proteins containing flexible or poorly covered regions.

### 4. AlphaFold2 structure prediction

AlphaFold2 predictions were evaluated using:

- **pLDDT** for local confidence;
- **pTM** for global structural confidence;
- **PAE (Predicted Aligned Error)** for confidence in relative domain placement.

The two proteins showed different confidence patterns. Protein A had high confidence across most of the structure, whereas Protein B contained well-defined structured domains separated by lower-confidence and more flexible regions.

### 5. Experimental structure selection

Relevant experimentally determined structures were identified in the **Protein Data Bank (PDB)** and selected as references based on sequence identity, coverage, experimental method, and structural relevance.

Representative references used in the analysis included:

- a high-identity experimental structure for Protein A;
- an experimentally resolved N-terminal-domain structure for Protein B.

This allowed the predicted models to be compared against experimental coordinates rather than evaluated only through internal model-confidence scores.

### 6. Structural alignment and model comparison

Predicted and experimental structures were aligned in **PyMOL**.

Comparisons included:

- homology model vs. experimental structure;
- AlphaFold2 model vs. experimental structure;
- RMSD-based structural agreement;
- visual inspection of conserved structural cores and flexible regions.

For Protein A, both approaches showed close agreement with the experimental structure. For Protein B, the structured N-terminal domain aligned well, while the full-length AlphaFold2 model provided additional information about regions that could not be modeled completely by homology.

### 7. Structural quality validation

Structural geometry was evaluated using **MolProbity** and related validation measures.

The analysis included:

- Ramachandran favored/allowed/outlier statistics;
- clashscore;
- side-chain rotamer quality;
- bond and angle geometry;
- MolProbity score;
- local backbone-quality indicators.

These measures were used to distinguish confidence in the structured cores from uncertainty associated with flexible loops and intrinsically disordered regions.

### 8. Structure-function interpretation

The final stage integrated sequence and structural evidence to interpret biological function.

The analysis examined:

- hydrophobic-core organization;
- surface distribution of charged residues;
- RNA-binding regions;
- protein-protein interaction regions;
- structured vs. intrinsically disordered segments;
- domain organization;
- accessibility of functional regions.

For Protein B, the positively charged surface of the N-terminal domain was consistent with RNA-binding function. The presence of distinct structured domains and flexible/disordered regions also helped explain why full-length homology modeling was less complete than AlphaFold-based prediction.

## Main Comparative Findings

### Protein A

- Predominantly compact and alpha-helical.
- Strong template support for homology modeling.
- Homology and AlphaFold2 models both showed close structural agreement with the experimental reference.
- Most structural uncertainty was concentrated in terminal or flexible loop regions.
- Surface charge and interaction-region analysis were consistent with nucleoprotein function.

### Protein B

- More structurally heterogeneous, with defined NTD/CTD domains and extended flexible regions.
- Strong homology-model support was available mainly for the structured N-terminal domain rather than the complete sequence.
- AlphaFold2 provided a full-length model and clearly separated high-confidence domains from low-confidence/disordered regions.
- The N-terminal domain showed a positively charged surface consistent with RNA binding.
- Geometric validation highlighted that low-confidence flexible regions should be interpreted differently from the well-structured domain cores.

## Tools and Databases

| Category | Tools / Resources |
|---|---|
| Sequence properties | ExPASy ProtParam, ExPASy ProtScale |
| Topology prediction | DeepTMHMM |
| Motif analysis | ScanProsite |
| Domain and family annotation | InterProScan, InterPro |
| Structural classification | CATH, SCOP |
| Disorder annotation | MobiDB-derived annotations |
| Homology modeling | SWISS-MODEL |
| AI structure prediction | AlphaFold2 |
| Experimental structures | Protein Data Bank (PDB) |
| Structural visualization and alignment | PyMOL |
| Structure validation | MolProbity |

## What This Repository Represents

This is a **structural-bioinformatics analysis project**, not a software library.

The work was carried out primarily through established bioinformatics servers, databases, and molecular-visualization software rather than through a custom codebase. The repository is therefore intended to document:

- the analytical workflow;
- tool selection and interpretation;
- comparative modeling decisions;
- validation methodology;
- biological interpretation of the resulting structures.

This distinction is intentional: the project demonstrates practical structural-bioinformatics analysis rather than presenting an original computational package.

## Academic Context

- **Course:** Macromolecular Structure Prediction
- **Institution:** Amirkabir University of Technology (Tehran Polytechnic)
- **Term:** Fall 2025
- **Author:** Maryam Jabbari
- **Instructors:** Dr. F. Zare and Dr. Z. Ghorbanali

## Report Language

The complete technical report was written in **Persian** as part of the original coursework. This English README is designed to make the full scope, methodology, and major conclusions accessible to international reviewers.

## Notes on Interpretation

This project is a course-based comparative analysis. It should not be interpreted as a new structure-prediction method or as an independent experimental validation study.

Several conclusions are necessarily tool- and model-dependent. In particular:

- AlphaFold confidence scores are prediction-confidence measures, not experimental validation.
- Homology-model quality depends strongly on template availability and sequence coverage.
- Motif predictions do not by themselves establish that a post-translational modification occurs biologically.
- Low-confidence/disordered regions require more cautious structural interpretation than well-resolved domain cores.

## Author

**Maryam Jabbari**  
M.Sc. Bioinformatics, Amirkabir University of Technology
