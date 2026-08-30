# Get ETOX ID

Query ETOX: Information System Ecotoxicology and Environmental Quality
Targets <https://webetox.uba.de/webETOX/index.do> for their substance ID

## Usage

``` r
get_etoxid(
  query,
  from = c("name", "cas", "ec", "gsbl", "rtecs"),
  match = c("all", "best", "first", "ask", "na"),
  verbose = getOption("verbose")
)
```

## Arguments

- query:

  character; The searchterm

- from:

  character; Type of input, can be one of "name" (chemical name), "cas"
  (CAS Number), "ec" (European Community number for regulatory
  purposes), "gsbl" (Identifier used by
  <https://www.chemikalieninfo.de/>) and "rtecs" (Identifier used by the
  Registry of Toxic Effects of Chemical Substances database).

- match:

  character; How should multiple hits be handeled? "all" returns all
  matched IDs, "first" only the first match, "best" the best matching
  (by name) ID, "ask" is a interactive mode and the user is asked for
  input, "na" returns `NA` if multiple hits are found.

- verbose:

  logical; print message during processing to console?

## Value

a tibble with 3 columns: the query, the match, and the etoxID

## Note

Before using this function, please read the disclaimer
<https://webetox.uba.de/webETOX/disclaimer.do>.

## References

Eduard Szöcs, Tamás Stirling, Eric R. Scott, Andreas Scharmüller, Ralf
B. Schäfer (2020). webchem: An R Package to Retrieve Chemical
Information from the Web. Journal of Statistical Software, 93(13).
[doi:10.18637/jss.v093.i13](https://doi.org/10.18637/jss.v093.i13) .

## See also

[`etox_basic`](https://docs.ropensci.org/webchem/reference/etox_basic.md)
for basic information,
[`etox_targets`](https://docs.ropensci.org/webchem/reference/etox_targets.md)
for quality targets and
[`etox_tests`](https://docs.ropensci.org/webchem/reference/etox_tests.md)
for test results.

## Examples

``` r
if (FALSE) { # \dontrun{
# might fail if API is not available
get_etoxid("Triclosan")
# multiple inputs
comps <- c("Triclosan", "Glyphosate")
get_etoxid(comps)
get_etoxid(comps, match = "all")
get_etoxid("34123-59-6", from = "cas") # Isoproturon
get_etoxid("133483", from = "gsbl") # 3-Butin-1-ol
get_etoxid("203-157-5", from = "ec") # Paracetamol
} # }
```
