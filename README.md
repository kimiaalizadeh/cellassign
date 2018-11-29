# cellassign

`cellassign` automatically assigns single-cell RNA-seq data to known cell types across thousands of cells accounting for patient and batch specific effects. Information about *a priori* known markers cell types is provided as input to the model in the form of a (binary) marker gene by cell-type matrix. `cellassign` then probabilistically assigns each cell to a cell type, removing subjective biases from typical unsupervised clustering workflows.

# Getting started

## Installation

`cellassign` is built using Google's Tensorflow, and as such requires installation of the R package `tensorflow`:

``` r
install.packages("tensorflow")
tensorflow::install_tensorflow()
```

`cellassign` can then be installed from github:

``` r
install.packages("devtools") # If not already installed
devtools::install_github("Irrationone/cellassign")
```

## Usage

`cellassign` requires the following inputs:

* `exprs_obj`: Cell-by-gene matrix of raw counts (or SingleCellExperiment with `counts` assay)
* `marker_gene_info`: Binary gene-by-celltype marker gene matrix or list relating cell types to marker genes
* `s`: Size factors
* `X`: Design matrix for any patient/batch specific effects

The model can be run as follows:

``` r
cas <- cellassign_em(exprs_obj = gene_expression_data,
                    marker_gene_info = marker_gene_info,
                    s = s,
                    X = X)
```

# Paper

TBA ...

# Authors

Allen W Zhang, University of British Columbia

Kieran R Campbell, University of British Columbia
