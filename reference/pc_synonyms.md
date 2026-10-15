# Search synonyms in pubchem

Search synonyms using PUG-REST, see <https://pubchem.ncbi.nlm.nih.gov/>.

## Usage

``` r
pc_synonyms(
  query,
  from = c("name", "cid", "sid", "aid", "smiles", "inchi", "inchikey"),
  match = c("all", "first", "ask", "na"),
  verbose = getOption("verbose"),
  arg = NULL,
  choices = NULL,
  ...
)
```

## Arguments

- query:

  character; search term.

- from:

  character; type of input, can be one of "name" (default), "cid",
  "sid", "aid", "smiles", "inchi", "inchikey"

- match:

  character; How should multiple hits be handled? `"all"` returns all
  matches, `"first"` returns only the first result, `"ask"` enters an
  interactive mode and the user is asked for input, `"na"` returns `NA`
  if multiple hits are found.

- verbose:

  logical; should a verbose output be printed on the console?

- arg:

  character; optional arguments like "name_type=word" to match
  individual words.

- choices:

  deprecated. Use the `match` argument instead.

- ...:

  currently unused

## Value

a named list.

## Note

Please respect the Terms and Conditions of the National Library of
Medicine, <https://www.nlm.nih.gov/databases/download.html> the data
usage policies of National Center for Biotechnology Information,
<https://www.ncbi.nlm.nih.gov/home/about/policies/>,
<https://pubchem.ncbi.nlm.nih.gov/docs/programmatic-access>, and the
data usage policies of the indicidual data sources
<https://pubchem.ncbi.nlm.nih.gov/sources/>.

## References

Wang, Y., J. Xiao, T. O. Suzek, et al. 2009 PubChem: A Public
Information System for Analyzing Bioactivities of Small Molecules.
Nucleic Acids Research 37: 623–633.

Kim, Sunghwan, Paul A. Thiessen, Evan E. Bolton, et al. 2016 PubChem
Substance and Compound Databases. Nucleic Acids Research 44(D1):
D1202–D1213.

Kim, S., Thiessen, P. A., Bolton, E. E., & Bryant, S. H. (2015).
PUG-SOAP and PUG-REST: web services for programmatic access to chemical
information in PubChem. Nucleic acids research, gkv396.

## Examples

``` r
if (FALSE) { # \dontrun{
pc_synonyms("Aspirin")
pc_synonyms(c("Aspirin", "Triclosan"))
pc_synonyms(5564, from = "cid")
pc_synonyms(c("Aspirin", "Triclosan"), match = "ask")
} # }
```
