# Query the local FooDB database for compound information

Query the local FooDB database for compound information

## Usage

``` r
foodb_query(query, from = "name", verbose = getOption("verbose"))
```

## Arguments

- query:

  character; a vector of compound identifiers to query.

- from:

  character; the type of identifier provided in \`query\`. Allowed
  values are: "id", "public_id", "name".

- verbose:

  logical; should verbose messages be printed to the console?

## Value

A nested list of fields for each compound query, with available
information from the FooDB database. If a query does not match any
compound in the database, the corresponding output will be \`NA\`.

## Note

When using ID types not supported by `foodb_query()` (e.g., CAS number
or InChIKey), first convert them to a supported ID type using
[`foodb_convert()`](https://docs.ropensci.org/webchem/reference/foodb_convert.md)
before querying with `foodb_query()`.

## Examples

``` r
if (FALSE) { # \dontrun{
# single query
foodb_query("Biotin")

# multiple queries
foodb_query(c("Biotin", "Folic acid"))
} # }
```
