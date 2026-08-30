# Check if input is a valid CAS

This function checks if a string is a valid CAS registry number. A valid
CAS is 1) separated by two hyphes into three parts; 2) the first part
consists from two up to seven digits; 3) the second of two digits; 4)
the third of one digit (check digit); 5) the check digits corresponds
the checksum. The checksum is found by taking the last digit (excluding
the check digit) multiplyingit with 1, the second last multiplied with
2, the third-last multiplied with 3 etc. The modulo 10 of the sum of
these is the checksum.

## Usage

``` r
is.cas(x, verbose = getOption("verbose"))
```

## Arguments

- x:

  character; input CAS

- verbose:

  logical; print messages during processing to console?

## Value

a logical

## Note

This function can only handle one CAS string

## References

Eduard Szöcs, Tamás Stirling, Eric R. Scott, Andreas Scharmüller, Ralf
B. Schäfer (2020). webchem: An R Package to Retrieve Chemical
Information from the Web. Journal of Statistical Software, 93(13).
[doi:10.18637/jss.v093.i13](https://doi.org/10.18637/jss.v093.i13) .

## Examples

``` r
is.cas('64-17-5')
#> 64-17-5 
#>    TRUE 
is.cas('64175')
#> 64175 
#> FALSE 
is.cas('4-17-5')
#> 4-17-5 
#>  FALSE 
is.cas('64-177-6')
#> 64-177-6 
#>    FALSE 
is.cas('64-17-55')
#> 64-17-55 
#>    FALSE 
is.cas('64-17-6')
#> 64-17-6 
#>   FALSE 
```
