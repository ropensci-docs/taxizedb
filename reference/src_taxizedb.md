# src - dplyr src objects

src - dplyr src objects

## Usage

``` r
src_itis(path = db_path("itis"), ...)

src_tpl(path = db_path("tpl"), ...)

src_col(path = db_path("col"), ...)

src_gbif(path = db_path("gbif"), ...)

src_ncbi(path = db_path("ncbi"), ...)

src_wikidata(path = db_path("wikidata"), ...)

src_wfo(path = db_path("wfo"), ...)
```

## Arguments

- path:

  (character) path to SQLite database. by default we use the function
  [`db_path()`](https://docs.ropensci.org/taxizedb/reference/db_path.md)
  to get the path

- ...:

  Further args passed on to
  [`DBI::dbConnect()`](https://dbi.r-dbi.org/reference/dbConnect.html)

## Value

an src object

## Examples

``` r
if (FALSE) { # \dontrun{
src_itis()
src_tpl()
src_col()
src_gbif()
src_ncbi()
src_wikidata()
src_wfo()
} # }
```
