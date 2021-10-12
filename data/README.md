# data

Place data file(s) in this folder.

Then, include metadata about your dataset including information on provenance, codebook, etc.

The codebook for your data file(s) using the following format.

## name of data file

|variable         |description |
|:----------------|:-----------|
|variable1        | Description of variable 1 |
|variable2        | Description of variable 2 |
|variable3        | Description of variable 3 |
|...              | ... |

knit_by_pkgdown <- !is.null(knitr::opts_chunk$get("fig.retina"))
knitr::opts_chunk$set(
  warning = TRUE, # show warnings during codebook generation
  message = TRUE, # show messages during codebook generation
  error = TRUE, # do not interrupt codebook generation in case of errors,
                # TRUE is usually better for debugging
  echo = TRUE  # show R code
)
ggplot2::theme_set(ggplot2::theme_bw())


hdi_overview <- rio::import("http://hdr.undp.org/sites/default/files/2020_statistical_annex_all.xlsx", "xlsx")

hdi1 <- rio::import("http://hdr.undp.org/sites/default/files/2020_statistical_annex_table_1.xlsx", "xlsx")

## hdi1

|variable         |description |
|:----------------|:-----------|
|country        | These are the countries that data was collected for the HDI.  |
|human development index (hdi)        | An overall "ranking" weighted on a compliation of various factors |
|gross national income (GNI) per capita        | The Gross National Income (GNI) is a key economic indicator of a country's wealth. This variable divides GNI into per capita measures|
|life expectancy at birth        | The expected life expectancy of an individual at birth in years  |

hdi4 <- rio::import("http://hdr.undp.org/sites/default/files/2020_statistical_annex_table_4.xlsx", "xlsx")

## hdi4

|variable         |description |
|:----------------|:-----------|
|life expectancy at birth by gender        | The expected life expectancy of an individual at birth in years, separated into male and female genders  |
|expected years of schooling by gender        | The expected years of schooling of an individual at birth in years, separated into male and female genders  |

hdi5 <- rio::import("http://hdr.undp.org/sites/default/files/2020_statistical_annex_table_5.xlsx", "xlsx")

## hdi5

|variable         |description |
|:----------------|:-----------|
|gender inequality index        | An index that measures inequalities among the factors of reproductive health, empowerment, and economic status. |
|maternal mortality ratio        | The number of maternal deaths per 100,000 live births |
|adolescent birth rate        | The number of births per 1,000 for women between the ages of 15-19 |
|population with at least some secondary education        | The percentage of individuals age 25 and older that have some secondary education, separated into male and female genders |
|labour force participation rate        | The percentage of individuals age 15 and older that have employment experience, separated into male and female genders  |

contraceptives <- rio::import("https://api.worldbank.org/v2/en/indicator/SP.DYN.CONU.ZS?downloadformat=excel", "xlsx")

## contraceptives

|variable         |description |
|:----------------|:-----------|
|contraceptive prevalence, any methods (% of women ages 15-49)     | The percentage of women ages 15-49 that use at least one method of contraceptives  |

adolescent_births <- read.csv("33e0e815-c117-40af-85f4-6443a33f276a.csv")

## adolescent_births

|variable         |description |
|:----------------|:-----------|
|indicator        | The number of births per 1,000 for women between the ages of 15-19 |
|period        | The years that observations were collected, from 2000-2019 |

#The two dataframes above are having trouble being imported since they do not have an external link to reference back to.


