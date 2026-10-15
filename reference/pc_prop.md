# Retrieve compound properties from a pubchem CID

Retrieve compound information from pubchem CID, see
<https://pubchem.ncbi.nlm.nih.gov/>

## Usage

``` r
pc_prop(cid, properties = NULL, verbose = getOption("verbose"), ...)
```

## Arguments

- cid:

  numeric; a vector of Pubchem IDs (CIDs). The input vector will be
  coerced to a vector of positive integers. The function will return a
  row of NAs for elements that cannot be coerced to positive integers.

- properties:

  character; a vector of properties to retrieve, e.g.
  c("MolecularFormula", "MolecularWeight"). If NULL (default) all
  available properties are retrieved. See
  <https://pubchem.ncbi.nlm.nih.gov/docs/pug-rest#section=Compound-Property-Tables>
  for a list of all available properties.

- verbose:

  logical; should a verbose output be printed to the console?

- ...:

  currently not used.

## Value

a tibble; each row is a queried CID, each column is a requested
property.

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

Eduard Szöcs, Tamás Stirling, Eric R. Scott, Andreas Scharmüller, Ralf
B. Schäfer (2020). webchem: An R Package to Retrieve Chemical
Information from the Web. Journal of Statistical Software, 93(13).
[doi:10.18637/jss.v093.i13](https://doi.org/10.18637/jss.v093.i13) .

## See also

[`get_cid`](https://docs.ropensci.org/webchem/reference/get_cid.md),
[`pc_sect`](https://docs.ropensci.org/webchem/reference/pc_sect.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# might fail if API is not available
pc_prop(5564)

###
# multiple CIDS
comp <- c("Triclosan", "Aspirin")
cids <- get_cid(comp)
pc_prop(cids$cid, properties = c("MolecularFormula", "MolecularWeight",
"SMILES"))
} # }
```
