# Check data source coverage of compounds

Checks if entries are found in (most) data sources included in webchem

## Usage

``` r
find_db(
  query,
  from,
  sources = c("etox", "pc", "chebi", "cs", "bcpc", "fn", "srs"),
  plot = FALSE
)
```

## Arguments

- query:

  character; the search term

- from:

  character; the format or type of query. Commonly accepted values are
  "name", "cas", "inchi", and "inchikey"

- sources:

  character; which data sources to check. Data sources are identified by
  the prefix associated with webchem functions that query those
  databases. If not specified, all data sources listed will be checked.

- plot:

  logical; plot a graphical representation of results.

## Value

a tibble of logical values where `TRUE` indicates that a data source
contains a record for the query

## Examples

``` r
if (FALSE) { # \dontrun{
find_db("hexane", from = "name")
} # }
```
