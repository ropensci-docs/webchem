# Download ChEMBL database

Download a version of the ChEMBL database for offline access.

## Usage

``` r
db_download_chembl(version = NULL, verbose = getOption("verbose"))
```

## Arguments

- version:

  character, the database release version. See Details for more
  information.

- verbose:

  logical; should verbose messages be printed to the console?

## Value

Downloads the requested database files.

## Details

If `version = NULL` (default), the function calls
\[chembl_check_db_version()\] to look for a pinned version to download,
or stops with an error if it cannot find any. If `version = "latest"`,
the function downloads the newest version currently published by ChEMBL.
If a specific version is requested, the function downloads that version.

## Note

If a checksum file is available for the requested version it will be
used to check data integrity. To save storage space, webchem only
retrieves those files that are used by the package. If you need other
files as well, please download them manually.

## References

You can find more information about ChEMBL releases at
<https://chembl.gitbook.io/chembl-interface-documentation/downloads>

## Examples

``` r
if (FALSE) { # \dontrun{
db_download_chembl()
db_download_chembl(version = "latest")
db_download_chembl(version = "35")
} # }
```
