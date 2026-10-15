# Retrieve Pubchem Compound ID (CID)

Retrieve compound IDs (CIDs) from PubChem.

## Usage

``` r
get_cid(
  query,
  from = "name",
  domain = c("compound", "substance", "assay"),
  match = c("all", "first", "ask", "na"),
  verbose = getOption("verbose"),
  arg = NULL,
  first = NULL,
  ...
)
```

## Arguments

- query:

  character; search term, one or more compounds.

- from:

  character; type of input. See details for more information.

- domain:

  character; query domain, can be one of `"compound"`, `"substance"`,
  `"assay"`.

- match:

  character; How should multiple hits be handled?, `"all"` all matches
  are returned, `"first"` the first matching is returned, `"ask"` enters
  an interactive mode and the user is asked for input, `"na"` returns NA
  if multiple hits are found.

- verbose:

  logical; should a verbose output be printed on the console?

- arg:

  character; optinal arguments like "name_type=word" to match individual
  words.

- first:

  deprecated. Use \`match\` instead.

- ...:

  currently unused.

## Value

a tibble.

## Details

Valid values for the `from` argument depend on the `domain`:

- `compound`: `"name"`, `"smiles"`, `"inchi"`, `"inchikey"`,
  `"formula"`, `"sdf"`, `"cas"` (an alias for `"xref/RN"`), \<xref\>,
  \<structure search\>, \<fast search\>.

- `substance`: `"name"`, `"sid"`, `<xref>`, `"sourceid/<source id>"` or
  `"sourceall"`.

- `assay`: `"aid"`, `<assay target>`.

\<structure search\> is assembled as "(`substructure` \|
`superstructure` \| `similarity` \| `identity`) / (`smiles` \| `inchi`
\| `sdf` \| `cid`)", e.g. `from = "substructure/smiles"`.

`<xref>` is assembled as "`xref`/(`RegistryID` \| `RN` \| `PubMedID` \|
`MMDBID` \| `ProteinGI`, `NucleotideGI` \| `TaxonomyID` \| `MIMID` \|
`GeneID` \| `ProbeID` \| `PatentID`)", e.g. `from = "xref/RN"` will
query by CAS RN.

\<fast search\> is either `fastformula` or it is assembled as
"(`fastidentity` \| `fastsimilarity_2d` \| `fastsimilarity_3d` \|
`fastsubstructure` \| `fastsuperstructure`)/(`smiles` \| `smarts` \|
`inchi` \| `sdf` \| `cid`)", e.g. `from = "fastidentity/smiles"`.

`<source id>` is any valid PubChem Data Source ID. When
`from = "sourceid/<source id>"`, the query is the ID of the substance in
the depositor's database.

If `from = "sourceall"` the query is one or more valid Pubchem depositor
names. Depositor names are not case sensitive.

Depositor names and Data Source IDs can be found at
<https://pubchem.ncbi.nlm.nih.gov/sources/>.

`<assay target>` is assembled as "`target`/(`gi` \| `proteinname` \|
`geneid` \| `genesymbol` \| `accession`)", e.g. `from = "target/geneid"`
will query by GeneID.

## Note

`from = "cas"` (equivalently `from = "xref/rn"`) relies on PubChem's
registry ID cross-reference, which is occasionally affected by upstream
data quality issues, i.e. a CAS RN can be incorrectly associated with
the wrong compound(s). If results look wrong, try `from = "name"`
instead: PubChem will then look up the CAS RN as a synonym, which often
(but not always, since not every CAS RN is registered as a synonym)
returns the expected compound.

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

## Examples

``` r
if (FALSE) { # \dontrun{
# might fail if API is not available
get_cid("Triclosan")
get_cid("Triclosan", arg = "name_type=word")
# from SMILES
get_cid("CCCC", from = "smiles")
# from InChI
get_cid("InChI=1S/CH5N/c1-2/h2H2,1H3", from = "inchi")
# from InChIKey
get_cid("BPGDAMSIGCZZLK-UHFFFAOYSA-N", from = "inchikey")
# from formula
get_cid("C26H52NO6P", from = "formula")
# from CAS RN
get_cid("56-40-6", from = "xref/rn")
# similarity
get_cid(5564, from = "similarity/cid")
get_cid("CCO", from = "similarity/smiles")
# from SID
get_cid("126534046", from = "sid", domain = "substance")
# sourceid
get_cid("VCC957895", from = "sourceid/23706", domain = "substance")
# sourceall
get_cid("Optopharma Ltd", from = "sourceall", domain = "substance")
# from AID (CIDs of substances tested in the assay)
get_cid(170004, from = "aid", domain = "assay")
# from GeneID (CIDs of substances tested on the gene)
get_cid(25086, from = "target/geneid", domain = "assay")

# multiple inputs
get_cid(c("Triclosan", "Aspirin"))

} # }
```
