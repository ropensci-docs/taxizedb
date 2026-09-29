# Retrieve immediate descendents of a taxon

Retrieve immediate descendents of a taxon

## Usage

``` r
children(x, db = "ncbi", verbose = TRUE, ...)
```

## Arguments

- x:

  (character) Vector of taxon keys for the given database

- db:

  (character) The database to search, one of ncbi, itis, gbif, col, or
  wfo

- verbose:

  (logical) Print verbose messages

- ...:

  Additional arguments passed to database specific function.

## Value

list of tibbles with the columns: id, name, rank. This is exactly
equivalent to the output of
[`taxize::children()`](https://docs.ropensci.org/taxize/reference/children.html)

## Examples

``` r
if (FALSE) { # \dontrun{
children(c(3700, 2))
children(c(154395, 154357), db = "itis")
children("wfo-4000032377", db = "wfo")
children(2877951, db = "gbif")
children("C66T4", db = "col") # Abies Mill. Mill.
} # }
```
