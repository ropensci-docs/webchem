# Check if input is a valid inchikey

This function checks if a string is a valid inchikey. Inchikey must
fulfill the following criteria: 1) consist of 27 characters; 2) be all
uppercase, all letters (no numbers); 3) contain two hyphens at positions
15 and 26; 4) 24th character (flag character) be 'S' (Standard InChI) or
'N' (non-standard) 5) 25th character (version character) must be 'A'
(currently).

## Usage

``` r
is.inchikey(
  x,
  type = c("format", "chemspider"),
  apikey = NULL,
  verbose = getOption("verbose")
)
```

## Arguments

- x:

  character; input InChIKey

- type:

  character; How should be checked? Either, by format (see above)
  ('format') or by ChemSpider ('chemspider').

- apikey:

  character; your API key. If NULL (default),
  [`cs_check_key()`](https://docs.ropensci.org/webchem/reference/cs_check_key.md)
  will look for it in .Renviron or .Rprofile. Only used when \`type =
  "chemspider"\`.

- verbose:

  logical; print messages during processing to console?

## Value

a logical

## Note

This function can handle only one inchikey string.

## References

Heller, Stephen R., et al. "InChI, the IUPAC International Chemical
Identifier." Journal of Cheminformatics 7.1 (2015): 23.

Eduard Szöcs, Tamás Stirling, Eric R. Scott, Andreas Scharmüller, Ralf
B. Schäfer (2020). webchem: An R Package to Retrieve Chemical
Information from the Web. Journal of Statistical Software, 93(13).
[doi:10.18637/jss.v093.i13](https://doi.org/10.18637/jss.v093.i13) .

## Examples

``` r
is.inchikey('BQJCRHHNABKAKU-KBQPJGBKSA-N')
#> [1] TRUE
is.inchikey('BQJCRHHNABKAKU-KBQPJGBKSA')
#> [1] FALSE
is.inchikey('BQJCRHHNABKAKU-KBQPJGBKSA-5')
#> [1] FALSE
is.inchikey('BQJCRHHNABKAKU-KBQPJGBKSA-n')
#> [1] FALSE
is.inchikey('BQJCRHHNABKAKU/KBQPJGBKSA/N')
#> [1] FALSE
is.inchikey('BQJCRHHNABKAKU-KBQPJGBKXA-N')
#> [1] FALSE
is.inchikey('BQJCRHHNABKAKU-KBQPJGBKSB-N')
#> [1] FALSE
```
