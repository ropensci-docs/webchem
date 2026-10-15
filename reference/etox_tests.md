# Get Tests from a ETOX ID

Query ETOX: Information System Ecotoxicology and Environmental Quality
Targets <https://recherche.chemikalieninfo.de/etox> for tests

## Usage

``` r
etox_tests(id, verbose = getOption("verbose"))
```

## Arguments

- id:

  character; ETOX ID

- verbose:

  logical; print message during processing to console?

## Value

A list of lists of two: A data.frame with test results from the ETOX
database and the source_url.

## Note

Terms and Conditions: https://www.chemikalieninfo.de/termsofuse.html

## See also

[`get_etoxid`](https://docs.ropensci.org/webchem/reference/get_etoxid.md)
to retrieve ETOX IDs,
[`etox_basic`](https://docs.ropensci.org/webchem/reference/etox_basic.md)
for basic information,
[`etox_targets`](https://docs.ropensci.org/webchem/reference/etox_targets.md)
for quality targets and `etox_tests` for test results

## Examples

``` r
if (FALSE) { # \dontrun{
id <- get_etoxid('Triclosan', match = 'best')
out <- etox_tests(id$etoxid)
out[ , c('Organism', 'Effect', 'Duration', 'Time_Unit',
'Endpoint', 'Value', 'Unit')]
etox_tests( c("20179", "9051"))
} # }
```
