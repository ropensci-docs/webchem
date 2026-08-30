# Download images from ChEMBL

Retrieve images of substances from ChEMBL and save them in SVG format.

## Usage

``` r
chembl_img(query, dir = NULL, verbose = getOption("verbose"), ...)
```

## Arguments

- query:

  character; a vector of ChEMBL IDs.

- dir:

  character; the directory in which to save the image(s). If the
  directory does not exist, it will be created. If \`NULL\` (default),
  the working directory will be used.

- verbose:

  logical; should verbose messages be printed to the console?

- ...:

  additional arguments, only used for internal testing.

## Value

Creates the download directory if needed and downloads one or more SVG
files.

## Examples

``` r
if (FALSE) { # \dontrun{
# download a single image
chembl_img("CHEMBL1")
# download a single image to another directory
chembl_img("CHEMBL1", dir = tempdir())
# download multiple images
chembl_img(c("CHEMBL1", "CHEMBL2"))
} # }
```
