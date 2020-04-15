
<!-- README.md is generated from README.Rmd. Please edit that file -->

# australias-essential-workers

<!-- badges: start -->

<!-- badges: end -->

The goal of this repository is to identify essential workers by their
ANZSIC and ANZSCO codes. Pull requests are welcome.

# Data sources

The original data sources of the spreadsheets in ‘data’ folder are as
stated below.

  - ANZSIC:
    <https://www.fwc.gov.au/awards-and-agreements/minimum-wages-conditions/annual-wage-reviews/previous-wage-reviews/annual-wa-0>
  - ANZSCO:
    <https://www.abs.gov.au/AUSSTATS/abs@.nsf/DetailsPage/1220.02013,%20Version%201.3?OpenDocument>

# References

  - <https://www.theaustralian.com.au/world/coronavirus-the-essential-workers-wholl-keep-australia-ticking-along/news-story/cb7992b6ae722afd0838f17e61338e01>
  - <https://en.wikipedia.org/wiki/Essential_services>
  - <https://www.betterteam.com/what-is-an-essential-worker-in-australia>

# ANZSIC

<table>

<caption>

ANZSIC 2006 divisions

</caption>

<thead>

<tr>

<th style="text-align:left;">

anzsic\_division

</th>

<th style="text-align:left;">

anzsic\_division\_title

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

A

</td>

<td style="text-align:left;">

Agriculture, Forestry and Fishing

</td>

</tr>

<tr>

<td style="text-align:left;">

B

</td>

<td style="text-align:left;">

Mining

</td>

</tr>

<tr>

<td style="text-align:left;">

C

</td>

<td style="text-align:left;">

Manufacturing

</td>

</tr>

<tr>

<td style="text-align:left;">

D

</td>

<td style="text-align:left;">

Electricity, Gas, Water and Waste Services

</td>

</tr>

<tr>

<td style="text-align:left;">

E

</td>

<td style="text-align:left;">

Construction

</td>

</tr>

<tr>

<td style="text-align:left;">

F

</td>

<td style="text-align:left;">

Wholesale Trade

</td>

</tr>

<tr>

<td style="text-align:left;">

G

</td>

<td style="text-align:left;">

Retail Trade

</td>

</tr>

<tr>

<td style="text-align:left;">

H

</td>

<td style="text-align:left;">

Accommodation and Food Services

</td>

</tr>

<tr>

<td style="text-align:left;">

I

</td>

<td style="text-align:left;">

Transport, Postal and Warehousing

</td>

</tr>

<tr>

<td style="text-align:left;">

J

</td>

<td style="text-align:left;">

Information Media and Telecommunications

</td>

</tr>

<tr>

<td style="text-align:left;">

K

</td>

<td style="text-align:left;">

Financial and Insurance Services

</td>

</tr>

<tr>

<td style="text-align:left;">

L

</td>

<td style="text-align:left;">

Rental, Hiring and Real Estate Services

</td>

</tr>

<tr>

<td style="text-align:left;">

M

</td>

<td style="text-align:left;">

Professional, Scientific and Technical Services

</td>

</tr>

<tr>

<td style="text-align:left;">

N

</td>

<td style="text-align:left;">

Administrative and Support Services

</td>

</tr>

<tr>

<td style="text-align:left;">

O

</td>

<td style="text-align:left;">

Public Administration and Safety

</td>

</tr>

<tr>

<td style="text-align:left;">

P

</td>

<td style="text-align:left;">

Education and Training

</td>

</tr>

<tr>

<td style="text-align:left;">

Q

</td>

<td style="text-align:left;">

Health Care and Social Assistance

</td>

</tr>

<tr>

<td style="text-align:left;">

R

</td>

<td style="text-align:left;">

Arts and Recreation Services

</td>

</tr>

<tr>

<td style="text-align:left;">

S

</td>

<td style="text-align:left;">

Other Services

</td>

</tr>

</tbody>

</table>

<table>

<caption>

ANZSIC 2006 codes, first 10 rows only

</caption>

<thead>

<tr>

<th style="text-align:left;">

anzsic\_code

</th>

<th style="text-align:left;">

