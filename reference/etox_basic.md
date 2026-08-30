# Get basic information from a ETOX ID

Query ETOX: Information System Ecotoxicology and Environmental Quality
Targets <https://webetox.uba.de/webETOX/index.do> for basic information

## Usage

``` r
etox_basic(id, verbose = getOption("verbose"))
```

## Arguments

- id:

  character; ETOX ID

- verbose:

  logical; print message during processing to console?

## Value

a list with lists of four entries: cas (the CAS numbers), ec (the EC
number), gsbl (the gsbl number), a data.frame synonys with synonyms and
the source url.

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
to retrieve ETOX IDs, `etox_basic` for basic information,
[`etox_targets`](https://docs.ropensci.org/webchem/reference/etox_targets.md)
for quality targets and
[`etox_tests`](https://docs.ropensci.org/webchem/reference/etox_tests.md)
for test results

## Examples

``` r
if (FALSE) { # \dontrun{
id <- get_etoxid('Triclosan', match = 'best')
etox_basic(id$etoxid)

# Retrieve data for multiple inputs
ids <- c("20179", "9051")
out <- etox_basic(ids)
out

# extract cas numbers
sapply(out, function(y) y$cas)
} # }
```
