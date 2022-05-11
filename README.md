
<!-- README.md is generated from README.Rmd. Please edit that file -->

# SpaceX

<!-- badges: start -->
<!-- badges: end -->

The goal of SpaceX is to provide shared and cluster specfic gene
co-expression networks for spatial transcriptomics data.

## Installation

The package requires a dependency that is not available on CRAN. Install
it with:

``` r
remotes::install_github("rdevito/MSFA")
```

You can install the released version of SpaceX from
(<https://github.com/SatwikAch/SpaceX>) with:

``` r
devtools::install_github("SatwikAch/SpaceX")
```

``` r
library(SpaceX)
#> Loading required package: PQLseq
```

``` r
## Reading the Breast cancer data

## Spatial locations
head(BC_loc)

## Gene expression for data
head(BC_count) 

## Data processing
G <-dim(BC_count)[2] ## number of genes
N <-dim(BC_count)[1] ## number of locations

## Application to SpaceX algorithm (Please make sure to request for large enough memory to work with the posterior samples)
BC_fit <- SpaceX(BC_count,BC_loc[,1:2],BC_loc[,3],sPMM=FALSE,Post_process = TRUE)

## Shared_network :: Shared co-expression matrix
## Cluster_network :: Cluster specific co-expression matrices
```

You can view the supplementary file at this link:
<https://bookdown.org/satwik91/SpaceX_supplementary/>.
