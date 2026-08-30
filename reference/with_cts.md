# Auto-translate identifiers and search databases

Supply a query of any type (e.g. SMILES, CAS, name, InChI, etc.) along
with any webchem function that has `query` and `from` arguments. If the
function doesn't accept the type of query you've supplied, this will try
to automatically translate it using CTS and run the query.

## Usage

``` r
with_cts(query, from, .f, .verbose = getOption("verbose"), ...)
```

## Arguments

- query:

  character; the search term

- from:

  character; the format or type of query. Commonly accepted values are
  "name", "cas", "inchi", and "inchikey"

- .f:

  character; the (quoted) name of a webchem function

- .verbose:

  logical; print a message when translating query?

- ...:

  other arguments passed to the function specified with `.f`

## Value

returns results from `.f`

## Note

During the translation step, only the first hit from CTS is used.
Therefore, using this function to translate on the fly is not foolproof
and care should be taken to verify the results.

## Examples

``` r
if (FALSE) { # \dontrun{
with_cts("XDDAORKBJWWYJS-UHFFFAOYSA-N", from = "inchikey", .f = "get_etoxid")
} # }
```
