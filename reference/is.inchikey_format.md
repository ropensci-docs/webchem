# Check if input is a valid inchikey using format

Inchikey must fulfill the following criteria: 1) consist of 27
characters; 2) be all uppercase, all letters (no numbers); 3) contain
two hyphens at positions 15 and 26; 4) 24th character (flag character)
be 'S' (Standard InChI) or 'N' (non-standard) 5) 25th character (version
character) must be 'A' (currently).

## Usage

``` r
is.inchikey_format(x, verbose = getOption("verbose"))
```

## Arguments

- x:

  character; input string

- verbose:

  logical; print messages during processing to console?

## Value

a logical

## See also

[`is.inchikey`](https://docs.ropensci.org/webchem/reference/is.inchikey.md)
for a pure-R implementation.

## Examples

``` r
if (FALSE) { # \dontrun{
# might fail if API is not available
is.inchikey_format('BQJCRHHNABKAKU-KBQPJGBKSA-N')
is.inchikey_format('BQJCRHHNABKAKU-KBQPJGBKSA')
is.inchikey_format('BQJCRHHNABKAKU-KBQPJGBKSA-5')
is.inchikey_format('BQJCRHHNABKAKU-KBQPJGBKSA-n')
is.inchikey_format('BQJCRHHNABKAKU/KBQPJGBKSA/N')
is.inchikey_format('BQJCRHHNABKAKU-KBQPJGBKXA-N')
is.inchikey_format('BQJCRHHNABKAKU-KBQPJGBKSB-N')
} # }
```
