# Get extended record details by ChemSpider ID

Get extended info from ChemSpider, see <https://www.chemspider.com/>

## Usage

``` r
cs_extcompinfo(csid, token, verbose = getOption("verbose"), ...)
```

## Arguments

- csid:

  character, ChemSpider ID.

- token:

  character; security token.

- verbose:

  logical; should a verbose output be printed on the console?

- ...:

  currently not used.

## Value

a data.frame with entries: 'csid', 'mf' (molecular formula), 'smiles',
'inchi' (non-standard), 'inchikey' (non-standard), 'average_mass', 'mw'
(Molecular weight), 'monoiso_mass' (MonoisotopicMass), nominal_mass',
'alogp', 'xlogp', 'common_name' and 'source_url'

## Note

An API key is needed. Register at <https://developer.rsc.org/> for an
API key. for a security token.

Terms and Conditions: <https://developer.rsc.org/terms>

use
[`cs_compinfo`](https://docs.ropensci.org/webchem/reference/cs_compinfo.md)
to retrieve standard inchikey.

## See also

[`get_csid`](https://docs.ropensci.org/webchem/reference/get_csid.md) to
retrieve ChemSpider IDs,
[`cs_compinfo`](https://docs.ropensci.org/webchem/reference/cs_compinfo.md)
for extended compound information.

## Examples

``` r
if (FALSE) { # \dontrun{
token <- "<redacted>"
csid <- get_csid("Triclosan")
cs_extcompinfo(csid, token)

csids <- get_csid(c('Aspirin', 'Triclosan'))
cs_compinfo(csids)
} # }
```
