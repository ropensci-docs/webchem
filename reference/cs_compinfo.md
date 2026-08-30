# Retrieve record details by ChemSpider ID

Submit a ChemSpider ID (CSID) and the fields you are interested in, and
retrieve the record details for your query.

## Usage

``` r
cs_compinfo(csid, fields, verbose = getOption("verbose"), apikey = NULL)
```

## Arguments

- csid:

  numeric; can be obtained using
  [`get_csid`](https://docs.ropensci.org/webchem/reference/get_csid.md)

- fields:

  character; see details.

- verbose:

  logical; should a verbose output be printed on the console?

- apikey:

  character; your API key. If NULL (default),
  [`cs_check_key()`](https://docs.ropensci.org/webchem/reference/cs_check_key.md)
  will look for it in .Renviron or .Rprofile.

## Value

Returns a data frame.

## Details

Valid values for `fields` are `"SMILES"`, `"Formula"`, `"InChI"`,
`"InChIKey"`, `"StdInChI"`, `"StdInChIKey"`, `"AverageMass"`,
`"MolecularWeight"`, `"MonoisotopicMass"`, `"NominalMass"`,
`"CommonName"`, `"ReferenceCount"`, `"DataSourceCount"`,
`"PubMedCount"`, `"RSCCount"`, `"Mol2D"`, `"Mol3D"`. You can specify any
number of fields.

## Note

An API key is needed. Register at <https://developer.rsc.org/> for an
API key. Please respect the Terms & Conditions. The Terms & Conditions
can be found at <https://developer.rsc.org/terms>.

## References

<https://developer.rsc.org/docs/compounds-v1-trial/1/overview>

## Examples

``` r
if (FALSE) { # \dontrun{
cs_compinfo(171, c("SMILES", "CommonName"))
cs_compinfo(171:182, "SMILES")
} # }
```
