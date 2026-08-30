# Convert taxon IDs to scientific ranks

Convert taxon IDs to scientific ranks

## Usage

``` r
taxid2rank(x, db = "ncbi", verbose = TRUE, warn = TRUE, ...)
```

## Arguments

- x:

  (character) Vector of taxon keys (name or id) for the given database

- db:

  (character) The database to search, one of ncbi, itis, gbif, col, or
  wfo

- verbose:

  (logical) Print verbose messages

- warn:

  (logical) If `TRUE`, raise a warning if any taxon IDs can not be found

- ...:

  Additional arguments passed to database specific classification
  functions

## Value

character vector of ranks in the same order as the inputs

## Examples

``` r
if (FALSE) { # \dontrun{
taxid2rank(c(3701, 9606))
taxid2rank(c(154395, 154357, 23041, 154396), db = "itis")
taxid2rank(c('wfo-4000032377', 'wfo-0000541830'), db = "wfo")
taxid2rank("wfo-7000000057", db = "wfo")
taxid2rank(2877951, db = "gbif")
taxid2rank(c(2877951, 5386), db = "gbif")
taxid2rank(c("C66T4", "C7ZVH", "TP"), db = "col")
} # }
```
