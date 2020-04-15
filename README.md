
<!-- README.md is generated from README.Rmd. Please edit that file -->

# australias-essential-workers

<!-- badges: start -->

<!-- badges: end -->

The goal of this repository is to identify essential workers by their
ANZSIC and ANZSCO codes.

# Data sources

The original data sources of the spreadsheets in ‘data’ folder are as
stated below.

  - ANZSIC:
    <https://www.fwc.gov.au/awards-and-agreements/minimum-wages-conditions/annual-wage-reviews/previous-wage-reviews/annual-wa-0>
  - ANZSCO:
    <https://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/1220.02013,%20Version%201.3?OpenDocument>

# References

# Summary

``` r
library(data.table)
library(readxl)
library(gt)
#> Warning: package 'gt' was built under R version 3.6.2

anzsic_codes <- 
  readxl::read_xlsx(path = "data/raw-data/ANZSIC.xlsx", sheet = "codes") %>%
  janitor::clean_names()
anzsic_divisions <- 
  readxl::read_xlsx(path = "data/raw-data/ANZSIC.xlsx", sheet = "divisions") %>%
  janitor::clean_names()

gt(head(anzsic_divisions, 10)) %>%
  tab_header(
    title = "ANZSIC 2006 divisions"
  )
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#ejiicjsvtq .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#ejiicjsvtq .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#ejiicjsvtq .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#ejiicjsvtq .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#ejiicjsvtq .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#ejiicjsvtq .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#ejiicjsvtq .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#ejiicjsvtq .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#ejiicjsvtq .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#ejiicjsvtq .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#ejiicjsvtq .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#ejiicjsvtq .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#ejiicjsvtq .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#ejiicjsvtq .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#ejiicjsvtq .gt_from_md > :first-child {
  margin-top: 0;
}

#ejiicjsvtq .gt_from_md > :last-child {
  margin-bottom: 0;
}

#ejiicjsvtq .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#ejiicjsvtq .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#ejiicjsvtq .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#ejiicjsvtq .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#ejiicjsvtq .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#ejiicjsvtq .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#ejiicjsvtq .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#ejiicjsvtq .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#ejiicjsvtq .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#ejiicjsvtq .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#ejiicjsvtq .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#ejiicjsvtq .gt_left {
  text-align: left;
}

#ejiicjsvtq .gt_center {
  text-align: center;
}

#ejiicjsvtq .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#ejiicjsvtq .gt_font_normal {
  font-weight: normal;
}

#ejiicjsvtq .gt_font_bold {
  font-weight: bold;
}

#ejiicjsvtq .gt_font_italic {
  font-style: italic;
}

#ejiicjsvtq .gt_super {
  font-size: 65%;
}

#ejiicjsvtq .gt_footnote_marks {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="ejiicjsvtq" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">

<table class="gt_table">

<thead class="gt_header">

<tr>

<th colspan="2" class="gt_heading gt_title gt_font_normal" style>

ANZSIC 2006 divisions

</th>

</tr>

<tr>

<th colspan="2" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>

</th>

</tr>

</thead>

<thead class="gt_col_headings">

<tr>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

anzsic\_division

</th>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

anzsic\_division\_title

</th>

</tr>

</thead>

<tbody class="gt_table_body">

<tr>

<td class="gt_row gt_left">

A

</td>

<td class="gt_row gt_left">

Agriculture, Forestry and Fishing

</td>

</tr>

<tr>

<td class="gt_row gt_left">

B

</td>

<td class="gt_row gt_left">

Mining

</td>

</tr>

<tr>

<td class="gt_row gt_left">

C

</td>

<td class="gt_row gt_left">

Manufacturing

</td>

</tr>

<tr>

<td class="gt_row gt_left">

D

</td>

<td class="gt_row gt_left">

Electricity, Gas, Water and Waste Services

</td>

</tr>

<tr>

<td class="gt_row gt_left">

E

</td>

<td class="gt_row gt_left">

Construction

</td>

</tr>

<tr>

<td class="gt_row gt_left">

F

</td>

<td class="gt_row gt_left">

Wholesale Trade

</td>

</tr>

<tr>

<td class="gt_row gt_left">

G

</td>

<td class="gt_row gt_left">

Retail Trade

</td>

</tr>

<tr>

<td class="gt_row gt_left">

H

</td>

<td class="gt_row gt_left">

Accommodation and Food Services

</td>

</tr>

<tr>

<td class="gt_row gt_left">

I

</td>

<td class="gt_row gt_left">

Transport, Postal and Warehousing

</td>

</tr>

<tr>

<td class="gt_row gt_left">

J

</td>

<td class="gt_row gt_left">

Information Media and Telecommunications

</td>

</tr>

</tbody>

</table>

</div>

<!--/html_preserve-->

``` r

