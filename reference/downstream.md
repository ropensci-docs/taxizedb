# Retrieve all taxa descending from a vector of taxa

This function is nearly equivalent to the
[`taxize::downstream()`](https://docs.ropensci.org/taxize/reference/downstream.html)
function

## Usage

``` r
downstream(x, db = "ncbi", verbose = TRUE, ...)
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

  Additional arguments passed to database specific downstream functions

## Value

list of data.frames with the columns: childtaxa_id, childtaxa_name, and
rank. This is exactly equivalent to the output of
[`taxize::downstream()`](https://docs.ropensci.org/taxize/reference/downstream.html)

## Examples

``` r
if (FALSE) { # \dontrun{
# get descendents from all ranks
# downstream(c(3700, 9605)) # takes a while

# limit results to species
downstream(c(3700, 9605), downto='species')

# allow ambiguous nodes but no ambiguous species
downstream(
  c(3700, 9605),
  downto='species',
  ambiguous_nodes=FALSE,
  ambiguous_species=TRUE
)

# ITIS
id <- name2taxid('Aves', db = "itis")
downstream(id, db = "itis", downto = "family")
downstream(id, db = "itis", downto = "genus")
id <- name2taxid('Bombus', db = "itis")
downstream(id, db = "itis", downto = "species")

# COL
id <- name2taxid('Chordata', db = "col")
downstream(id, db = "col", downto = "family")

# GBIF
id <- name2taxid('Pinaceae', db = "gbif")
downstream(id, db = "gbif", downto = "genus")

# World Flora Online
id <- name2taxid('Pinaceae', db = "wfo")
downstream(id, db = "wfo", downto = "species")
} # }
```
