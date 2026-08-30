# Package index

## Retrieve and translate chemical identifiers

- [`get_chebiid()`](https://docs.ropensci.org/webchem/reference/get_chebiid.md)
  : Retrieve Lite Entity (identifiers) from ChEBI
- [`get_cid()`](https://docs.ropensci.org/webchem/reference/get_cid.md)
  : Retrieve Pubchem Compound ID (CID)
- [`get_csid()`](https://docs.ropensci.org/webchem/reference/get_csid.md)
  : ChemSpider ID from compound name, formula, SMILES, InChI or InChIKey
- [`get_etoxid()`](https://docs.ropensci.org/webchem/reference/get_etoxid.md)
  : Get ETOX ID
- [`get_wdid()`](https://docs.ropensci.org/webchem/reference/get_wdid.md)
  : Get Wikidata Item ID
- [`cs_convert()`](https://docs.ropensci.org/webchem/reference/cs_convert.md)
  : Convert identifiers using ChemSpider
- [`cts_convert()`](https://docs.ropensci.org/webchem/reference/cts_convert.md)
  : Convert Ids using Chemical Translation Service (CTS)
- [`eup_convert()`](https://docs.ropensci.org/webchem/reference/eup_convert.md)
  : Convert identifiers in the local EU Pesticides database
- [`foodb_convert()`](https://docs.ropensci.org/webchem/reference/foodb_convert.md)
  : Convert compound identifiers in the local FooDB database
- [`cts_from()`](https://docs.ropensci.org/webchem/reference/cts_from.md)
  : Return a list of all possible ids
- [`cts_to()`](https://docs.ropensci.org/webchem/reference/cts_to.md) :
  Return a list of all possible ids
- [`eup_list_entries()`](https://docs.ropensci.org/webchem/reference/eup_list_entries.md)
  : List available entries in the local EU Pesticides database
- [`foodb_list_compounds()`](https://docs.ropensci.org/webchem/reference/foodb_list_compounds.md)
  : List available compound identifiers in the local FooDB database
- [`with_cts()`](https://docs.ropensci.org/webchem/reference/with_cts.md)
  : Auto-translate identifiers and search databases
- [`wd_ident()`](https://docs.ropensci.org/webchem/reference/wd_ident.md)
  : Retrieve identifiers from Wikidata
- [`pc_synonyms()`](https://docs.ropensci.org/webchem/reference/pc_synonyms.md)
  : Search synonyms in pubchem
- [`opsin_query()`](https://docs.ropensci.org/webchem/reference/opsin_query.md)
  : OPSIN web interface
- [`etox_basic()`](https://docs.ropensci.org/webchem/reference/etox_basic.md)
  : Get basic information from a ETOX ID

## Retrieve chemical properties

- [`bcpc_query()`](https://docs.ropensci.org/webchem/reference/bcpc_query.md)
  : Query https://pesticidecompendium.bcpc.org
- [`chembl_query()`](https://docs.ropensci.org/webchem/reference/chembl_query.md)
  : Query ChEMBL
- [`cir_query()`](https://docs.ropensci.org/webchem/reference/cir_query.md)
  : Query Chemical Identifier Resolver
- [`eup_query()`](https://docs.ropensci.org/webchem/reference/eup_query.md)
  : Query EU Pesticides
- [`foodb_query()`](https://docs.ropensci.org/webchem/reference/foodb_query.md)
  : Query the local FooDB database for compound information
- [`opsin_query()`](https://docs.ropensci.org/webchem/reference/opsin_query.md)
  : OPSIN web interface
- [`srs_query()`](https://docs.ropensci.org/webchem/reference/srs_query.md)
  : Get record details from U.S. EPA Substance Registry Servives (SRS)
- [`ppdb_query()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`ppdb_parse()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`ppdb()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`cir()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`pp_query()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`cs_prop()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`ci_query()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`pan_query()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  : Defunct function(s) in the webchem package
- [`cid_compinfo()`](https://docs.ropensci.org/webchem/reference/webchem-deprecated.md)
  [`aw_query()`](https://docs.ropensci.org/webchem/reference/webchem-deprecated.md)
  : Deprecated function(s) in the webchem package
- [`chebi_comp_entity()`](https://docs.ropensci.org/webchem/reference/chebi_comp_entity.md)
  : Retrieve Complete Entity from ChEBI
- [`cs_compinfo()`](https://docs.ropensci.org/webchem/reference/cs_compinfo.md)
  : Retrieve record details by ChemSpider ID
- [`cs_extcompinfo()`](https://docs.ropensci.org/webchem/reference/cs_extcompinfo.md)
  : Get extended record details by ChemSpider ID
- [`cts_compinfo()`](https://docs.ropensci.org/webchem/reference/cts_compinfo.md)
  : Get record details from Chemical Translation Service (CTS)
- [`etox_targets()`](https://docs.ropensci.org/webchem/reference/etox_targets.md)
  : Get Quality Targets from a ETOX ID
- [`etox_tests()`](https://docs.ropensci.org/webchem/reference/etox_tests.md)
  : Get Tests from a ETOX ID
- [`fn_percept()`](https://docs.ropensci.org/webchem/reference/fn_percept.md)
  : Retrieve flavor percepts from www.flavornet.org
- [`nist_ri()`](https://docs.ropensci.org/webchem/reference/nist_ri.md)
  : Retrieve retention indices from NIST
- [`pc_prop()`](https://docs.ropensci.org/webchem/reference/pc_prop.md)
  : Retrieve compound properties from a pubchem CID
- [`pc_sect()`](https://docs.ropensci.org/webchem/reference/pc_sect.md)
  : Retrieve data from PubChem content pages

## Download databases for offline use and connect to them

- [`db_download_chembl()`](https://docs.ropensci.org/webchem/reference/db_download_chembl.md)
  : Download ChEMBL database
- [`db_download_eup()`](https://docs.ropensci.org/webchem/reference/db_download_eup.md)
  : Download the EU Pesticides database and convert to SQLite
- [`db_download_foodb()`](https://docs.ropensci.org/webchem/reference/db_download_foodb.md)
  : Download FooDB database
- [`chembl_check_db_version()`](https://docs.ropensci.org/webchem/reference/chembl_check_db_version.md)
  : Retrieve the default ChEMBL database version
- [`db_connect()`](https://docs.ropensci.org/webchem/reference/db_connect.md)
  : Connect to a database

## Molecular structure images

- [`chembl_img()`](https://docs.ropensci.org/webchem/reference/chembl_img.md)
  : Download images from ChEMBL
- [`cir_img()`](https://docs.ropensci.org/webchem/reference/cir_img.md)
  : Query Chemical Identifier Resolver Images
- [`cs_img()`](https://docs.ropensci.org/webchem/reference/cs_img.md) :
  Download images from ChemSpider

## Cross-data-source functions

- [`find_db()`](https://docs.ropensci.org/webchem/reference/find_db.md)
  : Check data source coverage of compounds

## Data

- [`jagst`](https://docs.ropensci.org/webchem/reference/jagst.md) :
  Organic plant protection products in the river Jagst / Germany in 2013
- [`lc50`](https://docs.ropensci.org/webchem/reference/lc50.md) : Acute
  toxicity data from U.S. EPA ECOTOX

## Utility functions

- [`as.cas()`](https://docs.ropensci.org/webchem/reference/as.cas.md) :
  Format numbers as CAS numbers
- [`is.cas()`](https://docs.ropensci.org/webchem/reference/is.cas.md) :
  Check if input is a valid CAS
- [`is.inchikey()`](https://docs.ropensci.org/webchem/reference/is.inchikey.md)
  : Check if input is a valid inchikey
- [`is.inchikey_cs()`](https://docs.ropensci.org/webchem/reference/is.inchikey_cs.md)
  : Check if input is a valid inchikey using ChemSpider API
- [`is.inchikey_format()`](https://docs.ropensci.org/webchem/reference/is.inchikey_format.md)
  : Check if input is a valid inchikey using format
- [`is.smiles()`](https://docs.ropensci.org/webchem/reference/is.smiles.md)
  : Check if input is a SMILES string
- [`cs_check_key()`](https://docs.ropensci.org/webchem/reference/cs_check_key.md)
  : Retrieve ChemSpider API key
- [`cs_control()`](https://docs.ropensci.org/webchem/reference/cs_control.md)
  : Control ChemSpider API requests
- [`cas()`](https://docs.ropensci.org/webchem/reference/extractors.md)
  [`inchikey()`](https://docs.ropensci.org/webchem/reference/extractors.md)
  [`smiles()`](https://docs.ropensci.org/webchem/reference/extractors.md)
  : Extract parts from webchem objects
- [`ping_service()`](https://docs.ropensci.org/webchem/reference/ping_service.md)
  : Ping an API used in webchem to see if it's working.
- [`cs_datasources()`](https://docs.ropensci.org/webchem/reference/cs_datasources.md)
  : Retrieve ChemSpider data sources
- [`chembl_atc_classes()`](https://docs.ropensci.org/webchem/reference/chembl_atc_classes.md)
  : Retrieve all ATC classes
- [`chembl_status()`](https://docs.ropensci.org/webchem/reference/chembl_status.md)
  : Retrieve ChEMBL webservice status
- [`chembl_resources()`](https://docs.ropensci.org/webchem/reference/chembl_resources.md)
  : List ChEMBL Resources
- [`parse_mol()`](https://docs.ropensci.org/webchem/reference/parse_mol.md)
  : Parse Molfile (as returned by ChemSpider) into a R-object.
- [`write_mol()`](https://docs.ropensci.org/webchem/reference/write_mol.md)
  : Export a Chemical Structure in .mol Format.

## Deprecated and defunct

- [`ppdb_query()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`ppdb_parse()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`ppdb()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`cir()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`pp_query()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`cs_prop()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`ci_query()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  [`pan_query()`](https://docs.ropensci.org/webchem/reference/webchem-defunct.md)
  : Defunct function(s) in the webchem package
- [`cid_compinfo()`](https://docs.ropensci.org/webchem/reference/webchem-deprecated.md)
  [`aw_query()`](https://docs.ropensci.org/webchem/reference/webchem-deprecated.md)
  : Deprecated function(s) in the webchem package

## Package

- [`webchem`](https://docs.ropensci.org/webchem/reference/webchem-package.md)
  [`webchem-package`](https://docs.ropensci.org/webchem/reference/webchem-package.md)
  : webchem: An R package to retrieve chemical information from the web.
