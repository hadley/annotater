
<!-- README.md is generated from README.Rmd. Please edit that file -->

# annotater

## The main course

![look\!](https://raw.githubusercontent.com/luisdva/annotater/master/inst/media/annotcalls.gif)

![look\!](https://raw.githubusercontent.com/luisdva/annotater/master/inst/media/repos1.gif)

The goal of annotater is to annotate package load calls in text strings
and R scripts, so we can have an idea of the overall purpose of the
libraries we’re loading.

The other main feature helps us annotate the package load calls with the
repository source when a package is not installed from CRAN. Thanks to
[Jonathan Carroll](https://github.com/jonocarroll) for the suggestion.

This project came about after teaching workshops or helping peers and
realizing that many issues relate to package installation failures and
dependency issues for packages that are not even used in a problematic
script. Scripts get passed around, code is copied and pasted, and we
might not know what certain packages are for.

## Installation

You can install the development version of annotater from GitHub with:

``` r
# install.packages("devtools")
devtools::install_github("luisDVA/annotater")
```

Alternatively:

``` r
# install.packages("remotes")
remotes::install_github("luisDVA/annotater")
```

I suggest restarting RStudio after the installation for the addins to
load properly.

## Example

This is a basic example with a simple character string.

``` r
library(annotater)
test_string <-c("library(boot)\nrequire(Matrix)")
writeLines(annotate_pckg_calls(test_string))
#> library(boot) # Bootstrap Functions (Originally by Angelo Canty for S)
#> require(Matrix) # Sparse and Dense Matrix Classes and Methods
```

Entire .R files can also be parsed and annotated with the
*annotate\_script* function.

Try it out\! Feedback welcome
