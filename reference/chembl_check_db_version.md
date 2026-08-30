# Retrieve the default ChEMBL database version

Look for a default ChEMBL database version set via .Renviron or
.Rprofile.

## Usage

``` r
chembl_check_db_version()
```

## Value

the pinned version as a character string

## Details

Set a default version to avoid specifying \`version\` on every call to
an offline ChEMBL function (e.g. \[connect_chembl()\],
\[chembl_query()\], \[db_download_chembl()\]): store it as
`CHEMBL_DB_VERSION = "37"` in .Renviron, or as
`options(chembl_db_version = "37")` in .Rprofile or at runtime. A
version passed directly to a function always overrides this default.
This also lets a project's ChEMBL database version be pinned in one
place (e.g. alongside an \`renv\` lockfile) for reproducibility.

## See also

\[usethis::edit_r_environ()\], \[usethis::edit_r_profile()\]

## Examples

``` r
if (FALSE) { # \dontrun{
chembl_check_db_version()
} # }
```
