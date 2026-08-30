# Control ChemSpider API requests

For some ChemSpider API requests, you can also specify various control
options. This function is used to set these control options.

## Usage

``` r
cs_control(
  datasources = vector(),
  order_by = "default",
  order_direction = "default",
  include_all = FALSE,
  complexity = "any",
  isotopic = "any"
)
```

## Arguments

- datasources:

  character; specifies the databases to query. Use
  [`cs_datasources()`](https://docs.ropensci.org/webchem/reference/cs_datasources.md)
  to retrieve available ChemSpider data sources.

- order_by:

  character; specifies the sort order for the results. Valid values are
  `"default"`, `"recordId"`, `"massDefect"`, `"molecularWeight"`,
  `"referenceCount"`, `"dataSourceCount"`, `"pubMedCount"`,
  `"rscCount"`.

- order_direction:

  character; specifies the sort order for the results. Valid values are
  `"default"`, `"ascending"`, `"descending"`.

- include_all:

  logical; see details.

- complexity:

  character; see details. Valid values are `"any"` `"single"`,
  `"multiple"`.

- isotopic:

  character; see details. Valid values are `"any"`, `"labeled"`,
  `"unlabeled"`.

## Value

Returns a list of specified control options.

## Details

The only function that currently uses `databases` is
[`get_csid()`](https://docs.ropensci.org/webchem/reference/get_csid.md)
and only when you query a CSID from a formula. This parameter is
disregarded in all other queries.

Setting `include_all` to `TRUE` will consider records which contain all
of the filter criteria specified in the request. Setting it to `FALSE`
will consider records which contain any of the filter criteria.

A compound with a `complexity` of `"multiple"` has more than one
disconnected system in it or a metal atom or ion.

## Note

This is a full list of all API control options. However, not all of
these options are used in all functions. Each API uses a subset of these
controls. The controls that are available for a given function are
indicated within the documentation of the function.

## References

<https://developer.rsc.org/docs/compounds-v1-trial/1/overview>

## See also

[`get_csid`](https://docs.ropensci.org/webchem/reference/get_csid.md)

## Examples

``` r
cs_control()
#> $datasources
#> logical(0)
#> 
#> $order_by
#> [1] "default"
#> 
#> $order_direction
#> [1] "default"
#> 
#> $include_all
#> [1] FALSE
#> 
#> $complexity
#> [1] "any"
#> 
#> $isotopic
#> [1] "any"
#> 
cs_control(order_direction = "descending")
#> $datasources
#> logical(0)
#> 
#> $order_by
#> [1] "default"
#> 
#> $order_direction
#> [1] "descending"
#> 
#> $include_all
#> [1] FALSE
#> 
#> $complexity
#> [1] "any"
#> 
#> $isotopic
#> [1] "any"
#> 
```
