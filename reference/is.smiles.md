# Check if input is a SMILES string

This function checks if a string is a valid SMILES by checking if (R)CDK
can parse it. If it cannot be parsed by rcdk FALSE is returned, else
TRUE.

## Usage

``` r
is.smiles(x, verbose = getOption("verbose"))
```

## Arguments

- x:

  character; input SMILES.

- verbose:

  logical; print messages during processing to console?

## Value

a logical

## Note

This function can handle only one SMILES string.

## References

Egon Willighagen (2015). How to test SMILES strings in Supplementary
Information.
<https://chem-bla-ics.blogspot.nl/2015/10/how-to-test-smiles-strings-in.html>

## Examples

``` r
if (FALSE) { # \dontrun{
# might fail if rcdk is not working properly
is.smiles('Clc(c(Cl)c(Cl)c1C(=O)O)c(Cl)c1Cl')
is.smiles('Clc(c(Cl)c(Cl)c1C(=O)O)c(Cl)c1ClJ')
} # }
```
