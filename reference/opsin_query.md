# OPSIN web interface

Query the OPSIN (Open Parser for Systematic IUPAC nomenclature) web
service <https://www.ebi.ac.uk/opsin>.

## Usage

``` r
opsin_query(query, verbose = getOption("verbose"), ...)
```

## Arguments

- query:

  character; chemical name that should be queryed.

- verbose:

  logical; should a verbose output be printed on the console?

- ...:

  currently not used.

## Value

a tibble with six columnns: "query", inchi", "stdinchi", "stdinchikey",
"smiles", "message", and "status"

## References

Lowe, D. M., Corbett, P. T., Murray-Rust, P., & Glen, R. C. (2011).
Chemical Name to Structure: OPSIN, an Open Source Solution. Journal of
Chemical Information and Modeling, 51(3), 739–753.
[doi:10.1021/ci100384d](https://doi.org/10.1021/ci100384d)

## Examples

``` r
if (FALSE) { # \dontrun{
opsin_query('Cyclopropane')
opsin_query(c('Cyclopropane', 'Octane'))
opsin_query(c('Cyclopropane', 'Octane', 'xxxxx'))
} # }
```
