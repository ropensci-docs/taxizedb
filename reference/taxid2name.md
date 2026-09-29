# Convert taxon IDs to scientific names

Convert taxon IDs to scientific names

## Usage

``` r
taxid2name(x, db = "ncbi", verbose = TRUE, warn = TRUE, ...)
```

## Arguments

- x:

  (character) Vector of taxon keys for the given database

- db:

  (character) The database to search, one of ncbi, itis, gbif, col, wfo,
  or tpl

- verbose:

  (logical) Print verbose messages

- warn:

  (logical) If `TRUE`, raise a warning if any taxon IDs can not be found

- ...:

  Additional arguments passed to database specific classification
  functions

## Value

character vector of scientific names

## Examples

``` r
if (FALSE) { # \dontrun{
taxid2name(c(3702, 9606))
taxid2name(c(154395, 154357, 23041, 154396), db = "itis")
taxid2name(c('wfo-0000541830', 'wfo-0000291463'), db = "wfo")
taxid2name("wfo-7000000057", db = "wfo")
taxid2name(2877951, db = "gbif")
taxid2name(c(2877951, 5386), db = "gbif")
taxid2name(c("C66T4", "C7ZVH", "TP"), db = "col")
taxid2name(c("kew-2614538", "kew-2895433", "kew-2615007"), db = "tpl")
} # }
```
