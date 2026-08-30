# Retrieve ChemSpider API key

Look for and retrieve ChemSpider API key stored in .Renviron or
.Rprofile.

## Usage

``` r
cs_check_key()
```

## Value

an API key

## Details

To use the any of the functions in `webchem` that access the ChemSpider
database, you'll need to obtain an API key. Register at
<https://developer.rsc.org/> for an API key. Please respect the Terms &
Conditions <https://developer.rsc.org/terms>.

You can store your API key as `CHEMSPIDER_KEY = <your key>` in .Renviron
or as `options(chemspider_key = <your key>)` in .Rprofile. This will
allow you to use ChemSpider without adding your API key in the beginning
of each session, and will also allow you to share your analysis without
sharing your API key. Keeping your API key hidden is good practice.

## See also

[`edit_r_environ`](https://usethis.r-lib.org/reference/edit.html)
[`edit_r_profile`](https://usethis.r-lib.org/reference/edit.html)

## Examples

``` r
if (FALSE) { # \dontrun{
cs_check_key()
} # }
```
