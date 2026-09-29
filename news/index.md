# Changelog

## taxizedb 0.3.2

CRAN release: 2025-06-18

### MINOR IMPROVEMENTS

- For certain databases, the `db_download_*()` function downloaded a
  preprocessed SQLite database from the cloud, where it was updated
  automatically e.g. daily. However, cloud access occasionally broke. To
  provide robust functionaility. `db_download_*()` was updated to
  download raw data and convert it to SQLite locally, on demand, for all
  databases. ([\#81](https://github.com/ropensci/taxizedb/issues/81))

### BUG FIXES

- Replaced
  [`readr::read_tsv_chunked`](https://readr.tidyverse.org/reference/read_delim_chunked.html)
  with
  [`vroom::vroom()`](https://vroom.tidyverse.org/reference/vroom.html)
  to avoid memory limitation for checks on macOS.
  ([\#89](https://github.com/ropensci/taxizedb/issues/89))

### DEFUNCT

- TPL is no longer available so
  [`db_download_tpl()`](https://docs.ropensci.org/taxizedb/reference/db_download.md)
  will fail. However, if the database was downloaded earlier, it can
  still be queried using `taxizedb` functions.
  ([\#87](https://github.com/ropensci/taxizedb/issues/87))

## taxizedb 0.3.1

CRAN release: 2023-04-03

- New maintainer
  ([\#65](https://github.com/ropensci/taxizedb/issues/65)).

## taxizedb 0.3.0

CRAN release: 2021-01-15

### NEW FEATURES

- [`db_download()`](https://docs.ropensci.org/taxizedb/reference/db_download.md)
  gains new parameter `overwrite` (logical): used to state that you want
  to overwrite an existing database on disk. before this you would have
  to manually delete an older database file
  ([\#34](https://github.com/ropensci/taxizedb/issues/34))
- new function added
  [`taxa_at()`](https://docs.ropensci.org/taxizedb/reference/taxa_at.md)
  for getting taxa at specific scientific ranks. For example, your known
  taxon is the family Lachnospiraceae with NCBI identifier of 186803.
  You want information on the phylum which the Lachnospiraceae family is
  in. This function can do that for you.
  ([\#51](https://github.com/ropensci/taxizedb/issues/51))

### BUG FIXES

- fixed problem in internal function `txdb_rr()`: in older verions of R
  (e.g., 3.6) we were creating a data.frame in this function without
  settings `stringsAsFactors=FALSE`, resulting in different behavior in
  R v3 vs. R v4 given the change in `stringsAsFactors` behavior in R v4
  onward ([\#54](https://github.com/ropensci/taxizedb/issues/54))

## taxizedb 0.2.2

CRAN release: 2020-08-26

### BUG FIXES

- fix failing tests
  ([\#50](https://github.com/ropensci/taxizedb/issues/50))

## taxizedb 0.2.0

CRAN release: 2020-08-13

### NEW FEATURES

- gains 3 new data sources: NCBI taxonomy, World Flora Online, Wikidata
  ([\#18](https://github.com/ropensci/taxizedb/issues/18))
  ([\#49](https://github.com/ropensci/taxizedb/issues/49))
  ([\#37](https://github.com/ropensci/taxizedb/issues/37))
- gains ports of `taxize` functions to `taxizedb` (NCBI & ITIS
  supported): `children`, `classification`, `downstream`. beware when
  both `taxize` and `taxizedb` loaded in the same R session to namespace
  calls to these three functions
  ([\#19](https://github.com/ropensci/taxizedb/issues/19))
  ([\#25](https://github.com/ropensci/taxizedb/issues/25))
  ([\#44](https://github.com/ropensci/taxizedb/issues/44))
  ([\#48](https://github.com/ropensci/taxizedb/issues/48))
- gains mapping functions: `name2taxid` (scientific or common name to
  taxonomy ID); `taxid2name` (taxonomy ID to scientific name);
  `taxid2rank` (taxonomy ID to rank)
  ([\#41](https://github.com/ropensci/taxizedb/issues/41))
  ([\#42](https://github.com/ropensci/taxizedb/issues/42))
- intro vignette added
  ([\#17](https://github.com/ropensci/taxizedb/issues/17))
- GBIF and COL data sources are not updated daily in the repos
  <https://github.com/ropenscilabs/gbif-backbone-sql> and
  <https://github.com/ropenscilabs/col-sql/> via GithHub Actions. See
  those repos for details
  ([\#26](https://github.com/ropensci/taxizedb/issues/26))
- update package level manual file (`?taxizedb-package`) with details on
  each data source, their update schedules, and examples
- all data sources now use SQLite as the database storage engine.
  passwords/ports/usernames/etc are no longer needed! note that some
  `db_download*` functions download already created SQLite databases,
  whereas for other data sources the database is built locally on your
  machine from other data formats downloaded (see also
  [\#36](https://github.com/ropensci/taxizedb/issues/36),
  [\#46](https://github.com/ropensci/taxizedb/issues/46))
- a copy of the taxonomic ranks information from taxize package was
  ported over for internal use to be able to make
  [`downstream()`](https://docs.ropensci.org/taxizedb/reference/downstream.md)
  work for most data sources

### MINOR IMPROVEMENTS

- remove check for whether SQLite is installed
  ([\#5](https://github.com/ropensci/taxizedb/issues/5)
  [\#29](https://github.com/ropensci/taxizedb/issues/29))
- all `src_*` functions now only have two paramters: `path` and `...`.
  where path by default figures out the path for you using the function
  [`db_path()`](https://docs.ropensci.org/taxizedb/reference/db_path.md),
  and `...` allows the user to pass on parameters to
  [`DBI::dbConnect`](https://dbi.r-dbi.org/reference/dbConnect.html)

### DEFUNCT

- `db_load()` is now defunct. Now just use `db_download*` then `src*`
  for your data source (see also
  [\#43](https://github.com/ropensci/taxizedb/issues/43))

## taxizedb 0.1.4

CRAN release: 2017-06-20

### BUG FIXES

- Fixes to SQL database connection functions for changes in `dplyr`,
  which now requires `dbplyr` package - also `DBI` now imported
  ([\#16](https://github.com/ropensci/taxizedb/issues/16))

## taxizedb 0.1.0

CRAN release: 2017-05-03

### NEW FEATURES

- Released to CRAN
