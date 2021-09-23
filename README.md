
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Luna Sare’s academic CV using the package `vitae`

<!-- badges: start -->

<!-- badges: end -->

The goal of lunasare-cv-vitae is to hold the source files used to build
Luna Sare’s academic CV with the
[`vitae`](https://pkg.mitchelloharawild.com/vitae/) R package.

### Steps I followed:

Install required packages:

``` r
install.packages('vitae')
install.packages('tinytex')
tinytex::install_tinytex()
```

Package versions:

``` r
utils::packageVersion('vitae')
utils::packageVersion('tinytex')
```

Getting my publications:

``` r
orcid_data <- do.call("rbind",
  rorcid::orcid_educations("0000-0002-2140-5352")$`0000-0002-2140-5352`$`affiliation-group`$summaries
)
```
