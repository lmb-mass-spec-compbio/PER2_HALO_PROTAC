# PER2-HALO and PER2-PROTAC proteomics data analysis

Analysis of a PER2-HALO experiment to determine if PER2 interacts with mTORC1 and a PER2-PROTAC experiment to see if degradation of PER2 impacts mTORC1 signalling


## Directory structure:
- raw: PSM, peptide and protein level output from MaxQuant.
- notebooks: R markdown notebooks for all analysis. Run in denoted order.
- results: Output from analysis notebooks
- external: Data external to project required for analysis

## Running the notebooks
Notebooks must be run in numerical order (`0_...` to `4_...`). Notebook
`0_get_annotations.rmd` must be run first: it downloads UniProt protein
details and GO annotations to `external/`, which notebooks 1-4 all depend on.
Since files in `external/` are not stored in the repository (see
`external/README`), they will not exist on a fresh clone until notebook 0 has
been run at least once. Notebook 0 requires network access.

## Dependencies for R markdown notebooks:
All the dependencies are R packages.\
For CRAN use `install.packages()`\
For Bioconductor, use `BiocManager::install()`\
Both the above functions will take multiple package names, e.g `BiocManager::install(c(QFeatures, limma))`


### CRAN
here\
tidyr\
dplyr\
tibble\
ggplot2\
ggrepel\
ggbeeswarm\
openxlsx\
xml2\
knitr


### Bioconductor
QFeatures\
limma\
limpa


### Github
Install `biomasslmb` with:

``` r
remotes::install_github("lmb-mass-spec-compbio/biomasslmb", dependencies = TRUE)
```

Install `uniprotREST` with:

``` r
remotes::install_github("csdaw/uniprotREST", dependencies = TRUE)
```