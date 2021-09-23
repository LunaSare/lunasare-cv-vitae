
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Luna Sare’s academic CV using the package `vitae`

<!-- badges: start -->

<!-- badges: end -->

The goal of lunasare-cv-vitae is to hold the source files used to build
Luna Sare’s academic CV with the
[`vitae`](https://pkg.mitchelloharawild.com/vitae/) R package.

### Steps I followed:

``` r
R -e 'rmarkdown::render("cv-hyndman/cv-hyndman.knit.md")'
#> Error: <text>:1:6: unexpected string constant
#> 1: R -e 'rmarkdown::render("cv-hyndman/cv-hyndman.knit.md")'
#>          ^
```

Install required packages:

``` r
install.packages('vitae')
install.packages('tinytex')
tinytex::install_tinytex()
install.packages("rorcid")
install.packages("scholar")
install.packages("magrittr")
library(magrittr)
```

Package versions:

``` r
packages <- c("vitae", "tinytex", "rorcid", "scholar", "magrittr")
names(packages) <- packages

lapply(packages, utils::packageVersion)
#> $vitae
#> [1] '0.4.2.9000'
#> 
#> $tinytex
#> [1] '0.33'
#> 
#> $rorcid
#> [1] '0.7.0'
#> 
#> $scholar
#> [1] '0.2.2'
#> 
#> $magrittr
#> [1] '2.0.1'
```

Getting my education with ORCID

``` r
orcid_data <- do.call("rbind",
  rorcid::orcid_educations("0000-0001-7668-2528")$`0000-0001-7668-2528`$`affiliation-group`$summaries
)
```

Getting my publications with Google;

``` r
scholar::get_publications("rpXUk04AAAAJ") %>% 
  detailed_entries(
    what = title,
    when = year,
    with = author,
    where = journal,
    why = cites
  )
```