gt(head(anzsic_codes, 10)) %>%
  tab_header(
    title = "ANZSIC 2006 codes", 
    subtitle = "first 10 rows only"
  )
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#nuepwkbcub .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#nuepwkbcub .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#nuepwkbcub .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#nuepwkbcub .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#nuepwkbcub .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#nuepwkbcub .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#nuepwkbcub .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#nuepwkbcub .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#nuepwkbcub .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#nuepwkbcub .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#nuepwkbcub .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#nuepwkbcub .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#nuepwkbcub .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#nuepwkbcub .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#nuepwkbcub .gt_from_md > :first-child {
  margin-top: 0;
}

#nuepwkbcub .gt_from_md > :last-child {
  margin-bottom: 0;
}

#nuepwkbcub .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#nuepwkbcub .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#nuepwkbcub .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#nuepwkbcub .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#nuepwkbcub .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#nuepwkbcub .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#nuepwkbcub .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#nuepwkbcub .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#nuepwkbcub .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#nuepwkbcub .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#nuepwkbcub .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#nuepwkbcub .gt_left {
  text-align: left;
}

#nuepwkbcub .gt_center {
  text-align: center;
}

#nuepwkbcub .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#nuepwkbcub .gt_font_normal {
  font-weight: normal;
}

#nuepwkbcub .gt_font_bold {
  font-weight: bold;
}

#nuepwkbcub .gt_font_italic {
  font-style: italic;
}

#nuepwkbcub .gt_super {
  font-size: 65%;
}

#nuepwkbcub .gt_footnote_marks {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="nuepwkbcub" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">

<table class="gt_table">

<thead class="gt_header">

<tr>

<th colspan="2" class="gt_heading gt_title gt_font_normal" style>

ANZSIC 2006 codes

</th>

</tr>

<tr>

<th colspan="2" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>

first 10 rows only

</th>

</tr>

</thead>

<thead class="gt_col_headings">

<tr>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

anzsic\_code

</th>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

anzsic\_class\_title

</th>

</tr>

</thead>

<tbody class="gt_table_body">

<tr>

<td class="gt_row gt_left">

A0111

</td>

<td class="gt_row gt_left">

Nursery Production (Under Cover)

</td>

</tr>

<tr>

<td class="gt_row gt_left">

A0112

</td>

<td class="gt_row gt_left">

Nursery Production (Outdoors)

</td>

</tr>

<tr>

<td class="gt_row gt_left">

A0113

</td>

<td class="gt_row gt_left">

Turf Growing

</td>

</tr>

<tr>

<td class="gt_row gt_left">

A0114

</td>

<td class="gt_row gt_left">

Floriculture Production (Under Cover)

</td>

</tr>

<tr>

<td class="gt_row gt_left">

A0115

</td>

<td class="gt_row gt_left">

Floriculture Production (Outdoors)

</td>

</tr>

<tr>

<td class="gt_row gt_left">

A0121

</td>

<td class="gt_row gt_left">

Mushroom Growing

</td>

</tr>

<tr>

<td class="gt_row gt_left">

