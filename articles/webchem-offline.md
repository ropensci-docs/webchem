# Working with offline databases

``` r

library(webchem)
```

Webchem provides offline access to three databases: ChEMBL, FooDB, and
the EU Pesticides database. This means you download them once, and then
you can query them locally without an internet connection. Reliable and
lightning fast!

## Downloading a database

`webchem` uses the `hoardr` package for managing database files. By
default, `hoardr` will save into a users `.cache/R/webchem` directory.
We can set a custom directory for databases using
`wc_cache$cache_path_set()`. This can be useful when we work on a long
running project and we want to store database files in the project
directory. The current cache path can be retrieved using
`wc_cache$cache_path_get()`.

Databases can be downloaded using
[`db_download_chembl()`](https://docs.ropensci.org/webchem/reference/db_download_chembl.md),
[`db_download_foodb()`](https://docs.ropensci.org/webchem/reference/db_download_foodb.md)
or
[`db_download_eup()`](https://docs.ropensci.org/webchem/reference/db_download_eup.md).
Note that ChEMBL maintainers regularly issue new releases. We can pin a
ChEMBL release for our project using
[`chembl_check_db_version()`](https://docs.ropensci.org/webchem/reference/chembl_check_db_version.md)
or download the latest version. At the time of writing the other two
databases only had one version so their downloaders do not have a
`version` argument yet.

## Querying the database

ChEMBL’s main query function is
[`chembl_query()`](https://docs.ropensci.org/webchem/reference/chembl_query.md).
It will use the webservice by default but `mode = "offline"` will use
the offline database instead. It is intended to be a drop-in replacement
so you can expect the structure of the offline response to be at least
very similar to the webservice response. Fields that are missing from
the offline response are listed in a warning message.

``` r

res <- chembl_query("CHEMBL2", resource = "drug", mode = "offline", version = "37")
names(res$CHEMBL2)
```

The other two databases are implemented in offline mode only.
[`eup_list_entries()`](https://docs.ropensci.org/webchem/reference/eup_list_entries.md)
and
[`foodb_list_compounds()`](https://docs.ropensci.org/webchem/reference/foodb_list_compounds.md)
list available substances in the database,
[`eup_convert()`](https://docs.ropensci.org/webchem/reference/eup_convert.md)
and
[`foodb_convert()`](https://docs.ropensci.org/webchem/reference/foodb_convert.md)
convert between identifiers,
[`eup_query()`](https://docs.ropensci.org/webchem/reference/eup_query.md)
and
[`foodb_query()`](https://docs.ropensci.org/webchem/reference/foodb_query.md)
query the database for information on a substance.

Look at compounds in foodb:

``` r

res <- foodb_list_compounds(idtype = "name")
grep("Folic", res, value = TRUE)
```

Convert folic acid to some other supported ID:

``` r

foodb_convert("Folic acid", from = "name", to = "cas_number")
```

Let’s see some synonyms:

``` r

foodb_query("Folic acid", from = "name")$synonyms
```

If we want low level access to the database, we can use
[`db_connect()`](https://docs.ropensci.org/webchem/reference/db_connect.md)
to establish the connection and then use e.g. `dplyr` to interact with
the database.
[`db_connect()`](https://docs.ropensci.org/webchem/reference/db_connect.md)
is essentially a wrapper around
[`DBI::dbConnect()`](https://dbi.r-dbi.org/reference/dbConnect.html)
which automatically resolves the database path.

Let’s connect to FooDB

``` r

conn <- db_connect("foodb")
```

List tables:

``` r

conn |> DBI::dbListTables()
```

Let’s look at the first few rows and columns of the “Compound” table:

``` r

dplyr::tbl(conn, "Compound") |> dplyr::select(1:5) |> head()
```
