lab5555
================
YUEXU
2/8/2022

``` r
library(ggplot2)
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
library(moderndive)
library(gapminder)
library(skimr)
```

``` r
View(evals)
```

``` r
evals.scores <- evals %>%
  select(score, bty_avg)
evals.scores %>%
  skim()
```

|                                                  |            |
|:-------------------------------------------------|:-----------|
| Name                                             | Piped data |
| Number of rows                                   | 463        |
| Number of columns                                | 2          |
| \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_   |            |
| Column type frequency:                           |            |
| numeric                                          | 2          |
| \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ |            |
| Group variables                                  | None       |

Data summary

**Variable type: numeric**

| skim_variable | n_missing | complete_rate | mean |   sd |   p0 |  p25 |  p50 | p75 | p100 | hist  |
|:--------------|----------:|--------------:|-----:|-----:|-----:|-----:|-----:|----:|-----:|:------|
| score         |         0 |             1 | 4.17 | 0.54 | 2.30 | 3.80 | 4.30 | 4.6 | 5.00 | ▁▁▅▇▇ |
| bty_avg       |         0 |             1 | 4.42 | 1.53 | 1.67 | 3.17 | 4.33 | 5.5 | 8.17 | ▃▇▇▃▂ |

``` r
evals.scores %>%
  get_correlation(formula = score ~ bty_avg)
```

    ## # A tibble: 1 × 1
    ##     cor
    ##   <dbl>
    ## 1 0.187

``` r
ggplot(evals.scores, aes(x = bty_avg, y = score)) +
  geom_point()
```

![](lab5_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->
