# Retrieve data from PubChem content pages

When you search for an entity at <https://pubchem.ncbi.nlm.nih.gov/>,
e.g. a compound or a substance, and select the record you are interested
in, you will be forwarded to a PubChem content page. When you look at a
PubChem content page, you can see that chemical information is organised
into sections, subsections, etc. The chemical data live at the lowest
levels of these sections. Use this function to retrieve the lowest level
information from PubChem content pages.

## Usage

``` r
pc_sect(
  id,
  section,
  domain = c("compound", "substance", "assay", "gene", "protein", "patent"),
  form = c("auto", "long", "wide"),
  verbose = getOption("verbose")
)
```

## Arguments

- id:

  numeric or character; a vector of PubChem identifiers to search for.

- section:

  character; the section of the content page to be imported.

- domain:

  character; the query domain. Can be one of `"compound"`,
  `"substance"`, `"assay"`, `"gene"`, `"protein"` or `"patent"`.

- form:

  character; the form of the output. Can be one of `"auto"`, `"long"` or
  `"wide"`.

- verbose:

  logical; should a verbose output be printed on the console?

## Value

Returns a tibble of query results. In the returned tibble, `SourceName`
is the name of the depositor, and `SourceID` is the ID of the search
term within the depositor's database. You can browse
<https://pubchem.ncbi.nlm.nih.gov/sources/> for more information about
the depositors.

## Details

`section` is not case sensitive but it is sensitive to typing errors and
it requires the full name of the section as it is printed on the content
page. The PubChem Table of Contents Tree can also be found at
<https://pubchem.ncbi.nlm.nih.gov/classification/#hid=72>.

## Note

Please respect the Terms and Conditions of the National Library of
Medicine, <https://www.nlm.nih.gov/databases/download.html> the data
usage policies of National Center for Biotechnology Information,
<https://www.ncbi.nlm.nih.gov/home/about/policies/>,
<https://pubchem.ncbi.nlm.nih.gov/docs/programmatic-access>, and the
data usage policies of the individual data sources
<https://pubchem.ncbi.nlm.nih.gov/sources/>.

## References

Kim, S., Thiessen, P.A., Cheng, T. et al. PUG-View: programmatic access
to chemical annotations integrated in PubChem. J Cheminform 11, 56
(2019).
[doi:10.1186/s13321-019-0375-2](https://doi.org/10.1186/s13321-019-0375-2)
.

## See also

[`get_cid`](https://docs.ropensci.org/webchem/reference/get_cid.md),
[`pc_prop`](https://docs.ropensci.org/webchem/reference/pc_prop.md)

## Examples

``` r
# might fail if API is not available
if (FALSE) { # \dontrun{
pc_sect(176, "Dissociation Constants")
pc_sect(c(176, 311), "density")
pc_sect(2231, "depositor-supplied synonyms", "substance")
pc_sect(780286, "modify date", "assay")
pc_sect(9023, "Ensembl ID", "gene")
pc_sect("1ZHY_A", "Sequence", "protein")
} # }
```
