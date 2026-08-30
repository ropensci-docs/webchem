# Ping an API used in webchem to see if it's working.

Ping an API used in webchem to see if it's working.

## Usage

``` r
ping_service(
  service = c("bcpc", "chebi", "chembl", "cs", "cs_web", "cir", "cts", "etox", "fn",
    "nist", "opsin", "pc", "srs", "wd"),
  apikey = NULL
)
```

## Arguments

- service:

  character; the same abbreviations used as prefixes in `webchem`
  functions, with the exception of `"cs_web"`, which only checks if the
  ChemSpider website is up, and thus doesn't require an API key.

- apikey:

  character; API key for services that require API keys

## Value

A logical, TRUE if the service is available or FALSE if it isn't

## Examples

``` r
if (FALSE) { # \dontrun{
ping_service("chembl")
} # }
```