A0122

</td>

<td class="gt_row gt_left">

Vegetable Growing (Under Cover)

</td>

</tr>

<tr>

<td class="gt_row gt_left">

A0123

</td>

<td class="gt_row gt_left">

Vegetable Growing (Outdoors)

</td>

</tr>

<tr>

<td class="gt_row gt_left">

A0131

</td>

<td class="gt_row gt_left">

Grape Growing

</td>

</tr>

<tr>

<td class="gt_row gt_left">

A0132

</td>

<td class="gt_row gt_left">

Kiwifruit Growing

</td>

</tr>

</tbody>

</table>

</div>

<!--/html_preserve-->

``` r
anzsoc <-
  readxl::read_xlsx(path = "data/raw-data/ANZSCO.xlsx", sheet = "Table 5", skip = 5, col_names = FALSE) %>%
  janitor::clean_names() %>%
  setDT(.)
#> New names:
#> * `` -> ...1
#> * `` -> ...2
#> * `` -> ...3
#> * `` -> ...4
#> * `` -> ...5
#> * ...
  # setnames(c("major_code","major_group", "submajor_group", "minor_group", "unit_group", "occupation", "skill_level"))

anzsoc_major <-
  anzsoc %>%
  .[!is.na(x1) & !is.na(x2)] %>%
  janitor::remove_empty(., which = "cols") %>%
  setnames(c("major_code", "major_group"))

gt(head(anzsoc_major, 10)) %>%
  tab_header(
    title = "ANZSOC 2013 - Major group"
  )
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#hbwnmqefch .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#hbwnmqefch .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#hbwnmqefch .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#hbwnmqefch .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#hbwnmqefch .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#hbwnmqefch .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#hbwnmqefch .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#hbwnmqefch .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#hbwnmqefch .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#hbwnmqefch .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#hbwnmqefch .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#hbwnmqefch .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#hbwnmqefch .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#hbwnmqefch .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#hbwnmqefch .gt_from_md > :first-child {
  margin-top: 0;
}

#hbwnmqefch .gt_from_md > :last-child {
  margin-bottom: 0;
}

#hbwnmqefch .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#hbwnmqefch .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#hbwnmqefch .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#hbwnmqefch .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#hbwnmqefch .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#hbwnmqefch .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#hbwnmqefch .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#hbwnmqefch .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#hbwnmqefch .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#hbwnmqefch .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#hbwnmqefch .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#hbwnmqefch .gt_left {
  text-align: left;
}

#hbwnmqefch .gt_center {
  text-align: center;
}

#hbwnmqefch .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#hbwnmqefch .gt_font_normal {
  font-weight: normal;
}

#hbwnmqefch .gt_font_bold {
  font-weight: bold;
}

#hbwnmqefch .gt_font_italic {
  font-style: italic;
}

#hbwnmqefch .gt_super {
  font-size: 65%;
}

#hbwnmqefch .gt_footnote_marks {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="hbwnmqefch" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">

<table class="gt_table">

<thead class="gt_header">

<tr>

<th colspan="2" class="gt_heading gt_title gt_font_normal" style>

ANZSOC 2013 - Major group

</th>

</tr>

<tr>

<th colspan="2" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>

</th>

</tr>

</thead>

<thead class="gt_col_headings">

<tr>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

major\_code

</th>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

major\_group

</th>

</tr>

</thead>

<tbody class="gt_table_body">

<tr>

<td class="gt_row gt_left">

1

</td>

<td class="gt_row gt_left">

MANAGERS

</td>

</tr>

<tr>

<td class="gt_row gt_left">

2

</td>

<td class="gt_row gt_left">

PROFESSIONALS

</td>

</tr>

<tr>

<td class="gt_row gt_left">

3

</td>

<td class="gt_row gt_left">

TECHNICIANS AND TRADES WORKERS

</td>

</tr>

<tr>

<td class="gt_row gt_left">

4

</td>

<td class="gt_row gt_left">

COMMUNITY AND PERSONAL SERVICE WORKERS

</td>

</tr>

<tr>

<td class="gt_row gt_left">

5

</td>

<td class="gt_row gt_left">

CLERICAL AND ADMINISTRATIVE WORKERS

</td>

</tr>

<tr>

<td class="gt_row gt_left">

6

</td>

<td class="gt_row gt_left">

SALES WORKERS

</td>

</tr>

<tr>

<td class="gt_row gt_left">

7

</td>

<td class="gt_row gt_left">

MACHINERY OPERATORS AND DRIVERS

</td>

</tr>

<tr>

<td class="gt_row gt_left">

8

</td>

<td class="gt_row gt_left">

LABOURERS

</td>

</tr>

</tbody>

</table>

</div>

<!--/html_preserve-->

``` r

