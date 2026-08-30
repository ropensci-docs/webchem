# Query https://pesticidecompendium.bcpc.org

Query the BCPC Compendium of Pesticide Common Names
<https://pesticidecompendium.bcpc.org> formerly known as Alan Woods
Compendium of Pesticide Common Names

## Usage

``` r
bcpc_query(
  query,
  from = c("name", "cas"),
  verbose = getOption("verbose"),
  type,
  ...
)
```

## Arguments

- query:

  character; search string

- from:

  character; type of input ('cas' or 'name')

- verbose:

  logical; print message during processing to console?

- type:

  deprecated

- ...:

  additional arguments to internal utility functions

## Value

A list of eleven entries: common-name, status, preferred IUPAC Name,
IUPAC Name, cas, formula, activity, subactivity, inchikey, inchi and
source url.

## Note

for from = 'cas' only the first matched link is returned. Please respect
Copyright, Terms and Conditions
<https://pesticidecompendium.bcpc.org/legal.html>!

## References

Eduard Szöcs, Tamás Stirling, Eric R. Scott, Andreas Scharmüller, Ralf
B. Schäfer (2020). webchem: An R Package to Retrieve Chemical
Information from the Web. Journal of Statistical Software, 93(13).
[doi:10.18637/jss.v093.i13](https://doi.org/10.18637/jss.v093.i13) .

## Examples

``` r
if (FALSE) { # \dontrun{
bcpc_query('Fluazinam', from = 'name')
out <- bcpc_query(c('Fluazinam', 'Diclofop'), from = 'name')
out
# extract subactivity from object
sapply(out, function(y) y$subactivity[1])

# use CAS-numbers
bcpc_query("79622-59-6", from = 'cas')
} # }
```
