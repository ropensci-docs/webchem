# List available entries in the local EU Pesticides database

List available entries in the local EU Pesticides database

## Usage

``` r
eup_list_entries(idtype, verbose = getOption("verbose"))
```

## Arguments

- idtype:

  character; the type of identifier to list. Allowed values are:
  "substance_id", "substance_name", "as_cas_number",
  "pesticide_residue_id", "pesticide_residue_name".

- verbose:

  logical; should verbose messages be printed to the console?

## Value

A character vector of unique identifiers of the specified type that are
present in the EU Pesticides database.

## References

You can find more information about the EU Pesticides database at
<https://food.ec.europa.eu/plants/pesticides/eu-pesticides-database_en>.

## Examples

``` r
if (FALSE) { # \dontrun{
eup_list_entries("substance_name")
eup_list_entries("pesticide_residue_name")
} # }
```
