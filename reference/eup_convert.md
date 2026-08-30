# Convert identifiers in the local EU Pesticides database

Convert identifiers in the local EU Pesticides database

## Usage

``` r
eup_convert(
  query,
  from,
  to,
  resource = "active_substances",
  mode = "offline",
  ...
)
```

## Arguments

- query:

  character; a character of compound identifiers to convert.

- from:

  character; the type of identifier to conver from. Can be one of
  `"substance_id"`, `"substance_name"`, or `"as_cas_number"`.

- to:

  character; the type of identifier to convert to. Can be one of
  `"substance_id"`, `"substance_name"`, or `"as_cas_number"`.

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

A data frame of converted identifiers, in the same order as the input
`query`. If an identifier could not be converted, the corresponding
output will be `NA`. If multiple matches are found for a query, all
matches will be returned in separate rows.

## Details

`"substance_id"` is the unique identifier for each active substance in
the EU Pesticides database. `"substance_name"` is the name of the active
substance, and `"as_cas_number"` is the CAS number of the active
substance.

## References

You can find more information about the EU Pesticides database at
<https://food.ec.europa.eu/plants/pesticides/eu-pesticides-database_en>.

## Examples

``` r
if (FALSE) { # \dontrun{
# Download database
db_download_eup(verbose = TRUE)

# Query downloaded database
eup_convert(1313, from = "substance_id", to = "substance_name")
eup_convert("Monolinuron", from = "substance_name", to = "as_cas_number")

eup_convert()
} # }
```
