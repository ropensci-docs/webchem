# ChemSpider ID from compound name, formula, SMILES, InChI or InChIKey

Query one or more compunds by name, formula, SMILES, InChI or InChIKey
and return a vector of ChemSpider IDs.

## Usage

``` r
get_csid(
  query,
  from = c("name", "formula", "inchi", "inchikey", "smiles"),
  match = c("all", "first", "ask", "na"),
  verbose = getOption("verbose"),
  apikey = NULL,
  ...
)
```

## Arguments

- query:

  character; search term.

- from:

  character; the type of the identifier to convert from. Valid values
  are `"name"`, `"formula"`, `"smiles"`, `"inchi"`, `"inchikey"`. The
  default value is `"name"`.

- match:

  character; How should multiple hits be handled?, "all" all matches are
  returned, "best" the best matching is returned, "ask" enters an
  interactive mode and the user is asked for input, "na" returns NA if
  multiple hits are found.

- verbose:

  logical; should a verbose output be printed on the console?

- apikey:

  character; your API key. If NULL (default),
  [`cs_check_key()`](https://docs.ropensci.org/webchem/reference/cs_check_key.md)
  will look for it in .Renviron or .Rprofile.

- ...:

  furthrer arguments passed to
  [`cs_control`](https://docs.ropensci.org/webchem/reference/cs_control.md)

## Value

Returns a tibble.

## Details

Queries by SMILES, InChI or InChiKey do not use `cs_control` options.
Queries by name use `order_by` and `order_direction`. Queries by formula
also use `datasources`. See
[`cs_control()`](https://docs.ropensci.org/webchem/reference/cs_control.md)
for a full list of valid values for these control options.

`formula` can be expressed with and without LaTeX syntax.

## Note

An API key is needed. Register at <https://developer.rsc.org/> for an
API key. Please respect the Terms & conditions:
<https://developer.rsc.org/terms>.

## References

<https://developer.rsc.org/docs/compounds-v1-trial/1/overview>

Eduard Szöcs, Tamás Stirling, Eric R. Scott, Andreas Scharmüller, Ralf
B. Schäfer (2020). webchem: An R Package to Retrieve Chemical
Information from the Web. Journal of Statistical Software, 93(13).
[doi:10.18637/jss.v093.i13](https://doi.org/10.18637/jss.v093.i13) .

## Examples

``` r
if (FALSE) { # \dontrun{
get_csid("triclosan")
get_csid(c("carbamazepine", "naproxene","oxygen"))
get_csid("C2H6O", from = "formula")
get_csid("C_{2}H_{6}O", from = "formula")
get_csid("CC(O)=O", from = "smiles")
get_csid("InChI=1S/C2H4O2/c1-2(3)4/h1H3,(H,3,4)", from = "inchi")
get_csid("QTBSBXVTEAMEQO-UHFFFAOYAR", from = "inchikey")
} # }
```
