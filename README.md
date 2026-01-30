# PER2-HALO and PER2-PROTAC proteomics data analysis

Analysis of a PER2-HALO experiment to determine if PER2 interacts with mTORC1 and a PER2-PROTAC experiment to see if degradation of PER2 impacts components of mTORC1


## Directory structure:
- raw: PSM, peptide and protein level output from MaxQuant.
- notebooks: R markdown notebooks for all analysis. Run in denoted order.
- results: Output from analysis notebooks
- external: Data external to project required for analysis

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