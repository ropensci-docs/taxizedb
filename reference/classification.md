# Retrieve the taxonomic hierarchies from local database

This function is equivalent to the
[`taxize::classification()`](https://docs.ropensci.org/taxize/reference/classification.html)
function, except that it uses a local database (so is much faster). The
output is identical to
[`taxize::classification()`](https://docs.ropensci.org/taxize/reference/classification.html)

## Usage

``` r
classification(x, db = "ncbi", verbose = TRUE, ...)
```

## Arguments

- x:

  character) Vector of taxon keys for the given database

- db:

  character) The database to search, one of ncbi, itis, gbif, col, or
  wfo

- verbose:

  (logical) Print verbose messages

- ...:

  Additional arguments passed to database specific classification
  functions.

## Value

list of data.frames with the columns: name, rank, and id. This is
exactly equivalent to the output of
[`taxize::classification()`](https://docs.ropensci.org/taxize/reference/classification.html)

## Examples

``` r
if (FALSE) { # \dontrun{
classification(c(3702, 9606))
classification(c(154395, 154357), db = "itis")
classification(c("wfo-0000291463", "wfo-7000000057"), db = "wfo")
classification(2878586, db = "gbif")
classification(c(2878586, 2704179), db = "gbif")
classification("C66T4", db = "col") # Abies Mill.
} # }
```
