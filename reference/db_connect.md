# Connect to a database

This function connects to a database and returns a connection object.
Currently, it supports the following databases: "chembl", "eup", and
"foodb".

## Usage

``` r
db_connect(db, version = NULL, ...)
```

## Arguments

- db:

  character; database name. Must be one of "chembl", "eup", or "foodb".

- version:

  character; version of the database. Only applicable for "chembl". If
  \`NULL\` (default), \[chembl_check_db_version()\] resolves a default
  set via .Renviron or .Rprofile.

- ...:

  Further args passed on to \[DBI::dbConnect()\]

## Value

an object of class "SQLiteConnection".

## Examples

``` r
if (FALSE) { # \dontrun{
# Connect to a specific version of the ChEMBL database
con <- db_connect("chembl", version = "37")
# Connect to the EU Pesticides database
con <- db_connect("eup")
# Connect to the FooDB database
con <- db_connect("foodb")
} # }
```
