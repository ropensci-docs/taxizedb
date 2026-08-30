# Download taxonomic databases

Download taxonomic databases

## Usage

``` r
db_download_ncbi(verbose = TRUE, overwrite = FALSE)

db_download_itis(verbose = TRUE, overwrite = FALSE)

db_download_tpl(verbose = TRUE, overwrite = FALSE)

db_download_wfo(verbose = TRUE, overwrite = FALSE)

db_download_col(verbose = TRUE, overwrite = FALSE)

db_download_gbif(verbose = TRUE, overwrite = FALSE)

db_download_wikidata(verbose = TRUE, overwrite = FALSE)
```

## Arguments

- verbose:

  (logical) Print messages. Default: `TRUE`

- overwrite:

  (logical) If `TRUE` force an update by overwriting previously
  downloaded data. Default: `FALSE`

## Value

(character) path to the downloaded SQL database

## Details

Downloads sql database, cleans up unneeded files, returns path to sql
file

## Note

The Plant List (TPL) is no longer accessible. If you have a copy of the
sqlite database you can still use the rest of the TPL functions with it.
We suggest using the World Flora Online (WFO) database as a replacement.

## See also

[tdb_cache](https://docs.ropensci.org/taxizedb/reference/tdb_cache.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# ITIS
db_download_itis()
src_itis()

# Plantlist
db_download_tpl()
src_tpl()

# COL
db_download_col()
src_col()

# GBIF
db_download_gbif()
src_gbif()

# NCBI
db_download_ncbi()
src_ncbi()

# Wikidata
db_download_wikidata()
db_download_wikidata(overwrite=TRUE) # overwrite - download again
src_wikidata()

# World Flora Online
db_download_wfo()
src_wfo()
} # }
```
