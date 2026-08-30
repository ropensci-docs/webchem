# Convert identifiers using ChemSpider

Submit one or more identifiers (CSID, SMILES, InChI, InChIKey or Mol)
and return one or more identifiers in another format (CSID, SMILES,
InChI, InChIKey or Mol).

## Usage

``` r
cs_convert(query, from, to, verbose = getOption("verbose"), apikey = NULL)
```

## Arguments

- query:

  character; query ID.

- from:

  character; type of query ID.

- to:

  character; type to convert to.

- verbose:

  logical; should a verbose output be printed on the console?

- apikey:

  character; your API key. If NULL (default),
  [`cs_check_key()`](https://docs.ropensci.org/webchem/reference/cs_check_key.md)
  will look for it in .Renviron or .Rprofile.

## Value

Returns a vector containing the converted identifier(s).

## Details

Not all conversions are supported. Allowed conversions:

- CSID \<-\> InChI

- CSID \<-\> InChIKey

- CSID \<-\> SMILES

- CSID -\> Mol file

- InChI \<-\> InChIKey

- InChI \<-\> SMILES

- InChI -\> Mol file

- InChIKey \<-\> Mol file

## Note

An API key is needed. Register at <https://developer.rsc.org/> for an
API key. Please respect the Terms & Conditions. The Terms & Conditions
can be found at <https://developer.rsc.org/terms>.

## References

<https://developer.rsc.org/docs/compounds-v1-trial/1/overview>

Eduard Szöcs, Tamás Stirling, Eric R. Scott, Andreas Scharmüller, Ralf
B. Schäfer (2020). webchem: An R Package to Retrieve Chemical
Information from the Web. Journal of Statistical Software, 93(13).
[doi:10.18637/jss.v093.i13](https://doi.org/10.18637/jss.v093.i13) .

## Examples

``` r
if (FALSE) { # \dontrun{
cs_convert("BQJCRHHNABKAKU-KBQPJGBKSA-N",
  from = "inchikey", to = "csid"
)
cs_convert("BQJCRHHNABKAKU-KBQPJGBKSA-N",
  from = "inchikey", to = "inchi"
)
cs_convert("BQJCRHHNABKAKU-KBQPJGBKSA-N",
  from = "inchikey", to = "mol"
)
cs_convert(160, from = "csid", to = "smiles")
} # }
```
