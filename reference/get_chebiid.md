# Retrieve Lite Entity (identifiers) from ChEBI

Returns a data.frame with a ChEBI entity ID (chebiid), a ChEBI entity
name (chebiasciiname), a search score (searchscore) and stars (stars)
using the SOAP protocol: <https://www.ebi.ac.uk/chebi/webServices.do>

## Usage

``` r
get_chebiid(
  query,
  from = c("all", "chebi id", "chebi name", "definition", "name", "iupac name",
    "citations", "registry numbers", "manual xrefs", "automatic xrefs", "formula",
    "mass", "monoisotopic mass", "charge", "inchi", "inchikey", "smiles", "species"),
  match = c("all", "best", "first", "ask", "na"),
  max_res = 200,
  stars = c("all", "two only", "three only"),
  verbose = getOption("verbose"),
  ...
)
```

## Arguments

- query:

  character; search term.

- from:

  character; type of input. `"all"` searches all types and `"name"`
  searches all names. Other options include `'chebi id'`,
  `'chebi name'`, `'definition'`, `'iupac name'`, `'citations'`,
  `'registry numbers'`, `'manual xrefs'`, `'automatic xrefs'`,
  `'formula'`, `'mass'`, `'monoisotopic mass'`,`'charge'`, `'inchi'`,
  `'inchikey'`, `'smiles'`, and `'species'`

- match:

  character; How should multiple hits be handled?, `"all"` all matches
  are returned, `"best"` the best matching (by the ChEBI searchscore) is
  returned, `"ask"` enters an interactive mode and the user is asked for
  input, `"na"` returns NA if multiple hits are found.

- max_res:

  integer; maximum number of results to be retrieved from the web
  service

- stars:

  character; "three only" restricts results to those manualy annotated
  by the ChEBI team.

- verbose:

  logical; should a verbose output be printed on the console?

- ...:

  currently unused

## Value

returns a list of data.frames containing a chebiid, a chebiasciiname, a
searchscore and stars if matches were found. If not, data.frame(NA) is
returned

## References

Hastings J, Owen G, Dekker A, Ennis M, Kale N, Muthukrishnan V, Turner
S, Swainston N, Mendes P, Steinbeck C. (2016). ChEBI in 2016: Improved
services and an expanding collection of metabfolites. Nucleic Acids Res.

Hastings, J., de Matos, P., Dekker, A., Ennis, M., Harsha, B., Kale, N.,
Muthukrishnan, V., Owen, G., Turner, S., Williams, M., and Steinbeck, C.
(2013) The ChEBI reference database and ontology for biologically
relevant chemistry: enhancements for 2013. Nucleic Acids Res.

de Matos, P., Alcantara, R., Dekker, A., Ennis, M., Hastings, J., Haug,
K., Spiteri, I., Turner, S., and Steinbeck, C. (2010) Chemical entities
of biological interest: an update. Nucleic Acids Res. Degtyarenko, K.,
Hastings, J., de Matos, P., and Ennis, M. (2009). ChEBI: an open
bioinformatics and cheminformatics resource. Current protocols in
bioinformatics / editoral board, Andreas D. Baxevanis et al., Chapter
14.

Degtyarenko, K., de Matos, P., Ennis, M., Hastings, J., Zbinden, M.,
McNaught, A., Alcántara, R., Darsow, M., Guedj, M. and Ashburner, M.
(2008) ChEBI: a database and ontology for chemical entities of
biological interest. Nucleic Acids Res. 36, D344–D350.

Eduard Szöcs, Tamás Stirling, Eric R. Scott, Andreas Scharmüller, Ralf
B. Schäfer (2020). webchem: An R Package to Retrieve Chemical
Information from the Web. Journal of Statistical Software, 93(13).
[doi:10.18637/jss.v093.i13](https://doi.org/10.18637/jss.v093.i13) .

## Examples

``` r
if (FALSE) { # \dontrun{
# might fail if API is not available
get_chebiid('Glyphosate')
get_chebiid('BPGDAMSIGCZZLK-UHFFFAOYSA-N')

# multiple inputs
comp <- c('Iron', 'Aspirin', 'BPGDAMSIGCZZLK-UHFFFAOYSA-N')
get_chebiid(comp)

} # }
```
