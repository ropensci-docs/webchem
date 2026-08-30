# Query EU Pesticides

Query EU Pesticides

## Usage

``` r
eup_query(query, resource, mode = "offline", ...)
```

## Arguments

- query:

  numeric; a vector of IDs. The type of ID depends on the resource. See
  examples for more information.

- resource:

  character; the EU Pesticides resource to query. Can be one of
  `"active_substances"` or `"residues"`.

- mode:

  character; the mode of operation. Can be one of `"offline"` (offline
  access) or `"ws"` (web service access). Currently only offline mode is
  implemented.

- ...:

  Further args passed on to \[DBI::dbConnect()\]

## Value

A data frame containing information about the specified entry.

## References

You can find more information about the EU Pesticides database at
<https://food.ec.europa.eu/plants/pesticides/eu-pesticides-database_en>.

## Examples

``` r
if (FALSE) { # \dontrun{
# Download database
db_download_eup(verbose = TRUE)

# Retrieve information about active substances
eup_query(query = c(1313, 1314), resource = "active_substances")

# Retrieve information about residues
eup_query(query = c(1, 2), resource = "residues")
} # }
```
