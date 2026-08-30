# Query Chemical Identifier Resolver Images

A interface to the Chemical Identifier Resolver (CIR).
(<https://cactus.nci.nih.gov/chemical/structure_documentation>).

## Usage

``` r
cir_img(
  query,
  dir,
  format = c("png", "gif"),
  width = 500,
  height = 500,
  linewidth = 2,
  symbolfontsize = 16,
  bgcolor = NULL,
  antialiasing = TRUE,
  atomcolor = NULL,
  bondcolor = NULL,
  csymbol = c("special", "all"),
  hsymbol = c("special", "all"),
  hcolor = NULL,
  header = NULL,
  footer = NULL,
  frame = NULL,
  verbose = getOption("verbose"),
  ...
)
```

## Arguments

- query:

  character; Search term. Can be any common chemical identifier (e.g.
  CAS, INCHI(KEY), SMILES etc.)

- dir:

  character; Directory to save the image.

- format:

  character; Output format of the image. Can be one of "png", "gif".

- width:

  integer; Width of the image.

- height:

  integer; Height of the image.

- linewidth:

  integer; Width of lines.

- symbolfontsize:

  integer; Fontsize of atoms in the image.

- bgcolor:

  character; E.g. transparent, white, %23AADDEE

- antialiasing:

  logical; Should antialiasing be used?

- atomcolor:

  character; Color of the atoms in the image.

- bondcolor:

  character; Color of the atom bond lines.

- csymbol:

  character; Can be one of "special" (default - i.e. only hydrogen atoms
  in functional groups or defining stereochemistry) or "all".

- hsymbol:

  character; Can be one of "special" (default - i.e. none are shown) or
  "all" (all are printed).

- hcolor:

  character; Color of the hydrogen atoms.

- header:

  character; Should a header text be added to the image? Can be any
  string.

- footer:

  character; Should a footer text be added to the image? Can be any
  string.

- frame:

  integer; Should a frame be plotted? Can be on of NULL (default) or 1.

- verbose:

  logical; Should a verbose output be printed on the console?

- ...:

  currently not used.

## Value

image written to disk

## Details

CIR can resolve can be of the following `identifier`: Chemical Names,
IUPAC names, CAS Numbers, SMILES strings, IUPAC InChI/InChIKeys,
NCI/CADD Identifiers, CACTVS HASHISY, NSC number, PubChem SID, ZINC
Code, ChemSpider ID, ChemNavigator SID, eMolecule VID.

For an image with transparent background use ‘transparent’ as color name
and switch off antialiasing (i.e. antialiasing = 0).

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
cir_img("CCO", dir = tempdir()) # SMILES

# multiple query strings and different formats
query = c("Glyphosate", "Isoproturon", "BSYNRYMUTXBXSQ-UHFFFAOYSA-N")
cir_img(query, dir = tempdir(), bgcolor = "transparent", antialising = 0)

# all parameters
query  = "Triclosan"
cir_img(query,
        dir = tempdir(),
        format = "png",
        width = 600,
        height = 600,
        linewidth = 5,
        symbolfontsize = 30,
        bgcolor = "red",
        antialiasing = FALSE,
        atomcolor = "green",
        bondcolor = "yellow",
        csymbol = "all",
        hsymbol = "all",
        hcolor = "purple",
        header = "My funky chemical structure..",
        footer = "..is just so awesome!",
        frame = 1,
        verbose = getOption("verbose"))
} # }
```
