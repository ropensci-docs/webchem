# Query ChEMBL

Retrieve ChEMBL data using a vector of IDs.

## Usage

``` r
chembl_query(
  query,
  resource = "molecule",
  mode = "ws",
  output = "raw",
  cache_file = NULL,
  similarity = 70,
  version = NULL,
  verbose = getOption("verbose"),
  ...
)
```

## Arguments

- query:

  character; a vector of IDs. The type of ID depends on the resource.
  See examples for more information.

- resource:

  character; the ChEMBL resource to query. Use \[chembl_resources()\] to
  see all available resources.

- mode:

  character; either "ws" (default) to use the webservice or "offline" to
  use a local ChEMBL database. Note, to use the "offline" mode, you need
  to have a local ChEMBL database. See \[db_download_chembl()\].

- output:

  character; either "raw" (default) to return the raw results which is a
  list of lists, or "tidy" to return simplified results, if possible.

- cache_file:

  character or NULL; name of the cache file (without extension) used
  when mode = "ws". If NULL (default), results are not cached.

- similarity:

  numeric; similarity threshold for similarity searches (default 70).

- version:

  character; database version to use in "offline" mode. If \`NULL\`
  (default), \[chembl_check_db_version()\] resolves a default set via
  .Renviron or .Rprofile. Ignored when \`mode = "ws"\`.

- verbose:

  logical; should a verbose output be printed on the console?

- ...:

  additional arguments, only used for internal testing.

## Value

The function returns a list of lists, where each element of the list
contains a list of respective query results. If \`tidy = TRUE\` results
are simplified, if possible.

## Details

Each entry in ChEMBL has a unique ID. Data in ChEMBL is organized in
databases called resources. An entry may or may not have a record in a
particular resource. An entry may have a record in more than one
resource, e.g. a compound may be present in both the "molecule" and the
"drug" resource. This function queries a vector of IDs from a specific
ChEMBL resource.

If you are unsure which ChEMBL resource contains your ChEMBL ID, use
this function with the `"chembl_id_lookup"` resource to find the
appropriate resource for a ChEMBL ID. Note that `"chembl_id_lookup"` is
not a separate function but a resource used by `chembl_query`.

If `mode = "ws"` and `cache_file` is not \`NULL\` the function creates a
cache directory in the working directory and a cache file in the cache
directory. This file is used in subsequent calls of the function. The
cache file is extended as new ID-s are queried during the session.

## Note

Links to the webservice documentation:

- <https://chembl.gitbook.io/chembl-interface-documentation>,

- <https://www.ebi.ac.uk/chembl/api/data/docs>

## References

Gaulton, A., Bellis, L. J., Bento, A. P., Chambers, J., Davies, M.,
Hersey, A., ... & Overington, J. P. (2012). ChEMBL: a large-scale
bioactivity database for drug discovery. Nucleic acids research, 40(D1),
D1100-D1107.

## Examples

``` r
if (FALSE) { # \dontrun{
# Might fail if API is not available

# Examples with resources that operate on compounds

# Resource: biotherapeutic - requires compound ChEMBL ID
chembl_query("CHEMBL448105", resource = "biotherapeutic")

# Resource: compound_structural_alert - requires compound ChEMBL ID
chembl_query(
  "CHEMBL266429",
  resource = "compound_structural_alert"
)

# Resource: compound_record - requires compound record ID
chembl_query("1", resource = "compound_record")

# Resource: drug - requires compound ChEMBL ID
chembl_query("CHEMBL2", resource = "drug")

# Resource: molecule - requires compound ChEMBL ID
chembl_query("CHEMBL1082", resource = "molecule")
chembl_query(c("CHEMBL25", "CHEMBL1082"), resource = "molecule")

# Resource: molecule_form - requires compound ChEMBL ID
chembl_query("CHEMBL6329", resource = "molecule_form")

# Resource: similarity - requires compound SMILES
# By default, the function will use 70 as similarity threshold
chembl_query(
  "CC(=O)Oc1ccccc1C(=O)O", resource = "similarity",
  similarity = 70
)

# Resource: substructure - requires compound SMILES
chembl_query("CN(CCCN)c1cccc2ccccc12", resource = "substructure")

# Other Examples

# Resource: "activity" - requires activity ID
chembl_query("31863", resource = "activity")

# Resource: "assay" - requires assay ChEMBL ID
chembl_query("CHEMBL615117", resource = "assay")

# Resource: "atc_class" - requires ATC class ID
chembl_query("A01AA01", resource = "atc_class")

# Resource: binding_site - requires site ID
chembl_query(2, resource = "binding_site")

# Resource: cell_line - requires ChEMBL ID
chembl_query("CHEMBL3307241", resource = "cell_line")

# Resource: chembl_id_lookup - requires ChEMBL ID
chembl_query("CHEMBL1", resource = "chembl_id_lookup")

# Resource: document - requires document ChEMBL ID
chembl_query("CHEMBL1158643", resource = "document")

# Resource: document_similarity - requires document 1 ChEMBL ID
chembl_query("CHEMBL1148466", resource = "document_similarity")

# Resource: drug_indication - requires drug indication ID
chembl_query("22606", resource = "drug_indication")

# Resource: drug_warning - requires warning ID
chembl_query("1", resource = "drug_warning")

# Resource: go_slim - requires GO ID
chembl_query("GO:0000003", resource = "go_slim")

# Resource: mechanism - requires mechanism ID
chembl_query("13", resource = "mechanism")

# Resource: metabolism - requires metabolism ID
chembl_query("119", resource = "metabolism")

# Resource: organism - requires organism class ID (not taxid)
chembl_query("1", resource = "organism")

# Resource: protein_classification - requires protein class ID
chembl_query("1", resource = "protein_classification")

# Resource: source - requires source ID
chembl_query("1", resource = "source")

# Resource: target - requires target ChEMBL ID
chembl_query("CHEMBL2074", resource = "target")

# Resource: target_component - requires target component ID
chembl_query("1", resource = "target_component")

# Resource: target_relation - requires target ChEMBL ID
chembl_query("CHEMBL2251", resource = "target_relation")

# Resource: tissue - requires tissue ChEMBL ID
chembl_query("CHEMBL3988026", resource = "tissue")

# Resource: xref_source - requires the name of the resource
chembl_query("AlphaFoldDB", resource = "xref_source")
} # }
```
