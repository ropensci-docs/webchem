# Retrieve identifiers from Wikidata

Retrieve identifiers from Wikidata

## Usage

``` r
wd_ident(id, verbose = getOption("verbose"))
```

## Arguments

- id:

  character; identifier, as returned by
  [`get_wdid`](https://docs.ropensci.org/webchem/reference/get_wdid.md)

- verbose:

  logical; print message during processing to console?

## Value

A data.frame of identifiers. Currently these are 'smiles', 'cas', 'cid',
'einecs', 'csid', 'inchi', 'inchikey', 'drugbank', 'zvg', 'chebi',
'chembl', 'unii', 'lipidmaps', 'swisslipids' and source_url.

## Note

Only matches in labels are returned. If more than one unique hit is
found, only the first is returned.

## References

Willighagen, E., 2015. Getting CAS registry numbers out of WikiData. The
Winnower.
[doi:10.15200/winn.142867.72538](https://doi.org/10.15200/winn.142867.72538)

Mitraka, Elvira, Andra Waagmeester, Sebastian Burgstaller-Muehlbacher,
et al. 2015 Wikidata: A Platform for Data Integration and Dissemination
for the Life Sciences and beyond. bioRxiv: 031971.

## See also

[`get_wdid`](https://docs.ropensci.org/webchem/reference/get_wdid.md)

## Examples

``` r
if (FALSE) { # \dontrun{
 id <- c("Q408646", "Q18216")
 wd_ident(id)
} # }
```
