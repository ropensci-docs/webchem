# Get record details from U.S. EPA Substance Registry Servives (SRS)

Get record details from SRS, see
<https://cdxnodengn.epa.gov/cdx-srs-rest/>

## Usage

``` r
srs_query(
  query,
  from = c("itn", "cas", "epaid", "tsn", "name"),
  verbose = getOption("verbose"),
  ...
)
```

## Arguments

- query:

  character; query ID.

- from:

  character; type of query ID, e.g. `'itn'` , `'cas'`, `'epaid'`,
  `'tsn'`, `'name'`.

- verbose:

  logical; should a verbose output be printed on the console?

- ...:

  not currently used.

## Value

a list of lists (for each supplied query): a list of 22. subsKey,
internalTrackingNumber, systematicName, epaIdentificationNumber,
currentCasNumber, currentTaxonomicSerialNumber, epaName, substanceType,
categoryClass, kingdomCode, iupacName, pubChemId, molecularWeight,
molecularFormula, inchiNotation, smilesNotation, classifications,
characteristics, synonyms, casNumbers, taxonomicSerialNumbers,
relationships

## Examples

``` r
if (FALSE) { # \dontrun{
# might fail if API is not available
srs_query(query = '50-00-0', from = 'cas')

### multiple inputs
casrn <- c('50-00-0', '67-64-1')
srs_query(query = casrn, from = 'cas')
} # }
```
