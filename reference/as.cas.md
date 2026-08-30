# Format numbers as CAS numbers

This function attempts to format numeric (or character) vectors as
character vectors of CAS numbers. If they cannot be converted to CAS
format or don't pass
[`is.cas`](https://docs.ropensci.org/webchem/reference/is.cas.md), `NA`
is returned

## Usage

``` r
as.cas(x, verbose = getOption("verbose"))
```

## Arguments

- x:

  numeric vector, or character vector of CAS numbers missing the hyphens

- verbose:

  logical; should a verbose output be printed on the console?

## Value

character vector of valid CAS numbers

## See also

[`is.cas`](https://docs.ropensci.org/webchem/reference/is.cas.md)

## Examples

``` r
x = c(58082, 123456, "hexenol")
as.cas(x)
#>     58082    123456   hexenol 
#> "58-08-2"        NA        NA 
```