anzsoc_submajor <-
  anzsoc %>%
  .[!is.na(x2) & !is.na(x3)] %>%
  janitor::remove_empty(., which = "cols") %>%
  setnames(c("submajor_code", "submajor_group"))

gt(head(anzsoc_submajor, 10)) %>%
  tab_header(
    title = "ANZSOC 2013 - Submajor group"
  )
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#hslenvqvlk .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#hslenvqvlk .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#hslenvqvlk .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#hslenvqvlk .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#hslenvqvlk .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#hslenvqvlk .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#hslenvqvlk .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#hslenvqvlk .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#hslenvqvlk .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#hslenvqvlk .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#hslenvqvlk .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#hslenvqvlk .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#hslenvqvlk .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#hslenvqvlk .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#hslenvqvlk .gt_from_md > :first-child {
  margin-top: 0;
}

#hslenvqvlk .gt_from_md > :last-child {
  margin-bottom: 0;
}

#hslenvqvlk .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#hslenvqvlk .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#hslenvqvlk .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#hslenvqvlk .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#hslenvqvlk .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#hslenvqvlk .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#hslenvqvlk .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#hslenvqvlk .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#hslenvqvlk .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#hslenvqvlk .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#hslenvqvlk .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#hslenvqvlk .gt_left {
  text-align: left;
}

#hslenvqvlk .gt_center {
  text-align: center;
}

#hslenvqvlk .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#hslenvqvlk .gt_font_normal {
  font-weight: normal;
}

#hslenvqvlk .gt_font_bold {
  font-weight: bold;
}

#hslenvqvlk .gt_font_italic {
  font-style: italic;
}

#hslenvqvlk .gt_super {
  font-size: 65%;
}

#hslenvqvlk .gt_footnote_marks {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="hslenvqvlk" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">

<table class="gt_table">

<thead class="gt_header">

<tr>

<th colspan="2" class="gt_heading gt_title gt_font_normal" style>

ANZSOC 2013 - Submajor group

</th>

</tr>

<tr>

<th colspan="2" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>

</th>

</tr>

</thead>

<thead class="gt_col_headings">

<tr>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

submajor\_code

</th>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

submajor\_group

</th>

</tr>

</thead>

<tbody class="gt_table_body">

<tr>

<td class="gt_row gt_left">

11

</td>

<td class="gt_row gt_left">

Chief Executives, General Managers and Legislators

</td>

</tr>

<tr>

<td class="gt_row gt_left">

12

</td>

<td class="gt_row gt_left">

Farmers and Farm Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

13

</td>

<td class="gt_row gt_left">

Specialist Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

14

</td>

<td class="gt_row gt_left">

Hospitality, Retail and Service Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

21

</td>

<td class="gt_row gt_left">

Arts and Media Professionals

</td>

</tr>

<tr>

<td class="gt_row gt_left">

22

</td>

<td class="gt_row gt_left">

Business, Human Resource and Marketing Professionals

</td>

</tr>

<tr>

<td class="gt_row gt_left">

23

</td>

<td class="gt_row gt_left">

Design, Engineering, Science and Transport Professionals

