# Download images from ChemSpider

Retrieve images of substances from ChemSpider and export them in PNG
format.

## Usage

``` r
cs_img(
  csid,
  dir,
  overwrite = TRUE,
  apikey = NULL,
  verbose = getOption("verbose")
)
```

## Arguments

- csid:

  numeric; the ChemSpider ID (CSID) of the substance. This will also be
  the name of the image file.

- dir:

  character; the download directory. `dir` accepts both absolute and
  relative paths.

- overwrite:

  logical; should existing files in the directory with the same name be
  overwritten?

- apikey:

  character; your API key. If NULL (default),
  [`cs_check_key()`](https://docs.ropensci.org/webchem/reference/cs_check_key.md)
  will look for it in .Renviron or .Rprofile.

- verbose:

  logical; should a verbose output be printed on the console?

## Note

An API key is needed. Register at <https://developer.rsc.org/> for an
API key. Please respect the Terms & Conditions. The Terms & Conditions
can be found at <https://developer.rsc.org/terms>.

## References

<https://developer.rsc.org/docs/compounds-v1-trial/1/overview>

## See also

[`get_csid`](https://docs.ropensci.org/webchem/reference/get_csid.md),
[`cs_check_key`](https://docs.ropensci.org/webchem/reference/cs_check_key.md)

## Examples

``` r
if (FALSE) { # \dontrun{
cs_img(c(582, 682), dir = tempdir())
} # }
```
