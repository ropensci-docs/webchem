# Retrieve ChemSpider data sources

The function returns a vector of available data sources used by
ChemSpider. Some ChemSpider functions allow you to restrict which
sources are used to lookup the requested query. Restricting the sources
makes these queries faster.

## Usage

``` r
cs_datasources(apikey = NULL, verbose = getOption("verbose"))
```

## Arguments

- apikey:

  character; your API key. If NULL (default),
  [`cs_check_key()`](https://docs.ropensci.org/webchem/reference/cs_check_key.md)
  will look for it in .Renviron or .Rprofile.

- verbose:

  should a verbose output be printed on the console?

## Value

Returns a character vector.

## Note

An API key is needed. Register at <https://developer.rsc.org/> for an
API key. Please respect the Terms & Conditions. The Terms & Conditions
can be found at <https://developer.rsc.org/terms>.

## References

<https://developer.rsc.org/docs/compounds-v1-trial/1/overview>

## Examples

``` r
if (FALSE) { # \dontrun{
cs_datasources()
} # }
```