</td>

</tr>

<tr>

<td class="gt_row gt_left">

24

</td>

<td class="gt_row gt_left">

Education Professionals

</td>

</tr>

<tr>

<td class="gt_row gt_left">

25

</td>

<td class="gt_row gt_left">

Health Professionals

</td>

</tr>

<tr>

<td class="gt_row gt_left">

26

</td>

<td class="gt_row gt_left">

ICT Professionals

</td>

</tr>

</tbody>

</table>

</div>

<!--/html_preserve-->

``` r

anzsoc_minor <-
  anzsoc %>%
  .[!is.na(x3) & !is.na(x4)] %>% 
  janitor::remove_empty(., which = "cols") %>%
  setnames(c("minor_code", "minor_group"))

gt(head(anzsoc_minor, 10)) %>%
  tab_header(
    title = "ANZSOC 2013 - Minor group"
  )
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#fyrtxxkrdi .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#fyrtxxkrdi .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#fyrtxxkrdi .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#fyrtxxkrdi .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#fyrtxxkrdi .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#fyrtxxkrdi .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#fyrtxxkrdi .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#fyrtxxkrdi .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#fyrtxxkrdi .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#fyrtxxkrdi .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#fyrtxxkrdi .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#fyrtxxkrdi .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#fyrtxxkrdi .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#fyrtxxkrdi .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#fyrtxxkrdi .gt_from_md > :first-child {
  margin-top: 0;
}

#fyrtxxkrdi .gt_from_md > :last-child {
  margin-bottom: 0;
}

#fyrtxxkrdi .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#fyrtxxkrdi .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#fyrtxxkrdi .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#fyrtxxkrdi .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#fyrtxxkrdi .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#fyrtxxkrdi .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#fyrtxxkrdi .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#fyrtxxkrdi .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#fyrtxxkrdi .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#fyrtxxkrdi .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#fyrtxxkrdi .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#fyrtxxkrdi .gt_left {
  text-align: left;
}

#fyrtxxkrdi .gt_center {
  text-align: center;
}

#fyrtxxkrdi .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#fyrtxxkrdi .gt_font_normal {
  font-weight: normal;
}

#fyrtxxkrdi .gt_font_bold {
  font-weight: bold;
}

#fyrtxxkrdi .gt_font_italic {
  font-style: italic;
}

#fyrtxxkrdi .gt_super {
  font-size: 65%;
}

#fyrtxxkrdi .gt_footnote_marks {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="fyrtxxkrdi" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">

<table class="gt_table">

<thead class="gt_header">

<tr>

<th colspan="2" class="gt_heading gt_title gt_font_normal" style>

ANZSOC 2013 - Minor group

</th>

</tr>

<tr>

<th colspan="2" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>

</th>

</tr>

</thead>

<thead class="gt_col_headings">

<tr>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

minor\_code

</th>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

minor\_group

</th>

</tr>

</thead>

<tbody class="gt_table_body">

<tr>

<td class="gt_row gt_left">

111

</td>

<td class="gt_row gt_left">

Chief Executives, General Managers and Legislators

</td>

</tr>

<tr>

<td class="gt_row gt_left">

121

</td>

<td class="gt_row gt_left">

Farmers and Farm Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

131

</td>

<td class="gt_row gt_left">

Advertising, Public Relations and Sales Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

132

</td>

<td class="gt_row gt_left">

Business Administration Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

133

</td>

<td class="gt_row gt_left">

Construction, Distribution and Production Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

134

</td>

<td class="gt_row gt_left">

Education, Health and Welfare Services Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

135

</td>

<td class="gt_row gt_left">

ICT Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

139

</td>

<td class="gt_row gt_left">

Miscellaneous Specialist Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

141

</td>

<td class="gt_row gt_left">

Accommodation and Hospitality Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

142

</td>

<td class="gt_row gt_left">

Retail Managers

</td>

</tr>

</tbody>

</table>

</div>

<!--/html_preserve-->

``` r

