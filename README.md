PS07 Michel Ruiz-Fuentes
================

<figure>
<img src="https://www.townofgb.org/sites/g/files/vyhlif636/f/styles/news_image_teaser/public/news/dubois-interior1-1540x1026_1.jpg?itok=75EiDw5S" style="width:85.0%" alt="“Figure 1. (2019). [Du Bois Legacy Committee Seeks Nominations for Second W.E.B. Du Bois Legacy Award] [Digital Art]. Great Barrington Massachussetts. https://www.townofgb.org/home/news/du-bois-legacy-committee-seeks-nominations-second-web-du-bois-legacy-award”" /><figcaption aria-hidden="true">“Figure 1. (2019). [Du Bois Legacy Committee Seeks Nominations for Second W.E.B. Du Bois Legacy Award] [Digital Art]. Great Barrington Massachussetts. <a href="https://www.townofgb.org/home/news/du-bois-legacy-committee-seeks-nominations-second-web-du-bois-legacy-award" class="uri">https://www.townofgb.org/home/news/du-bois-legacy-committee-seeks-nominations-second-web-du-bois-legacy-award</a>”</figcaption>
</figure>

## Inspired by W.E.B Du Bois’ Legacy to Data Viz

Last year, I was enrolled in a statistics course named “Communicating
with Data”. I had an exciting experience learning how I can apply my
**passion for civic engagement, creativity, and problem-solving** in the
Statistics and Data Science department at Smith. We had several engaging
units, but our focus on accessibility was one of my favorites. In this
unit, we explored the importance of making data accessible for people of
all backgrounds. For example, we discussed designing colorblind-friendly
data visualizations by using inclusive color palettes.

This unit inspired me to search for more literature about this subject
of **equity and accessibility in data visualizations**. I found the book
“W.E.B. Du Bois’ Data Portraits: Visualizing Black America” which
includes map, graphs and charts that DuBois and a team of black
sociologist used to illustrate the experiences of black Americans from
1790-1870. Ever since I discovered the data visualization contributions
of DuBois and his team, I have been fascinated in using this tool to
address agendas that relate to social good. In probleset 07, I will
pursue this by engaging in the \#DuBoisChallenge.

## Where is the Data From

The data I am using, **W.E.B Du Bois Challenge** (published 02-16-2021),
is from TidyTuesday. The challenge came from Anthony Starks in his
article, [Recreating W.E.B Du Bois’s Data
Portraits](https://medium.com/nightingale/recreating-w-e-b-du-boiss-data-portraits-87dd36096f34).
As he describes it, the goal of the \#DuBoisChallenge is to “celebrate
the data visualization legacy of W.E.B DuBois by recreating the
visualizations from the 1900 Paris Exposition using modern tools.”

## Loading necessary package and csv files from TidyTuesday

``` r
#loading necessary packages
library(ggplot2)
library(knitr)
```

occupation.csv (Occupation by race)

``` r
occupation <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2021/2021-02-16/occupation.csv')
```

city\_rural.csv (Black population split between city and rural areas)

``` r
city_rural <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2021/2021-02-16/city_rural.csv')
```


## Modern Data Vizualization on Occupations

``` r
ggplot(data = occupation, mapping = aes(x=Percentage, y= Occupation, fill= Group)) + 
  geom_col() + labs(title= "Occupations Between Black and White Population",
  subtitle= "Data Collected in Georgia from 1790s to 1870s",
  fill= "Racial Groups") + 
  xlab("Percentage") + ylab("Occupation Type") +
  scale_fill_manual(values = c("salmon4", "bisque1"))
```

![](README_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

## Modern Data Visualization on City-Rural Residency

``` r
ggplot(data = city_rural, mapping = aes(x=Category, y= Population, fill= Category)) + 
  geom_col() + labs(title= "Where Did Black Americans Reside in the 1890s?",
  subtitle= "Population in City versus Rural Areas") + 
  xlab("Georgraphic Classification") + ylab("Population Amount") +
  theme(axis.text.x = element_text(angle = 20, hjust=1)) +
  scale_fill_manual(values = c("deepskyblue3","lightpink3", "seagreen3", "hotpink4")) 
```

![](README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

## Conclusions

He concluded that this experience to recreate the visualizations,
“taught me \[him\] to boldly use color, to provide focus with bold,
simple visuals, to using data to tell compelling stories, and not to be
afraid to shape your tools and materials to your own will. I’m \[He is\]
inspired by them as a develop my own tools in the twenty-first century
and hope they can also be used to inspire and motivate.” I seek to have
the same impact in PS07 and other visualizations I create in the future.

## Acknowledgements

I want to thank Professor Kim, Professor Poirier, and Professor Kinnaird
for their support in building my data analysis skills!

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
