# Convert compound identifiers in the local FooDB database

Convert compound identifiers in the local FooDB database

## Usage

``` r
foodb_convert(query, from, to, verbose = getOption("verbose"))
```

## Arguments

- query:

  character; a character of compound identifiers to convert.

- from:

  The type of identifier provided in `query`. See Details for allowed
  values.

- to:

  The type of identifier to convert to. See Details for allowed values.

- verbose:

  logical; should verbose messages be printed to the console?

## Value

A data frame of converted identifiers, in the same order as the input
`query`. If an identifier could not be converted, the corresponding
output will be `NA`. If multiple matches are found for a query, all
matches will be returned in separate rows.

## Details

Allowed values for `from` and `to` are:

- `id`: internal numeric ID in the FooDB database

- `public_id`: public numeric ID in the FooDB database

- `name`: compound name

- `cas_number`: CAS number

- `moldb_smiles`: SMILES string

- `moldb_inchi`: InChI string

- `moldb_inchikey`: InChIKey string

- `moldb_iupac`: IUPAC name

## Examples

``` r
if (FALSE) { # \dontrun{
foodb_convert("4", from = "id", to = "name")
foodb_convert("FDB000004", from = "public_id", to = "cas_number")
} # }
```
