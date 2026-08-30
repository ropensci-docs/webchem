# Download FooDB database

Download the FooDB database for offline access.

## Usage

``` r
db_download_foodb(verbose = getOption("verbose"))
```

## Arguments

- verbose:

  logical; should verbose messages be printed to the console?

## Value

Invisibly returns the file path to the processed SQLite database.

## Details

FooDB is a static database with a single release. `db_download_foodb()`
downloads the data set in JSON format and converts it to SQLite. If the
database has already been downloaded and processed, the function will
skip the download and conversion steps and simply return the file path
to the existing database.

## Note

The SQLite database does not include spectra downloads. See
<https://foodb.ca/downloads> for more information on these data files.

## Examples

``` r
if (FALSE) { # \dontrun{
db_download_foodb(verbose = TRUE)
} # }
```