anzsoc_unit <-
  anzsoc %>%
  .[!is.na(x4) & !is.na(x5)] %>%
  janitor::remove_empty(., which = "cols") %>%
  setnames(c("unit_code", "unit_group"))

gt(head(anzsoc_unit, 10)) %>%
  tab_header(
    title = "ANZSOC 2013 - Unit group"
  )
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#anzudlrbzw .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#anzudlrbzw .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#anzudlrbzw .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#anzudlrbzw .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#anzudlrbzw .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#anzudlrbzw .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#anzudlrbzw .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#anzudlrbzw .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#anzudlrbzw .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#anzudlrbzw .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#anzudlrbzw .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#anzudlrbzw .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#anzudlrbzw .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#anzudlrbzw .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#anzudlrbzw .gt_from_md > :first-child {
  margin-top: 0;
}

#anzudlrbzw .gt_from_md > :last-child {
  margin-bottom: 0;
}

#anzudlrbzw .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#anzudlrbzw .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#anzudlrbzw .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#anzudlrbzw .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#anzudlrbzw .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#anzudlrbzw .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#anzudlrbzw .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#anzudlrbzw .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#anzudlrbzw .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#anzudlrbzw .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#anzudlrbzw .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#anzudlrbzw .gt_left {
  text-align: left;
}

#anzudlrbzw .gt_center {
  text-align: center;
}

#anzudlrbzw .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#anzudlrbzw .gt_font_normal {
  font-weight: normal;
}

#anzudlrbzw .gt_font_bold {
  font-weight: bold;
}

#anzudlrbzw .gt_font_italic {
  font-style: italic;
}

#anzudlrbzw .gt_super {
  font-size: 65%;
}

#anzudlrbzw .gt_footnote_marks {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="anzudlrbzw" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">

<table class="gt_table">

<thead class="gt_header">

<tr>

<th colspan="2" class="gt_heading gt_title gt_font_normal" style>

ANZSOC 2013 - Unit group

</th>

</tr>

<tr>

<th colspan="2" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>

</th>

</tr>

</thead>

<thead class="gt_col_headings">

<tr>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

unit\_code

</th>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

unit\_group

</th>

</tr>

</thead>

<tbody class="gt_table_body">

<tr>

<td class="gt_row gt_left">

1111

</td>

<td class="gt_row gt_left">

Chief Executives and Managing Directors

</td>

</tr>

<tr>

<td class="gt_row gt_left">

1112

</td>

<td class="gt_row gt_left">

General Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

1113

</td>

<td class="gt_row gt_left">

Legislators

</td>

</tr>

<tr>

<td class="gt_row gt_left">

1211

</td>

<td class="gt_row gt_left">

Aquaculture Farmers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

1212

</td>

<td class="gt_row gt_left">

Crop Farmers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

1213

</td>

<td class="gt_row gt_left">

Livestock Farmers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

1214

</td>

<td class="gt_row gt_left">

Mixed Crop and Livestock Farmers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

1311

</td>

<td class="gt_row gt_left">

Advertising, Public Relations and Sales Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

1321

</td>

<td class="gt_row gt_left">

Corporate Services Managers

</td>

</tr>

<tr>

<td class="gt_row gt_left">

1322

</td>

<td class="gt_row gt_left">

Finance Managers

</td>

</tr>

</tbody>

</table>

</div>

<!--/html_preserve-->

