# Get Wikidata Item ID

Search www.wikidata.org for wikidata item identifiers. Note that this
search is currently not limited to chemical substances, so be sure to
check your results.

## Usage

``` r
get_wdid(
  query,
  match = c("best", "first", "all", "ask", "na"),
  verbose = getOption("verbose"),
  language = "en"
)
```

## Arguments

- query:

  character; The searchterm

- match:

  character; How should multiple hits be handeled? 'all' returns all
  matched IDs, 'first' only the first match, 'best' the best matching
  (by name) ID, 'ask' is a interactive mode and the user is asked for
  input, na' returns NA if multiple hits are found.

- verbose:

  logical; print message during processing to console?

- language:

  character; the language to search in

## Value

if match = 'all' a list with ids, otherwise a dataframe with 4 columns:
id, matched text, string distance to match and the queried string

## Note

Only matches in labels are returned.

## Examples

``` r
if (FALSE) { # \dontrun{
get_wdid('Triclosan', language = 'de')
get_wdid('DDT')
get_wdid('DDT', match = 'all')

# multiple inputs
comps <- c('Triclosan', 'Glyphosate')
get_wdid(comps)
} # }
```
