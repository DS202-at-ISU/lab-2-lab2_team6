
<!-- README.md is generated from README.Rmd. Please edit the README.Rmd file -->

# Lab report \#1

*Question 1:* Variables Parcel ID; type chr, showing an id number for
each observation Address; type chr, showing address of each sold house
Style; type factor, showing architectural type of each sold house
Occupancy; type factor, showing the occupancy type of each house (i.e.,
condo, townhome, etc.) Sale Date; type date, showing date of sale Sale
Price; type num, showing price of each sale Multi sale; type chr,
showing whether or not it was a multi sale YearBuilt; type num, showing
year it was built Acres; type num, showing acreage of lot sold
TotalLivingArea; type num, showing total square footage of house sold
Bedrooms; type num, showing number of bedrooms FinishedBsmtArea; type
num, showing square footage of finished basement LotArea; type num,
showing square footage of lot AC; type chr, showing whether it has AC or
not Fireplace; type chr, showing whether it has a fireplace or not
Neighborhood; type Factor, showing what type of neighborhood it is
located in

<<<<<<< HEAD
=======
3.  

``` r
max(ames$`Sale Price`, na.rm = FALSE)
```

    ## [1] 20500000

``` r
min(ames$`Sale Price`, na.rm = FALSE)
```

    ## [1] 0

``` r
library("ggplot2")
```

``` r
ggplot(ames, aes(x = `Sale Price`)) +
  geom_histogram()
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](/Users/brennansauser/Library/CloudStorage/OneDrive-IowaStateUniversity/lab-2-lab2_team6/README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

Amanda

``` r
library("classdata")
ames
```

    ## # A tibble: 6,935 × 16
    ##    `Parcel ID` Address     Style Occupancy `Sale Date` `Sale Price` `Multi Sale`
    ##    <chr>       <chr>       <fct> <fct>     <date>             <dbl> <chr>       
    ##  1 0903202160  1024 RIDGE… 1 1/… Single-F… 2022-08-12        181900 <NA>        
    ##  2 0907428215  4503 TWAIN… 1 St… Condomin… 2022-08-04        127100 <NA>        
    ##  3 0909428070  2030 MCCAR… 1 St… Single-F… 2022-08-15             0 <NA>        
    ##  4 0923203160  3404 EMERA… 1 St… Townhouse 2022-08-09        245000 <NA>        
    ##  5 0520440010  4507 EVERE… <NA>  <NA>      2022-08-03        449664 <NA>        
    ##  6 0907275030  4512 HEMIN… 2 St… Single-F… 2022-08-16        368000 <NA>        
    ##  7 0535105180  511 25TH S… 1 St… Single-F… 2022-08-03             0 <NA>        
    ##  8 0907428446  4510 TWAIN… 1 St… Condomin… 2022-08-16        110000 <NA>        
    ##  9 0527301030  3409 EISEN… 1 St… Single-F… 2022-08-08        350000 <NA>        
    ## 10 0531363050  5426 KANSA… 1 St… Single-F… 2022-08-03        242000 <NA>        
    ## # ℹ 6,925 more rows
    ## # ℹ 9 more variables: YearBuilt <dbl>, Acres <dbl>,
    ## #   `TotalLivingArea (sf)` <dbl>, Bedrooms <dbl>,
    ## #   `FinishedBsmtArea (sf)` <dbl>, `LotArea(sf)` <dbl>, AC <chr>,
    ## #   FirePlace <chr>, Neighborhood <fct>

there are 16 variables in the ames data set. the majority of the
variables are characters. there are some variables that are dates or
years, and there are also some numberical variables.

2.  some variabes of special interest would be sale price

*Question 4: Luke*

``` r
max(ames$`FinishedBsmtArea (sf)`, na.rm = TRUE)
```

    ## [1] 6496

``` r
min(ames$`FinishedBsmtArea (sf)`, na.rm = TRUE)
```

    ## [1] 10

``` r
ggplot(ames, aes(x = `FinishedBsmtArea (sf)`)) +
  geom_histogram()
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

    ## Warning: Removed 2682 rows containing non-finite values (`stat_bin()`).