anzsic\_class\_title

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

A0111

</td>

<td style="text-align:left;">

Nursery Production (Under Cover)

</td>

</tr>

<tr>

<td style="text-align:left;">

A0112

</td>

<td style="text-align:left;">

Nursery Production (Outdoors)

</td>

</tr>

<tr>

<td style="text-align:left;">

A0113

</td>

<td style="text-align:left;">

Turf Growing

</td>

</tr>

<tr>

<td style="text-align:left;">

A0114

</td>

<td style="text-align:left;">

Floriculture Production (Under Cover)

</td>

</tr>

<tr>

<td style="text-align:left;">

A0115

</td>

<td style="text-align:left;">

Floriculture Production (Outdoors)

</td>

</tr>

<tr>

<td style="text-align:left;">

A0121

</td>

<td style="text-align:left;">

Mushroom Growing

</td>

</tr>

<tr>

<td style="text-align:left;">

A0122

</td>

<td style="text-align:left;">

Vegetable Growing (Under Cover)

</td>

</tr>

<tr>

<td style="text-align:left;">

A0123

</td>

<td style="text-align:left;">

Vegetable Growing (Outdoors)

</td>

</tr>

<tr>

<td style="text-align:left;">

A0131

</td>

<td style="text-align:left;">

Grape Growing

</td>

</tr>

<tr>

<td style="text-align:left;">

A0132

</td>

<td style="text-align:left;">

Kiwifruit Growing

</td>

</tr>

</tbody>

</table>

# ANZSOC

<table>

<caption>

ANZSOC 2013 - Major group

</caption>

<thead>

<tr>

<th style="text-align:left;">

major\_code

</th>

<th style="text-align:left;">

major\_group

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

1

</td>

<td style="text-align:left;">

MANAGERS

</td>

</tr>

<tr>

<td style="text-align:left;">

2

</td>

<td style="text-align:left;">

PROFESSIONALS

</td>

</tr>

<tr>

<td style="text-align:left;">

3

</td>

<td style="text-align:left;">

TECHNICIANS AND TRADES WORKERS

</td>

</tr>

<tr>

<td style="text-align:left;">

4

</td>

<td style="text-align:left;">

COMMUNITY AND PERSONAL SERVICE WORKERS

</td>

</tr>

<tr>

<td style="text-align:left;">

5

</td>

<td style="text-align:left;">

CLERICAL AND ADMINISTRATIVE WORKERS

</td>

</tr>

<tr>

<td style="text-align:left;">

6

</td>

<td style="text-align:left;">

SALES WORKERS

</td>

</tr>

<tr>

<td style="text-align:left;">

7

</td>

<td style="text-align:left;">

MACHINERY OPERATORS AND DRIVERS

</td>

</tr>

<tr>

<td style="text-align:left;">

8

</td>

<td style="text-align:left;">

LABOURERS

</td>

</tr>

</tbody>

</table>

<table>

<caption>

ANZSOC 2013 - Sub-major group, first 10 rows only

</caption>

<thead>

<tr>

<th style="text-align:left;">

submajor\_code

</th>

<th style="text-align:left;">

submajor\_group

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

11

</td>

<td style="text-align:left;">

Chief Executives, General Managers and Legislators

</td>

</tr>

<tr>

<td style="text-align:left;">

12

</td>

<td style="text-align:left;">

Farmers and Farm Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

13

</td>

<td style="text-align:left;">

Specialist Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

14

</td>

<td style="text-align:left;">

Hospitality, Retail and Service Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

21

</td>

<td style="text-align:left;">

Arts and Media Professionals

</td>

</tr>

<tr>

<td style="text-align:left;">

22

</td>

<td style="text-align:left;">

Business, Human Resource and Marketing Professionals

</td>

</tr>

<tr>

<td style="text-align:left;">

23

</td>

<td style="text-align:left;">

Design, Engineering, Science and Transport Professionals

</td>

</tr>

<tr>

<td style="text-align:left;">

24

</td>

<td style="text-align:left;">

Education Professionals

</td>

</tr>

<tr>

<td style="text-align:left;">

25

</td>

<td style="text-align:left;">

Health Professionals

