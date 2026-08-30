# Retrieve flavor percepts from www.flavornet.org

Retrieve flavor percepts from <http://www.flavornet.org>. Flavornet is a
database of 738 compounds with odors perceptible to humans detected
using gas chromatography olfactometry (GCO).

## Usage

``` r
fn_percept(query, from = "cas", verbose = getOption("verbose"), CAS, ...)
```

## Arguments

- query:

  character; CAS number to search by. See
  [`is.cas`](https://docs.ropensci.org/webchem/reference/is.cas.md) for
  correct formatting

- from:

  character; currently only CAS numbers are accepted.

- verbose:

  logical; should a verbose output be printed on the console?

- CAS:

  deprecated

- ...:

  currently unused

## Value

A named character vector containing flavor percepts or NA's in the case
of CAS numbers that are not found

## Examples

``` r
if (FALSE) { # \dontrun{
# might fail if website is not available
fn_percept("123-32-0")

CASs <- c("75-07-0",  "64-17-5",  "109-66-0", "78-94-4",  "78-93-3")
fn_percept(CASs)
} # }
```