![](/Users/brennansauser/Library/CloudStorage/OneDrive-IowaStateUniversity/lab-2-lab2_team6/README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

``` r
ggplot(ames, aes(x = 'FinishedBsmtArea (sf)', y = 'Sale Price')) +
  geom_point() +
  labs(title = "Scatterplot of Finished Basement Area vs. Sale Price",
       x = "Finished Basement Area (sf)",
       y = "Sale Price") +
  theme_minimal()
```

![](/Users/brennansauser/Library/CloudStorage/OneDrive-IowaStateUniversity/lab-2-lab2_team6/README_files/figure-gfm/unnamed-chunk-5-2.png)<!-- -->

I pick FinishedBsmtArea (sf). Range is 6486. It is skewed right, with
the mean centered around 800 sf. The relationship between Sale Price and
FinishedBsmtArea is positive, with sale price rising as FinishedBsmtArea
rises. There are no oddities.

4.  num of bedrooms compared to sales price

``` r
ggplot(ames, aes(x = `Sale Price`, y = Bedrooms)) +
  geom_point()
```

    ## Warning: Removed 447 rows containing missing values (`geom_point()`).

![](/Users/brennansauser/Library/CloudStorage/OneDrive-IowaStateUniversity/lab-2-lab2_team6/README_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

*Question 4* I pick FinishedBsmtArea (sf).

>>>>>>> 7f3287f06b8b3fd000e4a7fa9657a8d07a2c7ce0
Follow the instructions posted at
<https://ds202-at-isu.github.io/labs.html> for the lab assignment. The
work is meant to be finished during the lab time, but you have time
until Monday evening to polish things.

Include your answers in this document (Rmd file). Make sure that it
knits properly (into the md file). Upload both the Rmd and the md file
to your repository.

``` r
head(ames)
```

<<<<<<< HEAD
    ##    Parcel ID                       Address             Style
    ## 1 0903202160      1024 RIDGEWOOD AVE, AMES 1 1/2 Story Frame
    ## 2 0907428215 4503 TWAIN CIR UNIT 105, AMES     1 Story Frame
    ## 3 0909428070        2030 MCCARTHY RD, AMES     1 Story Frame
    ## 4 0923203160         3404 EMERALD DR, AMES     1 Story Frame
    ## 5 0520440010       4507 EVEREST  AVE, AMES              <NA>
    ## 6 0907275030       4512 HEMINGWAY DR, AMES     2 Story Frame
    ##                        Occupancy  Sale Date Sale Price Multi Sale YearBuilt
    ## 1 Single-Family / Owner Occupied 2022-08-12     181900       <NA>      1940
    ## 2                    Condominium 2022-08-04     127100       <NA>      2006
    ## 3 Single-Family / Owner Occupied 2022-08-15          0       <NA>      1951
    ## 4                      Townhouse 2022-08-09     245000       <NA>      1997
    ## 5                           <NA> 2022-08-03     449664       <NA>        NA
    ## 6 Single-Family / Owner Occupied 2022-08-16     368000       <NA>      1996
    ##   Acres TotalLivingArea (sf) Bedrooms FinishedBsmtArea (sf) LotArea(sf)  AC
    ## 1 0.109                 1030        2                    NA        4740 Yes
    ## 2 0.027                  771        1                    NA        1181 Yes
    ## 3 0.321                 1456        3                  1261       14000 Yes
    ## 4 0.103                 1289        4                   890        4500 Yes
    ## 5 0.287                   NA       NA                    NA       12493  No
    ## 6 0.494                 2223        4                    NA       21533 Yes
    ##   FirePlace              Neighborhood
    ## 1       Yes       (28) Res: Brookside
    ## 2        No    (55) Res: Dakota Ridge
    ## 3        No        (32) Res: Crawford
    ## 4        No        (31) Res: Mitchell
    ## 5        No (19) Res: North Ridge Hei
    ## 6       Yes   (37) Res: College Creek
=======
    ## # A tibble: 6 × 16
    ##   `Parcel ID` Address      Style Occupancy `Sale Date` `Sale Price` `Multi Sale`
    ##   <chr>       <chr>        <fct> <fct>     <date>             <dbl> <chr>       
    ## 1 0903202160  1024 RIDGEW… 1 1/… Single-F… 2022-08-12        181900 <NA>        
    ## 2 0907428215  4503 TWAIN … 1 St… Condomin… 2022-08-04        127100 <NA>        
    ## 3 0909428070  2030 MCCART… 1 St… Single-F… 2022-08-15             0 <NA>        
    ## 4 0923203160  3404 EMERAL… 1 St… Townhouse 2022-08-09        245000 <NA>        
    ## 5 0520440010  4507 EVERES… <NA>  <NA>      2022-08-03        449664 <NA>        
    ## 6 0907275030  4512 HEMING… 2 St… Single-F… 2022-08-16        368000 <NA>        
    ## # ℹ 9 more variables: YearBuilt <dbl>, Acres <dbl>,
    ## #   `TotalLivingArea (sf)` <dbl>, Bedrooms <dbl>,
    ## #   `FinishedBsmtArea (sf)` <dbl>, `LotArea(sf)` <dbl>, AC <chr>,
    ## #   FirePlace <chr>, Neighborhood <fct>
>>>>>>> 7f3287f06b8b3fd000e4a7fa9657a8d07a2c7ce0

``` r
str(ames)
```

<<<<<<< HEAD
    ## Classes 'tbl_df', 'tbl' and 'data.frame':    6935 obs. of  16 variables:
    ##  $ Parcel ID            : chr  "0903202160" "0907428215" "0909428070" "0923203160" ...
    ##  $ Address              : chr  "1024 RIDGEWOOD AVE, AMES" "4503 TWAIN CIR UNIT 105, AMES" "2030 MCCARTHY RD, AMES" "3404 EMERALD DR, AMES" ...
    ##  $ Style                : Factor w/ 12 levels "1 1/2 Story Brick",..: 2 5 5 5 NA 9 5 5 5 5 ...
    ##  $ Occupancy            : Factor w/ 5 levels "Condominium",..: 2 1 2 3 NA 2 2 1 2 2 ...
    ##  $ Sale Date            : Date, format: "2022-08-12" "2022-08-04" ...
    ##  $ Sale Price           : num  181900 127100 0 245000 449664 ...
    ##  $ Multi Sale           : chr  NA NA NA NA ...
    ##  $ YearBuilt            : num  1940 2006 1951 1997 NA ...
    ##  $ Acres                : num  0.109 0.027 0.321 0.103 0.287 0.494 0.172 0.023 0.285 0.172 ...
    ##  $ TotalLivingArea (sf) : num  1030 771 1456 1289 NA ...
    ##  $ Bedrooms             : num  2 1 3 4 NA 4 5 1 3 4 ...
    ##  $ FinishedBsmtArea (sf): num  NA NA 1261 890 NA ...
    ##  $ LotArea(sf)          : num  4740 1181 14000 4500 12493 ...
    ##  $ AC                   : chr  "Yes" "Yes" "Yes" "Yes" ...
    ##  $ FirePlace            : chr  "Yes" "No" "No" "No" ...
    ##  $ Neighborhood         : Factor w/ 42 levels "(0) None","(13) Apts: Campus",..: 15 40 19 18 6 24 14 40 13 23 ...

=======
    ## tibble [6,935 × 16] (S3: tbl_df/tbl/data.frame)
    ##  $ Parcel ID            : chr [1:6935] "0903202160" "0907428215" "0909428070" "0923203160" ...
    ##  $ Address              : chr [1:6935] "1024 RIDGEWOOD AVE, AMES" "4503 TWAIN CIR UNIT 105, AMES" "2030 MCCARTHY RD, AMES" "3404 EMERALD DR, AMES" ...
    ##  $ Style                : Factor w/ 12 levels "1 1/2 Story Brick",..: 2 5 5 5 NA 9 5 5 5 5 ...
    ##  $ Occupancy            : Factor w/ 5 levels "Condominium",..: 2 1 2 3 NA 2 2 1 2 2 ...
    ##  $ Sale Date            : Date[1:6935], format: "2022-08-12" "2022-08-04" ...
    ##  $ Sale Price           : num [1:6935] 181900 127100 0 245000 449664 ...
    ##  $ Multi Sale           : chr [1:6935] NA NA NA NA ...
    ##  $ YearBuilt            : num [1:6935] 1940 2006 1951 1997 NA ...
    ##  $ Acres                : num [1:6935] 0.109 0.027 0.321 0.103 0.287 0.494 0.172 0.023 0.285 0.172 ...
    ##  $ TotalLivingArea (sf) : num [1:6935] 1030 771 1456 1289 NA ...
    ##  $ Bedrooms             : num [1:6935] 2 1 3 4 NA 4 5 1 3 4 ...
    ##  $ FinishedBsmtArea (sf): num [1:6935] NA NA 1261 890 NA ...
    ##  $ LotArea(sf)          : num [1:6935] 4740 1181 14000 4500 12493 ...
    ##  $ AC                   : chr [1:6935] "Yes" "Yes" "Yes" "Yes" ...
    ##  $ FirePlace            : chr [1:6935] "Yes" "No" "No" "No" ...
    ##  $ Neighborhood         : Factor w/ 42 levels "(0) None","(13) Apts: Campus",..: 15 40 19 18 6 24 14 40 13 23 ...

Jackson picked TotalLivingArea (sf)

``` r
Range_TotalLivingArea <- range(ames$`TotalLivingArea (sf)`, na.rm = TRUE)
print(Range_TotalLivingArea)
```

    ## [1]    0 6007

``` r
ggplot(data = ames) + 
  geom_smooth(mapping = aes(x = `TotalLivingArea (sf)`, y = `Sale Price`, )) 
```

    ## `geom_smooth()` using method = 'gam' and formula = 'y ~ s(x, bs = "cs")'

    ## Warning: Removed 447 rows containing non-finite values (`stat_smooth()`).

![](/Users/brennansauser/Library/CloudStorage/OneDrive-IowaStateUniversity/lab-2-lab2_team6/README_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

``` r
TotalLivingArea_extremeSlopeChange <- subset(ames, `TotalLivingArea (sf)` >= 1000 & `TotalLivingArea (sf)` <= 2000)

ggplot(data = TotalLivingArea_extremeSlopeChange ) + 
  geom_smooth(mapping = aes(x = `TotalLivingArea (sf)`, y = `Sale Price`, )) 
```

    ## `geom_smooth()` using method = 'gam' and formula = 'y ~ s(x, bs = "cs")'

![](/Users/brennansauser/Library/CloudStorage/OneDrive-IowaStateUniversity/lab-2-lab2_team6/README_files/figure-gfm/unnamed-chunk-8-2.png)<!-- -->
The graph above tells me that the price per total living area in ft.^2
is higher around 0 - 1200, then after that the sales price goes down
dramatically. Then the sales price flattens out around 2500 - 5000; then
it starts to go back up again. The sales price per ft.^2 at the
beginning is very high, its at its highest at around 750 ft.^2, then it
has a dramatic drop around 1200 - 1500. This tells me there is a
starting cost of a building that is automatically built into it or the
supply and demand is very high, I would need more data to figure that
out. The total living area from 1000 - 2000 sales price doesn’t reach
near a constant, it’s constantly changing.

Brennan picked Style (sf)

``` r
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
ames <- ames %>%
  mutate(Price_Range = cut(`Sale Price`,
                           breaks = c(0, 50000, 100000, 150000, 200000, 300000, 400000, 500000, Inf),
                           labels = c("0-50k", "50k-100k", "100k-150k", "150k-200k", "200k-300k", "300k-400k", "400k-500k", "500k+"),
                           include.lowest = TRUE,
                           ordered_result = TRUE))
ames <- ames %>%
  filter(!is.na(Style) & Style != "None")

ggplot(ames, aes(x = Style, fill = Price_Range)) +
  geom_bar(position = "stack", color = "black") +
  theme(axis.text.x = element_text(angle = 45, hjust = 1)) +
  labs(y = "Number of Houses Sold", x = "Type of House", fill = "Sale Price Range")
```

![](/Users/brennansauser/Library/CloudStorage/OneDrive-IowaStateUniversity/lab-2-lab2_team6/README_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

The x-axis represents the different styles, while the y-axis represents
the number of homes sold. Each bar on the graph represents a distinct
style. The bars are divided or “stacked” into color-coded segments that
represent different price ranges. The height of each individual segment
within a bar corresponds to the number of houses of that specific style
sold. Clearly, 0-50k was the most popular sale price. Additionally, one
and two-story frame houses sold the most. And the most homes sold at
500k+ resided within the one-story frame house style.

>>>>>>> 7f3287f06b8b3fd000e4a7fa9657a8d07a2c7ce0
All submissions to the github repo will be automatically uploaded for
grading once the due date is passed. Submit a link to your repository on
Canvas (only one submission per team) to signal to the instructors that
you are done with your submission.
