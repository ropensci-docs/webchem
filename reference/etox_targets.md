# Get Quality Targets from a ETOX ID

Query ETOX: Information System Ecotoxicology and Environmental Quality
Targets <https://webetox.uba.de/webETOX/index.do> for quality targets

## Usage

``` r
etox_targets(id, verbose = getOption("verbose"))
```

## Arguments

- id:

  character; ETOX ID

- verbose:

  logical; print message during processing to console?

## Value

A list of lists of two: `res` a data.frame with quality targets from the
ETOX database, and source_url.

## Note

Before using this function, please read the disclaimer
<https://webetox.uba.de/webETOX/disclaimer.do>.

## References

Eduard Szöcs, Tamás Stirling, Eric R. Scott, Andreas Scharmüller, Ralf
B. Schäfer (2020). webchem: An R Package to Retrieve Chemical
Information from the Web. Journal of Statistical Software, 93(13).
[doi:10.18637/jss.v093.i13](https://doi.org/10.18637/jss.v093.i13) .

## See also

[`get_etoxid`](https://docs.ropensci.org/webchem/reference/get_etoxid.md)
to retrieve ETOX IDs,
[`etox_basic`](https://docs.ropensci.org/webchem/reference/etox_basic.md)
for basic information, `etox_targets` for quality targets and
[`etox_tests`](https://docs.ropensci.org/webchem/reference/etox_tests.md)
for test results

## Examples

``` r
if (FALSE) { # \dontrun{
id <- get_etoxid('Triclosan', match = 'best')
out <- etox_targets(id$etoxid)
out[ , c('Substance', 'CAS_NO', 'Country_or_Region', 'Designation',
'Value_Target_LR', 'Unit')]
etox_targets( c("20179", "9051"))

} # }
```
