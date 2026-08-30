# Query Chemical Identifier Resolver

A interface to the Chemical Identifier Resolver (CIR).
(<https://cactus.nci.nih.gov/chemical/structure_documentation>).

## Usage

``` r
cir_query(
  identifier,
  representation = "smiles",
  resolver = NULL,
  match = c("all", "first", "ask", "na"),
  verbose = getOption("verbose"),
  choices = NULL,
  ...
)
```

## Arguments

- identifier:

  character; chemical identifier.

- representation:

  character; what representation of the identifier should be returned.
  See details for possible representations.

- resolver:

  character; what resolver should be used? If NULL (default) the
  identifier type is detected and the different resolvers are used in
  turn. See details for possible resolvers.

- match:

  character; How should multiple hits be handled? `"all"` returns all
  matches, `"first"` returns only the first result, `"ask"` enters an
  interactive mode and the user is asked for input, `"na"` returns `NA`
  if multiple hits are found.

- verbose:

  logical; should a verbose output be printed on the console?

- choices:

  deprecated. Use the `match` argument instead.

- ...:

  currently not used.

## Value

A tibble with a \`query\` column and a column for the requested
representation.

## Details

CIR can resolve can be of the following `identifier`: Chemical Names,
IUPAC names, CAS Numbers, SMILES strings, IUPAC InChI/InChIKeys,
NCI/CADD Identifiers, CACTVS HASHISY, NSC number, PubChem SID, ZINC
Code, ChemSpider ID, ChemNavigator SID, eMolecule VID.

`cir_query()` can handle only a part of all possible conversions of CIR.
Possible `representations` are:

- `'smiles'`(SMILES strings),

- `'names'` (Names),

- `'cas'` (CAS numbers),

- `'stdinchikey'` (Standard InChIKey),

- `'stdinchi'` (Standard InChI),

- `'ficts'` (FICTS Identifier),

- `'ficus'` (FICuS Indetifier),

- `'uuuuu'` (uuuuu Identifier),

- `'mw'` (Molecular weight),

- `'monoisotopic_mass'` (Monoisotopic Mass),

- `'formula'` (Chemical Formula),

- `'chemspider_id'` (ChemSpider ID),

- `'pubchem_sid'` (PubChem SID),

- `'chemnavigator_sid'` (ChemNavigator SID),

- `'h_bond_donor_count'` (Number of Hydrogen Bond Donors),

- `'h_bond_acceptor_count'` (Number of Hydrogen Bond Acceptors),

- `'h_bond_center_count'` (Number of Hydrogen Bond Centers),

- `'rule_of_5_violation_count'` (Number of Rule of 5 Violations),

- `'rotor_count'` (Number of Freely Rotatable Bonds),

- `'effective_rotor_count'` (Number of Effectively Rotatable Bonds),

- `'ring_count'` (Number of Rings),

- `'ringsys_count'` (Number of Ring Systems),

- `'xlogp2'` (octanol-water partition coefficient),

- `'aromatic'` (is the compound aromatic),

- `'macrocyclic'` (is the compound macrocyclic),

- `'heteroatom_count'` (heteroatom count),

- `'hydrogen_atom_count'` (H atom count),

- `'heavy_atom_count'` ( Heavy atom count),

- `'deprotonable_group_count'` (Number of deprotonable groups),

- `'protonable_group_count'` (Number of protonable groups).

CIR first tries to determine the identifier type submitted and then uses
'resolvers' to look up the data. If no `resolver` is supplied, CIR tries
different resolvers in turn till a hit is found. E.g. for names CIR
tries first to look up in OPSIN and if this fails the local name index
of CIR. However, it can be also specified which resolvers to use (if you
know e.g. know your identifier type) Possible `resolvers` are:

- `'name_by_cir'` (Lookup in name index of CIR),

- `'name_by_opsin'` (Lookup in OPSIN),

- `'name_by_chemspider'` (Lookup in ChemSpider,
  <https://cactus.nci.nih.gov/blog/?p=1386>),

- `'smiles'` (Lookup SMILES),

- `'stdinchikey'`, `'stdinchi'` (InChI),

- `'cas_number'` (CAS Number),

- `'name_pattern'` (Google-like pattern search
  (<https://cactus.nci.nih.gov/blog/?p=1456>) Note, that the pattern
  search can be combined with other resolvers, e.g.
  `resolver = 'name_by_chemspider,name_pattern'`.

## Note

You can only make 1 request per second (this is a hard-coded feature).

## References

`cir` relies on the great CIR web service created by the CADD Group at
NCI/NIH!  
<https://cactus.nci.nih.gov/chemical/structure_documentation>,  
<https://cactus.nci.nih.gov/blog/?cat=10>,  
<https://cactus.nci.nih.gov/blog/?p=1386>,  
<https://cactus.nci.nih.gov/blog/?p=1456>,  

## Examples

``` r
if (FALSE) { # \dontrun{
# might fail if API is not available
cir_query("Triclosan", "cas")
cir_query("3380-34-5", "cas", match = "first")
cir_query("3380-34-5", "cas", resolver = "cas_number")
cir_query("3380-34-5", "smiles")
cir_query("Triclosan", "mw")

# multiple inputs
comp <- c("Triclosan", "Aspirin")
cir_query(comp, "cas", match = "first")

} # }
```
