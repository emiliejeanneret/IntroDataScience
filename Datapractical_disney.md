Datapractical_disney
================
2022-11-23

![](pexels-benjamin-suter-2362002.jpg)

## Introduction

Disney movies are know across the world. It is for that reason that we
can to understand *why* disney movies are so famous and engender so much
money.

# Data

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.2 ──
    ## ✔ ggplot2 3.3.6      ✔ purrr   0.3.4 
    ## ✔ tibble  3.1.8      ✔ dplyr   1.0.10
    ## ✔ tidyr   1.2.1      ✔ stringr 1.4.1 
    ## ✔ readr   2.1.3      ✔ forcats 0.5.2 
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
total_gross <- read.csv("disney_movies_total_gross.csv")
head(total_gross)
```

    ##   index                     movie_title release_date     genre MPAA_rating
    ## 1     0 Snow White and the Seven Dwarfs Dec 21, 1937   Musical           G
    ## 2     1                       Pinocchio  Feb 9, 1940 Adventure           G
    ## 3     2                        Fantasia Nov 13, 1940   Musical           G
    ## 4     3               Song of the South Nov 12, 1946 Adventure           G
    ## 5     4                      Cinderella Feb 15, 1950     Drama           G
    ## 6     5    20,000 Leagues Under the Sea Dec 23, 1954 Adventure            
    ##    total_gross inflation_adjusted_gross
    ## 1 $184,925,485           $5,228,953,251
    ## 2  $84,300,000           $2,188,229,052
    ## 3  $83,320,000           $2,187,090,808
    ## 4  $65,000,000           $1,078,510,579
    ## 5  $85,000,000             $920,608,730
    ## 6  $28,200,000             $528,279,994

# Analysis

# Conclusion
