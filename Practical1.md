Practical 1 - Data Science
================
Elisa Simon
19 04 2022

# Alcohol consumption in Switzerland and neigborhood between 1960 and 2014

In this report, I am interested in **alcohol consumption in Switzerland
and neigborhood between 1960 and 2014**. The five countries of interest
are the following:

-   Austria
-   France
-   Germany
-   Italy
-   Switzerland

*The dataset I used is from Holmes & Anderson (2017) and can be
downloaded from the website
[OurWorldinData](https://ourworldindata.org/alcohol-consumption), in the
section “Total alcohol consumption over the long run.”*

``` r
# Because the variables names were quite strange and included symbols R doesn't like, I had to clean a little. To do this I have notably used the clean_names() function which requires to load the janitor library.

library(janitor)
df_clean <- clean_names(per_capita_alcohol_1890)
df <- df_clean %>% dplyr::rename(alcohol_consumption = alcohol_consumption_since_1890_alexander_holmes_2017)

# because the dataset contains other countries (and years) than those I am interested in, I have to do some data preparation - in order to have an easy access to the pertinent data only. Here's how I went:

d <- df %>%
  filter(entity %in% c("Austria", "France", "Germany", "Italy", "Switzerland"),
         year >= "1960",
         year <= "2014")
```

## Evolution of alcohol consumption in Switzerland and neigborhood

If we look at the graph below, we can observe that the alcohol
consumption has decreased in each countries, except in Austria.

![](Practical1_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

### Ranking of countries depending on their alcohol consumption in 1960

1.  France
2.  Italy
3.  Germany & Switzerland
4.  Austria

### Ranking of countries depending on their alcohol consumption in 2014

1.  Austria
2.  Germany
3.  France
4.  Switzerland
5.  Italy

## Alcohol consumption in each country (average from 1960 to 2014)

The graph below show that, in average, French people tend to drink more
alcohol (on average) than the ones living in Austria, Germany, Italy,
and Switzerland. Even if - as we saw above - the tendance is decreasing.

![](Practical1_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

# Conclusion

![Austria, the country where people tend to ~~be alcoholic~~ drink more
and more over
years](https://www.coe.int/documents/16695/61254353/ECRI-vienna-news-june-2020.jpg/64b94a41-d8dd-5f48-16b5-caaa4d260f49?t=1591084794000)

## Alcohol consumption evolution

Globally, we can observe a tendency of decrease in alcohol consumption
in Switzerland and neighborhood, except in Austria where people drink
1.7 supplementary liter of alcohol in 2014 than in 1960. The greatest
decrease is found in France, where people drink 8.5 liters of alcohol
less than in 1960.

## Alcohol consumption nowadays (well, in 2014)

Despite France is overall the country where people have drank the more
alcohol since 1960, the huge increase of alcohol consumption in Austria
makes it the contry where people have drank the more alcohol in 2014,
with in average 10.4 liters of alcohol per person.

# Bibliography

<div id="refs" class="references csl-bib-body hanging-indent"
line-spacing="2">

<div id="ref-holmes_convergence_2017" class="csl-entry">

Holmes, A. J., & Anderson, K. (2017). Convergence in National Alcohol
Consumption Patterns: New Global Indicators. *Journal of Wine
Economics*, *12*(2), 117–148. <https://doi.org/10.1017/jwe.2017.15>

</div>

</div>