``` r

anzsoc_occupation <-
  anzsoc %>%
  .[!is.na(x5) & !is.na(x6)] %>% 
  janitor::remove_empty(., which = "cols") %>% 
  setnames(c("occupation_code", "occupation_group", "skill_level"))

gt(head(anzsoc_occupation, 10)) %>%
  tab_header(
    title = "ANZSOC 2013 - Occupation"
  )
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#ztzzxwqanl .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#ztzzxwqanl .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#ztzzxwqanl .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#ztzzxwqanl .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#ztzzxwqanl .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#ztzzxwqanl .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#ztzzxwqanl .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#ztzzxwqanl .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#ztzzxwqanl .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#ztzzxwqanl .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#ztzzxwqanl .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#ztzzxwqanl .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#ztzzxwqanl .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#ztzzxwqanl .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#ztzzxwqanl .gt_from_md > :first-child {
  margin-top: 0;
}

#ztzzxwqanl .gt_from_md > :last-child {
  margin-bottom: 0;
}

#ztzzxwqanl .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#ztzzxwqanl .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#ztzzxwqanl .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#ztzzxwqanl .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#ztzzxwqanl .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#ztzzxwqanl .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#ztzzxwqanl .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#ztzzxwqanl .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#ztzzxwqanl .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#ztzzxwqanl .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#ztzzxwqanl .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#ztzzxwqanl .gt_left {
  text-align: left;
}

#ztzzxwqanl .gt_center {
  text-align: center;
}

#ztzzxwqanl .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#ztzzxwqanl .gt_font_normal {
  font-weight: normal;
}

#ztzzxwqanl .gt_font_bold {
  font-weight: bold;
}

#ztzzxwqanl .gt_font_italic {
  font-style: italic;
}

#ztzzxwqanl .gt_super {
  font-size: 65%;
}

#ztzzxwqanl .gt_footnote_marks {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="ztzzxwqanl" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">

<table class="gt_table">

<thead class="gt_header">

<tr>

<th colspan="3" class="gt_heading gt_title gt_font_normal" style>

ANZSOC 2013 - Occupation

</th>

</tr>

<tr>

<th colspan="3" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>

</th>

</tr>

</thead>

<thead class="gt_col_headings">

<tr>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

occupation\_code

</th>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

occupation\_group

</th>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

skill\_level

</th>

</tr>

</thead>

<tbody class="gt_table_body">

<tr>

<td class="gt_row gt_left">

111111

</td>

<td class="gt_row gt_left">

Chief Executive or Managing Director

</td>

<td class="gt_row gt_left">

1

</td>

</tr>

<tr>

<td class="gt_row gt_left">

111211

</td>

<td class="gt_row gt_left">

Corporate General Manager

</td>

<td class="gt_row gt_left">

1

</td>

</tr>

<tr>

<td class="gt_row gt_left">

111212

</td>

<td class="gt_row gt_left">

Defence Force Senior Officer

</td>

<td class="gt_row gt_left">

1

</td>

</tr>

<tr>

<td class="gt_row gt_left">

111311

</td>

<td class="gt_row gt_left">

Local Government Legislator

</td>

<td class="gt_row gt_left">

1

</td>

</tr>

<tr>

<td class="gt_row gt_left">

111312

</td>

<td class="gt_row gt_left">

Member of Parliament

</td>

<td class="gt_row gt_left">

1

</td>

</tr>

<tr>

<td class="gt_row gt_left">

111399

</td>

<td class="gt_row gt_left">

Legislators nec

</td>

<td class="gt_row gt_left">

1

</td>

</tr>

<tr>

<td class="gt_row gt_left">

121111

</td>

<td class="gt_row gt_left">

Aquaculture Farmer

</td>

<td class="gt_row gt_left">

1

</td>

</tr>

<tr>

<td class="gt_row gt_left">

121211

</td>

<td class="gt_row gt_left">

Cotton Grower

</td>

<td class="gt_row gt_left">

1

</td>

</tr>

<tr>

<td class="gt_row gt_left">

121212

</td>

<td class="gt_row gt_left">

Flower Grower

</td>

<td class="gt_row gt_left">

1

</td>

</tr>

<tr>

<td class="gt_row gt_left">

121213

</td>

<td class="gt_row gt_left">

Fruit or Nut Grower

</td>

<td class="gt_row gt_left">

1

</td>

</tr>

</tbody>

</table>

</div>

<!--/html_preserve-->
