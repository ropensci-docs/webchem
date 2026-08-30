# Check if input is a valid inchikey using ChemSpider API

Check if input is a valid inchikey using ChemSpider API

## Usage

``` r
is.inchikey_cs(x, apikey = NULL, verbose = getOption("verbose"))
```

## Arguments

- x:

  character; input string

- apikey:

  character; your API key. If NULL (default),
  [`cs_check_key()`](https://docs.ropensci.org/webchem/reference/cs_check_key.md)
  will look for it in .Renviron or .Rprofile.

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
is.inchikey_cs('BQJCRHHNABKAKU-KBQPJGBKSA-N')
is.inchikey_cs('BQJCRHHNABKAKU-KBQPJGBKSA')
is.inchikey_cs('BQJCRHHNABKAKU-KBQPJGBKSA-5')
is.inchikey_cs('BQJCRHHNABKAKU-KBQPJGBKSA-n')
is.inchikey_cs('BQJCRHHNABKAKU/KBQPJGBKSA/N')
is.inchikey_cs('BQJCRHHNABKAKU-KBQPJGBKXA-N')
is.inchikey_cs('BQJCRHHNABKAKU-KBQPJGBKSB-N')
} # }
```
