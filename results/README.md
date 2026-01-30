## Directory of results

### HALO_wide_format_protein.tsv
Protein abundance data in wide format. Protein abundance values are log2-transformed.

Columns:
- **UniprotID**
- **HA_1 / HA_2 / HA_3**: HALO replicates 1–3
- **P2H_1 / P2H_2 / P2H_3**: PER2-HALO replicates 1–3

---

### HALO_long_format_protein.tsv
Protein abundance data in long format. Protein abundance values are log2-transformed.

Columns:
- **Leading.razor.protein**: UniProt ID(s)
- **Gene.Names.First**: First gene name, usually the canonical gene name
- **condition**: HALO (HA) or PER2-HALO (P2H)
- **replicate**: Replicate number (1–3)
- **abundance**: Log2-transformed protein abundance
- **std_error**: Standard error of protein abundance, as estimated by *limpa*
- **any_pep_quant**: Logical indicator of whether the protein was quantified by any peptides in this sample

---

### HALO_limpa_results.tsv
Summary of statistical testing for differences in protein abundance between PER2-HALO and HALO conditions. Statistical testing was performed using *limpa* and *limma*, an extension of linear modeling. The test is conceptually similar to a t-test, with moderated statistics obtained by sharing information across proteins to reduce false positives and false negatives. Positive fold changes indicate higher abundance in PER2-HALO.

Columns:
- **Leading.razor.protein**: UniProt ID(s)
- **Entry.Name**: UniProt entry name
- **Protein.names**: Protein names
- **Gene.Names**: All gene names
- **Gene.Names.First**: First gene name, usually the canonical gene name
- **NPeptides**: Number of quantified peptides
- **logFC**: Log2 fold change (PER2-HALO vs HALO)
- **CI.L, CI.R**: Left and right boundaries of the 95% confidence interval for logFC
- **AveExpr**: Mean protein abundance
- **P.Value**: P-value from the statistical test
- **adj.P.Val**: P-value adjusted for multiple testing

---

### PROTAC_wide_format_protein.tsv
Protein abundance data in wide format. Protein abundance values are log2-transformed.

Columns:
- **UniprotID**
- **DMSO_1 / DMSO_2 / DMSO_3**: DMSO replicates 1–3
- **PROTAC_1 / PROTAC_2 / PROTAC_3**: PROTAC replicates 1–3

---

### PROTAC_long_format_protein.tsv
Protein abundance data in long format. Protein abundance values are log2-transformed.

Columns:
- **UniprotID**
- **Gene.Names**: All gene names
- **Gene.Names.First**: First gene name, usually the canonical gene name
- **Protein.names**: Protein description from UniProt
- **condition**: PROTAC or DMSO
- **replicate**: Replicate number (1–3)
- **abundance**: Log2-transformed protein abundance

---

### PROTAC_long_format_phospho.tsv
Phosphorylation abundance data in long format. Abundance values are log2-transformed.

Columns:
- **UniprotID**
- **phosphopeptide**: UniProt ID concatenated with phosphosite(s)
- **ptm_positions_prot**: Phosphosite position(s) on the protein; NA if positions could not be determined
- **Gene.Names**: All gene names
- **Gene.Names.First**: First gene name, usually the canonical gene name
- **Protein.names**: Protein description from UniProt
- **condition**: PROTAC or DMSO
- **replicate**: Replicate number (1–3)
- **abundance**: Log2-transformed phosphorylation abundance

---

### PROTAC_phospho_limma_results.tsv
Summary of statistical testing for differences in phosphorylation abundance between PROTAC and DMSO conditions. Statistical testing was performed using *limma*, an extension of linear modeling. The test uses moderated statistics that borrow information across sites to reduce false positives and false negatives. Positive fold changes indicate higher phosphorylation in PROTAC relative to DMSO.

Columns:
- **UniprotID**
- **phosphopeptide**: UniProt ID concatenated with phosphosite(s)
- **phospho_pos**: Phosphosite position(s); NA if positions could not be determined
- **logFC**: Log2 fold change (PROTAC vs DMSO)
- **P.Value**: P-value from the statistical test
- **adj.P.Val**: P-value adjusted for multiple testing
- **Protein.names**: Protein names
- **Gene.Names**: All gene names
- **Gene.Names.First**: First gene name, usually the canonical gene name
- **site_seq**: 15 amino acids surrounding the phosphosite. Padded with `_` if the site is at a protein terminus. NA if the phosphopeptide contains multiple phosphosites.
