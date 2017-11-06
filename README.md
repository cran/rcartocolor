
<!-- README.md is generated from README.Rmd. Please edit that file -->
rcartocolor
===========

[![Build Status](https://travis-ci.org/Nowosad/rcartocolor.png?branch=master)](https://travis-ci.org/Nowosad/rcartocolor) [![codecov](https://codecov.io/gh/Nowosad/rcartocolor/branch/master/graph/badge.svg)](https://codecov.io/gh/Nowosad/rcartocolor) [![CRAN\_Status\_Badge](http://www.r-pkg.org/badges/version/rcartocolor)](https://cran.r-project.org/package=rcartocolor) [![CRAN RStudio mirror downloads](http://cranlogs.r-pkg.org/badges/rcartocolor)](https://cran.r-project.org/package=rcartocolor)

The goal of `rcartocolor` is to provide color schemes for maps and other graphics designed by [CARTO](https://carto.com/) as described at <https://carto.com/carto-colors/>.

Installation
------------

You can install `rcartocolor` from github with:

``` r
# install.packages("devtools")
devtools::install_github("Nowosad/rcartocolor")
```

Examples
--------

Display a CARTOcolor palette:

``` r
library(rcartocolor)
display_carto_pal(7, "Vivid")
```

![](man/figures/README-example-1.png)

Create a CARTOcolor palette:

``` r
my_colors = carto_pal(7, "Burg")
my_colors
#> [1] "#ffc6c4" "#f4a3a8" "#e38191" "#cc607d" "#ad466c" "#8b3058" "#672044"
```

Display all of the CARTOcolor palettes:

``` r
display_carto_all()
```

![](man/figures/README-example3-1.png)

``` r
library(sf)
#> Linking to GEOS 3.5.0, GDAL 2.1.2, proj.4 4.9.2
library(spData)
library(ggplot2)
ggplot(world, aes(fill = lifeExp)) +
        geom_sf(data = world) +
        coord_sf(crs = "+proj=robin") +
        scale_fill_carto_c(name = "Life expectancy: ",
                           type = "diverging", palette = "Fall", direction = -1) +
        theme_void()
```

![](man/figures/README-examplegg1-1.png)

``` r
ggplot(world, aes(fill = region_un)) +
        geom_sf(data = world) +
        coord_sf(crs = "+proj=robin")  +
        scale_fill_carto_d(name = "Region: ", palette = "Prism") +
        theme_void()
```

![](man/figures/README-examplegg2-1.png)
