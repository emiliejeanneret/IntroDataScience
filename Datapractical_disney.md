Disney movies, a money question
================
Jeanneret Emilie
2022-11-23

<div align="center">

<img src="pexels-benjamin-suter-2362002.jpg" style="width:30.0%" />

<div align="left">

# Introduction

Have you ever seen a Disney movie ? I am sure that you cannot respond
“no” to that question. If you really never have seen one, I bet that you
know the worldwide famous mouse (of course I am speaking of Mickey
Mouse).

![](giphy.gif)

And this is because [The Walt Disney
Company](https://fr.wikipedia.org/wiki/The_Walt_Disney_Company) is,
since 2012, the first group of entertainment across the world ! Now
talking a little bit about the history of this company, we know that is
has been created in 1923 (100 years next year ! **woaw**). The founders
are Roy and Walter Disney, but the latter is the main character in the
Disney history.

They create many types of movie and you can easily find your way through
it. Indeed, it’s adapted to the whole family. The number of movies they
produced is about *529*, that is huge ! [The
list](https://www.imdb.com/list/ls033609554/) of all movie would take
quite a lot of time to go through but the main element we are interested
in in this research are the income of each movie, and the genre of each
movie.

## Research question

This research is interested in the evolution of incomings of Disney
movies through time. We also want to see is there is an impact of the
genre of movie on the income they engender. Of course, we will need to
adapt the table with inflation rate in order to adapt our data. The main
question here is **Is there an impact of the genre of Disney movies
incomings over time ?**

## Hypothesis

<div align="center">

N0: There is no impact of the genre on the incoming

<div align="center">

N1: There is an impact of the genre on the incoming

<div align="left">

# Data

The data comes from [kaggle](https://www.kaggle.com), where was hidden a
[very interesting
dataset](https://www.kaggle.com/datasets/prateekmaj21/disney-movies)
about disney movies. For this research, we do not need every details and
every lines, even if that would be very interesting to analyze.

As we can see in the following chunck, the main table is displaying in
the following way :

``` r
head(df)
```

    ##                       movie_title release_month release_date     genre
    ## 1 Snow White and the Seven Dwarfs      December Dec 21, 1937   Musical
    ## 2                       Pinocchio      February  Feb 9, 1940 Adventure
    ## 3                        Fantasia      November Nov 13, 1940   Musical
    ## 4               Song of the South      November Nov 12, 1946 Adventure
    ## 5                      Cinderella      February Feb 15, 1950     Drama
    ## 6    20,000 Leagues Under the Sea      December Dec 23, 1954 Adventure
    ##   MPAA_rating  total_gross inflation_adjusted_gross
    ## 1           G $184,925,485           $5,228,953,251
    ## 2           G  $84,300,000           $2,188,229,052
    ## 3           G  $83,320,000           $2,187,090,808
    ## 4           G  $65,000,000           $1,078,510,579
    ## 5           G  $85,000,000             $920,608,730
    ## 6              $28,200,000             $528,279,994

``` r
nrow(df)
```

    ## [1] 579

Here, the only columns that we are interested in are the movie title
(obviously), the release date (which includes month, day and year), the
genre and the gross (as well as the inflation adjusted gross in order to
compare (up to date) movies). There is 579 rows, each corresponding to
one country.

# Analysis

The first thing we want to look at in this analysis is about the genre.
How many movies from each genre is in our dataset ?

``` r
library(tidyr)
df_clean <- df[!df$genre=="",]
library(ggplot2)
library(dplyr)
df_clean <- within(df_clean, 
             genre <- factor(genre, 
                             levels=names(sort(table(genre), 
                                            decreasing=TRUE))))
library(ggplot2)
ggplot(df_clean, aes(x=genre, color=genre)) +
  geom_bar() +
  coord_flip() +
  xlab("Genre of movie") +
  ylab("Number of movies")
```

![](Datapractical_disney_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->
Aswe can see in this first barplot is that there are three main genre of
movies that are produced by Disney. Namely **comedy**, **adventure** and
**drama**. Other genre of movies are much less produces as we can see on
the graph. This is an overall view of disney movies production since
they stared.

The following part of this analyze concerns only the revenue of those
movies, over the entire period of movies production from disney company.

``` r
library(tidyr)


ggplot(df, aes(x=release_date, y=total_gross)) +
  geom_line()
```

    ## geom_path: Each group consists of only one observation. Do you need to adjust
    ## the group aesthetic?

![](Datapractical_disney_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

``` r
ggplot(df, aes(x=genre, y=release_month)) +
  geom_tile()
```

![](Datapractical_disney_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

# Conclusion
