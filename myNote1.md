R Notebook
================

``` r
data("AirPassengers")
AP <- AirPassengers
str(AP) # Time series with 144 values from years 1949 to 1961
```

    ##  Time-Series [1:144] from 1949 to 1961: 112 118 132 129 121 135 148 148 136 119 ...

``` r
# number of passenger in each month in each year = 112 118 129 ...
```

``` r
ts(AP, frequency=12, start=c(1494,1)) # because we have monthly data from 1494 from January
```

    ##      Jan Feb Mar Apr May Jun Jul Aug Sep Oct Nov Dec
    ## 1494 112 118 132 129 121 135 148 148 136 119 104 118
    ## 1495 115 126 141 135 125 149 170 170 158 133 114 140
    ## 1496 145 150 178 163 172 178 199 199 184 162 146 166
    ## 1497 171 180 193 181 183 218 230 242 209 191 172 194
    ## 1498 196 196 236 235 229 243 264 272 237 211 180 201
    ## 1499 204 188 235 227 234 264 302 293 259 229 203 229
    ## 1500 242 233 267 269 270 315 364 347 312 274 237 278
    ## 1501 284 277 317 313 318 374 413 405 355 306 271 306
    ## 1502 315 301 356 348 355 422 465 467 404 347 305 336
    ## 1503 340 318 362 348 363 435 491 505 404 359 310 337
    ## 1504 360 342 406 396 420 472 548 559 463 407 362 405
    ## 1505 417 391 419 461 472 535 622 606 508 461 390 432

``` r
attributes(AP) # in a year we have 12 data points from year 1949 to 1960 something month
```

    ## $tsp
    ## [1] 1949.000 1960.917   12.000
    ## 
    ## $class
    ## [1] "ts"

``` r
plot(AP)
```

![](myNote1_files/figure-gfm/unnamed-chunk-4-1.png)<!-- --> The number
of passengers are gradually going up. But there is also some amount of
seasonality (there are periods of the year which are higher, some other
periods are lower). This time series is definitely not stationary (THIS
IS A PROBLEM)

What can we do? Log transformation
