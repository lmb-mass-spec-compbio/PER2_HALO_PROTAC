# Update this text!!!

# Project Title

Contact: XXX.
Monday ID: XXXX

## Directory structure:
- raw: PSM, peptide and protein level output from PD. 
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
ggplot2



### Bioconductor
QFeatures


### Github
Install `biomasslmb` with:

``` r
remotes::install_github("lmb-mass-spec-compbio/biomasslmb", dependencies = TRUE)
```

Install `uniprotREST` with:

``` r
remotes::install_github("csdaw/uniprotREST", dependencies = TRUE)
```