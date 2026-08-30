# Export a Chemical Structure in .mol Format.

Some webchem functions return character strings that contain a chemical
structure in Mol format. This function exports a character string as a
.mol file so it can be imported with other chemistry software.

## Usage

``` r
write_mol(x, file = "")
```

## Arguments

- x:

  a character string of a chemical structure in mol format.

- file:

  a character vector of file names

## Examples

``` r
if (FALSE) { # \dontrun{
# export Mol file
csid <- get_csid("bergapten")
mol3d <- cs_compinfo(csid$csid, field = "Mol3D")
write_mol(mol3d$mol3D, file = mol3d$id)

# export multiple Mol files
csids <- get_csid(c("bergapten", "xanthotoxin"))
mol3ds <- cs_compinfo(csids$csid, field = "Mol3D")
mapply(function(x, y) write_mol(x, y), x = mol3ds$mol3D, y = mol3ds$id)
} # }
```
