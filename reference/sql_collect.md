# Query and get data back into a data.frame

Execute and SQL query on a database.

## Usage

``` r
sql_collect(src, query, ...)
```

## Arguments

- src:

  (src) An `src` object, result of calling
  [`src_itis()`](https://docs.ropensci.org/taxizedb/reference/src_taxizedb.md),
  [`src_col()`](https://docs.ropensci.org/taxizedb/reference/src_taxizedb.md),
  or
  [`src_tpl()`](https://docs.ropensci.org/taxizedb/reference/src_taxizedb.md)

- query:

  (character) A SQL query

- ...:

  further args passed on to
  [`dplyr::tbl()`](https://dplyr.tidyverse.org/reference/tbl.html)

## Value

A tibble with query results.

## Details

we run [`dplyr::tbl()`](https://dplyr.tidyverse.org/reference/tbl.html),
then
[`dplyr::collect()`](https://dplyr.tidyverse.org/reference/compute.html)

## Examples

``` r
if (FALSE) { # \dontrun{
src <- src_itis()
sql_collect(src, "select * from hierarchy limit 5")
## or pipe the src to sql_collect
src |> sql_collect("select * from hierarchy limit 5")
} # }
```
