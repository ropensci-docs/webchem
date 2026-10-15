# Retrieve all ATC classes

Retrieve all available classes within the Anatomical Therapeutic
Chemical (ATC) classification system.

## Usage

``` r
chembl_atc_classes(verbose = getOption("verbose"), ...)
```

## Arguments

- verbose:

  logical; should a verbose output be printed on the console?

- ...:

  additional arguments, only used for internal testing.

## References

Gaulton, A., Bellis, L. J., Bento, A. P., Chambers, J., Davies, M.,
Hersey, A., ... & Overington, J. P. (2012). ChEMBL: a large-scale
bioactivity database for drug discovery. Nucleic acids research, 40(D1),
D1100-D1107.

## Examples

``` r
if (FALSE) { # \dontrun{
# Might fail if API is not available

atc <- atc_classes()
} # }
```
