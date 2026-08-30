# List available compound identifiers in the local FooDB database

List available compound identifiers in the local FooDB database

## Usage

``` r
foodb_list_compounds(
  idtype,
  include_synonyms = TRUE,
  verbose = getOption("verbose")
)
```

## Arguments

- idtype:

  character; the type of identifier to list. Allowed values are: "id",
  "public_id", "name", "cas_number", "moldb_smiles", "moldb_inchi",
  "moldb_inchikey", "moldb_iupac".

- include_synonyms:

  logical; should compound name synonyms also be included in the output?
  Only used if \`idtype\` is "name". Default is \`TRUE\`.

- verbose:

  logical; should verbose messages be printed to the console?

## Value

A character vector of unique identifiers of the specified type that are
present in the FooDB database.

## Examples

``` r
if (FALSE) { # \dontrun{
foodb_list_compounds("name")
foodb_list_compounds("cas_number")
} # }
```
