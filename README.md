
<!-- README.md is generated from README.Rmd. Please edit that file -->

# pipedat

<!-- badges: start -->
<!-- [![Check package](https://github.com/inSileco/graphicsutils/actions/workflows/check-moreorless-standard.yaml/badge.svg)](https://github.com/inSileco/graphicsutils/actions/workflows/check-moreorless-standard.yaml) -->
<!-- [![codecov](https://codecov.io/gh/inSileco/graphicsutils/branch/master/graph/badge.svg)](https://codecov.io/gh/inSileco/graphicsutils) -->

[![lifecycle](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://www.tidyverse.org/lifecycle/#preliminary)
![](https://img.shields.io/badge/status-preliminary-blue.svg)
<!-- [![r-universe](https://insileco.r-universe.dev/badges/graphicsutils)](https://insileco.r-universe.dev/ui#builds) -->
<!-- badges: end -->

*pipedat* is a package that provides pipelines to access, load, and
format a variety of data from multiple sources programatically. The
intent of this package is to support the varying projects undertaken
under the umbrella organization *Ecosystem Assessments*. Certain
datasets are directly accessed through APIs and open data portals, while
others require a local copy of the raw data for varying reasons such as
data whose distribution is limited or protected by data sharing
agreements. The sole purpose of this package is to facilate the
reproducible use and reuse of specific datasets accross different
projects.

## Installation

The easiest way to install `pipedat` is to use
[`remotes`](https://cran.r-project.org/package=remotes):

``` r
install.packages("remotes")
remotes::install_github("Ecosystem-Assessments/pipedat")
```

Then, load it:

``` r
library(pipedat)
```

## Main features

The `pipedat` package is built around function called `pipedat()` that
is used to access, load and format a wide variety of data; this function
calls on a series of individual scripts built to access data
programmatically and reproducibly, which we refer to as *data
pipelines*. Individual data pipelines are executed by using their
*unique identifier*, which are specific to the `pipedat` package. The
full list of data pipelines available can be viewed with the
`pipelist()` function:

``` r
# View list of pipelines 
pipelist()

# Download and format a single dataset 
pipedat("a3jsd4jh")

# Download and format multiple datasets
pipedat(c("a3jsd4jh","a8732975y","soif8yiao"))
```

By default, the `pipedat()` function will export the raw and formatted
data in folders ‘data/data-raw/’ and `data/data-format`, respectively.

## How to contribute

External contributors are welcome to contribute data pipelines to this
package. Simply fork the [public repo]() and create your own data
pipeline. The `pipenew()` function creates a `p_#####.R` template for
you to use to create a new data pipeline with a unique id. Create a pull
request for us to review the data pipeline for inclusion in the package.
