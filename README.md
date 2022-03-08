# FrenchIncomeGroupByCity

## 1. Data source:

We will use four files in this project. You can find the origin source file from [INSEE](https://www.insee.fr/fr/statistiques/1893274)

## 1.1 base_etablissement_par_tranche_effectif.csv

This file gives information on the number of firms in every French town, categorized by size.

Column info:
|name|description|
|----|-----------|
|CODGEO | geographic code for the town (can be joined with `code-insee` column from 'name_geographic_information.csv')|
|LIBGEO | name of the town (in French)|
|REG | region number|
|DEP | department number|
|E14TST | total number of firms in the town|
|E14TS0ND | number of unknown or null size firms in the town|
|E14TS1 | number of firms with 1 to 5 employees in the town|
|E14TS6 | number of firms with 6 to 9 employees in the town|
|E14TS10 | number of firms with 10 to 19 employees in the town|
|E14TS20 | number of firms with 20 to 49 employees in the town|
|E14TS50 | number of firms with 50 to 99 employees in the town|
|E14TS100 | number of firms with 100 to 199 employees in the town|
|E14TS200 | number of firms with 200 to 499 employees in the town|
|E14TS500 | number of firms with more than 500 employees in the town|

## 1.2 name_geographic_information.csv 

This file gives geographic coordinate on french town (mainly latitude and longitude, but also region / department codes and names )

EU_circo : name of the European Union Circonscription
code_région : code of the region attached to the town
nom_région : name of the region attached to the town
chef.lieu_région : name the administrative center around the town
numéro_département : code of the department attached to the town
nom_département : name of the department attached to the town
préfecture : name of the local administrative division around the town
numéro_circonscription : number of the circumpscription
nom_commune : name of the town
codes_postaux : post-codes relative to the town
code_insee : unique code for the town
latitude : GPS latitude
longitude : GPS longitude
éloignement : i couldn't manage to figure out what was the meaning of this number
netsalarypertownper_category : salaries around french town per job categories, age and sex

CODGEO : unique code of the town
LIBGEO : name of the town
SNHM14 : mean net salary
SNHMC14 : mean net salary per hour for executive
SNHMP14 : mean net salary per hour for middle manager
SNHME14 : mean net salary per hour for employee
SNHMO14 : mean net salary per hour for worker
SNHMF14 : mean net salary for women
SNHMFC14 : mean net salary per hour for feminin executive
SNHMFP14 : mean net salary per hour for feminin middle manager
SNHMFE14 : mean net salary per hour for feminin employee
SNHMFO14 : mean net salary per hour for feminin worker
SNHMH14 : mean net salary for man
SNHMHC14 : mean net salary per hour for masculin executive
SNHMHP14 : mean net salary per hour for masculin middle manager
SNHMHE14 : mean net salary per hour for masculin employee
SNHMHO14 : mean net salary per hour for masculin worker
SNHM1814 : mean net salary per hour for 18-25 years old
SNHM2614 : mean net salary per hour for 26-50 years old
SNHM5014 : mean net salary per hour for >50 years old
SNHMF1814 : mean net salary per hour for women between 18-25 years old
SNHMF2614 : mean net salary per hour for women between 26-50 years old
SNHMF5014 : mean net salary per hour for women >50 years old
SNHMH1814 : mean net salary per hour for men between 18-25 years old
SNHMH2614 : mean net salary per hour for men between 26-50 years old
SNHMH5014 : mean net salary per hour for men >50 years old
population : demographic information in France per town, age, sex and living mode

NIVGEO : geographic level (arrondissement, communes…)
CODGEO : unique code for the town
LIBGEO : name of the town (might contain some utf-8 errors, this information has better quality namegeographicinformation)
MOCO : cohabitation mode : [list and meaning available in Data description]
AGE80_17 : age category (slice of 5 years) | ex : 0 -> people between 0 and 4 years old
SEXE : sex, 1 for men | 2 for women
NB : Number of people in the category
These datasets can be merged by : CODGEO = code_insee