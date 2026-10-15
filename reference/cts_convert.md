# Convert Ids using Chemical Translation Service (CTS)

Convert Ids using Chemical Translation Service (CTS), see
<http://cts.fiehnlab.ucdavis.edu/>

## Usage

``` r
cts_convert(
  query,
  from,
  to,
  match = c("all", "first", "ask", "na"),
  verbose = getOption("verbose"),
  choices = NULL,
  ...
)
```

## Arguments

- query:

  character; query ID.

- from:

  character; type of query ID, e.g. `'Chemical Name'` , `'InChIKey'`,
  `'PubChem CID'`, `'ChemSpider'`, `'CAS'`.

- to:

  character; type to convert to.

- match:

  character; How should multiple hits be handled? `"all"` returns all
  matches, `"first"` returns only the first result, `"ask"` enters an
  interactive mode and the user is asked for input, `"na"` returns `NA`
  if multiple hits are found.

- verbose:

  logical; should a verbose output be printed on the console?

- choices:

  deprecated. Use the `match` argument instead.

- ...:

  currently not used.

## Value

a list of character vectors or if `choices` is used, then a single named
vector.

## Details

See also <http://cts.fiehnlab.ucdavis.edu/> for possible values of from
and to.

## References

Wohlgemuth, G., P. K. Haldiya, E. Willighagen, T. Kind, and O. Fiehn
2010The Chemical Translation Service – a Web-Based Tool to Improve
Standardization of Metabolomic Reports. Bioinformatics 26(20):
2647–2648.

## See also

[`cts_from`](https://docs.ropensci.org/webchem/reference/cts_from.md)
for possible values in the 'from' argument and
[`cts_to`](https://docs.ropensci.org/webchem/reference/cts_to.md) for
possible values in the 'to' argument.

## Examples

``` r
if (FALSE) { # \dontrun{
# might fail if API is not available
cts_convert("XEFQLINVKFYRCS-UHFFFAOYSA-N", "inchikey", "Chemical Name")

### multiple inputs
keys <- c("XEFQLINVKFYRCS-UHFFFAOYSA-N", "VLKZOEOYAKHREP-UHFFFAOYSA-N")
cts_convert(keys, "inchikey", "cas")
} # }
```
