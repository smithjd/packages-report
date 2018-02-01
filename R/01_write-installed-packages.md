01\_write-installed-packages.R
================
jds
Thu Feb 1 11:46:59 2018

``` r
## deja vu from yesterday!
library(tidyverse)
```

    ## ── Attaching packages ───────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 2.2.1.9000     ✔ purrr   0.2.4     
    ## ✔ tibble  1.3.4          ✔ dplyr   0.7.4     
    ## ✔ tidyr   0.7.2          ✔ stringr 1.2.0     
    ## ✔ readr   1.1.1          ✔ forcats 0.2.0

    ## ── Conflicts ──────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(fs)
library(here)
```

    ## here() starts at /Users/jds/Documents/Library/R/jenny-forgot/packages-report

``` r
## create a data frame of your installed packages
ipt <- installed.packages() %>%
  as_tibble() %>%
  select(Package, LibPath, Version, Priority, Built)

## keep the variables
##   * Package
##   * LibPath
##   * Version
##   * Priority
##   * Built

## write it to data/installed-packages.csv

write_csv(ipt, here("data", "installed-packages.csv"))

## YES overwrite the file that is there now
## that came from me (Jenny)
## it an example of what yours should look like

## when this script works, stage & commit it and the csv file
## PUSH!
```
