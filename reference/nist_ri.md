# Retrieve retention indices from NIST

This function scrapes NIST for literature retention indices given a
query or vector of queries as input. The query can be a cas number,
IUPAC name, or International Chemical Identifier (`inchikey`), according
to the value of the `from` argument. Retention indices are stored in
tables by `type`, `polarity` and temperature program (`temp_prog`). The
function can take multiple arguments for these parameters and will
return any retention times matching the specified criteria in a single
table.

If a non-cas query is provided, the function will try to resolve the
query by searching the NIST WebBook for a corresponding CAS number. If
`from == "name"`, phonetic spellings of Greek stereo-descriptors (e.g.
"alpha", "beta", "gamma") will be automatically converted to the
corresponding letters to match the form used by NIST. If a CAS number is
found, it will be returned in a `tibble` with the corresponding
information from the NIST retention index database.

## Usage

``` r
nist_ri(
  query,
  from = c("cas", "inchi", "inchikey", "name"),
  type = c("kovats", "linear", "alkane", "lee"),
  polarity = c("polar", "non-polar"),
  temp_prog = c("isothermal", "ramp", "custom"),
  cas = NULL,
  verbose = getOption("verbose")
)
```

## Arguments

- query:

  character; the search term

- from:

  character; type of search term. can be one of `"name"`, `"inchi"`,
  `"inchikey"`, or `"cas"`. Using an identifier is preferred to `"name"`
  since `NA` is returned in the event of multiple matches to a query.
  Using an identifier other than a CAS number will cause this function
  to run slower as CAS numbers are used as internal identifiers by NIST.

- type:

  Retention index type: `"kovats"`, `"linear"`, `"alkane"`, and/or
  `"lee"`. See details for more.

- polarity:

  Column polarity: `"polar"` and/or `"non-polar"` to get RIs calculated
  for polar or non-polar columns.

- temp_prog:

  Temperature program: `"isothermal"`, `"ramp"`, and/or `"custom"`.

- cas:

  deprecated. Use `query` instead.

- verbose:

  logical; should a verbose output be printed on the console?

## Value

returns a tibble of literature RIs with the following columns:

- `query` is the query provided to the NIST server

- `cas` is the CAS number or unique record identified used by NIST

- `RI` is retention index

- `type` is the type of RI (e.g. "kovats", "linear", "alkane", or "lee")

- `polarity` is the polarity of the column (either "polar" or
  "non-polar")

- `temp_prog` is the type of temperature program (e.g. "isothermal",
  "ramp", or "custom")

- `column` is the column type, e.g. "capillary"

- `phase` is the stationary phase (column phase)

- `length` is column length in meters

- `gas` is the carrier gas used

- `substrate`

- `diameter` is the column diameter in mm

- `thickness` is the phase thickness in µm

- `program`. various columns depending on the value of `temp_prog`

- `reference` is where this retention index was published

- `comment`. I believe this denotes the database these data were
  aggregated from

## Details

The types of retention indices included in NIST include Kovats
(`"kovats"`), Van den Dool and Kratz (`"linear"`), normal alkane
(`"alkane"`), and Lee (`"lee"`). Details about how these are calculated
are available on the NIST website:
<https://webbook.nist.gov/chemistry/gc-ri/>

## Note

Copyright for NIST Standard Reference Data is governed by the Standard
Reference Data Act, <https://www.nist.gov/srd/public-law>.

## References

NIST Mass Spectrometry Data Center, William E. Wallace, director,
"Retention Indices" in NIST Chemistry WebBook, NIST Standard Reference
Database Number 69, Eds. P.J. Linstrom and W.G. Mallard, National
Institute of Standards and Technology, Gaithersburg MD, 20899,
[doi:10.18434/T4D303](https://doi.org/10.18434/T4D303) .

## See also

[`is.cas`](https://docs.ropensci.org/webchem/reference/is.cas.md)
[`as.cas`](https://docs.ropensci.org/webchem/reference/as.cas.md)

## Examples

``` r
if (FALSE) { # \dontrun{
myRIs <-
  nist_ri(
    c("78-70-6", "13474-59-4"),
    from = "cas",
    type = c("linear", "kovats"),
    polarity = "non-polar",
    temp_prog = "ramp"
  )
myRIs} # }
```