</td>

</tr>

<tr>

<td style="text-align:left;">

26

</td>

<td style="text-align:left;">

ICT Professionals

</td>

</tr>

</tbody>

</table>

<table>

<caption>

ANZSOC 2013 - Minor group, first 10 rows only

</caption>

<thead>

<tr>

<th style="text-align:left;">

minor\_code

</th>

<th style="text-align:left;">

minor\_group

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

111

</td>

<td style="text-align:left;">

Chief Executives, General Managers and Legislators

</td>

</tr>

<tr>

<td style="text-align:left;">

121

</td>

<td style="text-align:left;">

Farmers and Farm Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

131

</td>

<td style="text-align:left;">

Advertising, Public Relations and Sales Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

132

</td>

<td style="text-align:left;">

Business Administration Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

133

</td>

<td style="text-align:left;">

Construction, Distribution and Production Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

134

</td>

<td style="text-align:left;">

Education, Health and Welfare Services Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

135

</td>

<td style="text-align:left;">

ICT Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

139

</td>

<td style="text-align:left;">

Miscellaneous Specialist Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

141

</td>

<td style="text-align:left;">

Accommodation and Hospitality Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

142

</td>

<td style="text-align:left;">

Retail Managers

</td>

</tr>

</tbody>

</table>

<table>

<caption>

ANZSOC 2013 - Unit group, first 10 rows only

</caption>

<thead>

<tr>

<th style="text-align:left;">

unit\_code

</th>

<th style="text-align:left;">

unit\_group

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

1111

</td>

<td style="text-align:left;">

Chief Executives and Managing Directors

</td>

</tr>

<tr>

<td style="text-align:left;">

1112

</td>

<td style="text-align:left;">

General Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

1113

</td>

<td style="text-align:left;">

Legislators

</td>

</tr>

<tr>

<td style="text-align:left;">

1211

</td>

<td style="text-align:left;">

Aquaculture Farmers

</td>

</tr>

<tr>

<td style="text-align:left;">

1212

</td>

<td style="text-align:left;">

Crop Farmers

</td>

</tr>

<tr>

<td style="text-align:left;">

1213

</td>

<td style="text-align:left;">

Livestock Farmers

</td>

</tr>

<tr>

<td style="text-align:left;">

1214

</td>

<td style="text-align:left;">

Mixed Crop and Livestock Farmers

</td>

</tr>

<tr>

<td style="text-align:left;">

1311

</td>

<td style="text-align:left;">

Advertising, Public Relations and Sales Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

1321

</td>

<td style="text-align:left;">

Corporate Services Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

1322

</td>

<td style="text-align:left;">

Finance Managers

</td>

</tr>

</tbody>

</table>

<table>

<caption>

ANZSOC 2013 - Occupation, first 10 rows only

</caption>

<thead>

<tr>

<th style="text-align:left;">

unit\_code

</th>

<th style="text-align:left;">

unit\_group

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

1111

</td>

<td style="text-align:left;">

Chief Executives and Managing Directors

</td>

</tr>

<tr>

<td style="text-align:left;">

1112

</td>

<td style="text-align:left;">

General Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

1113

</td>

<td style="text-align:left;">

Legislators

</td>

</tr>

<tr>

<td style="text-align:left;">

1211

</td>

<td style="text-align:left;">

Aquaculture Farmers

</td>

</tr>

<tr>

<td style="text-align:left;">

1212

</td>

<td style="text-align:left;">

Crop Farmers

</td>

</tr>

<tr>

<td style="text-align:left;">

1213

</td>

<td style="text-align:left;">

Livestock Farmers

</td>

</tr>

<tr>

<td style="text-align:left;">

1214

</td>

<td style="text-align:left;">

Mixed Crop and Livestock Farmers

</td>

</tr>

<tr>

<td style="text-align:left;">

1311

</td>

<td style="text-align:left;">

Advertising, Public Relations and Sales Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

1321

</td>

<td style="text-align:left;">

Corporate Services Managers

</td>

</tr>

<tr>

<td style="text-align:left;">

1322

</td>

<td style="text-align:left;">

Finance Managers

</td>

</tr>

</tbody>

</table>
