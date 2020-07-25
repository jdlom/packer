<div align="center">

<!-- badges: start -->
[![R build status](https://github.com/JohnCoene/packer/workflows/R-CMD-check/badge.svg)](https://github.com/JohnCoene/packer/actions)
<!-- badges: end -->

An opinionated and robust framework for using JavaScript with R.

# packer

</div>

## Installation

Packer is not yet available on CRAN but can be obtained from Github using `remotes` or `devtools`.

``` r
# install.packages("remotes")
remotes::install_github("JohnCoene/packer")
```

## Usage

At its core packer consists of functions to scaffold R packages powered by webpack and npm, these take the form of scaffolds which are built on top of packages. All of the functions listed below need to be run from within an R package.

* `scaffold_widget` - Scaffold an [htmlwidgets](http://www.htmlwidgets.org/) with webpack.
* `scaffold_golem` - Use webpack with [golem](http://golemverse.org/).
* `scaffold_extension` - Scaffold a shiny extension, e.g.: [shinyjs](https://deanattali.com/shinyjs/) or [waiter](https://waiter.john-coene.com/).
* `scaffold_input` - Scaffold a custom shiny input.
* `scaffold_output` - Scaffold a custom shiny output.

## Example

Always start from an empty package and run `scaffold_*` to set up the required basic structure.

```r
usethis::create_package("inputPkg")
packer::scaffold_input("increment")
```

Once the scaffold laid down you can either `bundle` the JavaScript or `watch` for changes as you develop it.

```r
packer::bundle()
```

You can then document and install the package to try it out.

## Inspiration

This package is heavily inspired by [devtools](http://devtools.r-lib.org/), [golem](http://golemverse.org/), [htmlwidgets](http://www.htmlwidgets.org/), and [usethis](https://usethis.r-lib.org/).