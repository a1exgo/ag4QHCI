#### R4DS
### Chapter 16 (Dates & Times)
This chapter is about working with dates and times. As some countries have DST or are located in different time zones or leap year are existent, the topic may be relevant. It uses the package `lubricate`.

- Transform date from a string (with bringing y, m, and d in the correct order). Note that his works only if the data is appropriate (otherwise it won't parse):
```
> dateinastring <- "1st of April 2019 "
> dmy(dateinastring)
[1] "2019-04-01"
```
  - we can add a timezone to that:
  ```
  > dmy(dateinastring, tz= 'GMT')
  [1] "2019-04-01 GMT"
  ```
  - and quickly modify with, e.g. to 30th April:
  ```
  ymd("2019-04-01") %>%
  update(mday = 30)
  ```
  
- Transform dates from a data frame (here, I use the package dplyr with the data frame coming from the package nyflights13)
```html
flights %>%
+ select(year, month, day, hour, minute)
 ```

This gives us 336 776 rows. In the next step, we can create dates and datetimes in a new column:
```html
> flights %>%
+ select(year, month, day, hour, minute) %>%
+ mutate(departure = make_datetime(year, month, day, hour, minute))
# A tibble: 336,776 x 6
    year month   day  hour minute departure          
   <int> <int> <int> <dbl>  <dbl> <dttm>             
 1  2013     1     1     5     15 2013-01-01 05:15:00
 2  2013     1     1     5     29 2013-01-01 05:29:00
 3  2013     1     1     5     40 2013-01-01 05:40:00
 4  2013     1     1     5     45 2013-01-01 05:45:00
 5  2013     1     1     6      0 2013-01-01 06:00:00
 6  2013     1     1     5     58 2013-01-01 05:58:00
 7  2013     1     1     6      0 2013-01-01 06:00:00
 8  2013     1     1     6      0 2013-01-01 06:00:00
 9  2013     1     1     6      0 2013-01-01 06:00:00
10  2013     1     1     6      0 2013-01-01 06:00:00
# … with 336,766 more rows
```

Also, we can convert variable values to:
- durations (Quickly create Duration objects for easy date-time manipulation) with `dseconds`, `dminutes`, `dhours`, `ddays`, `dweeks`, `dyears`, e.g.

      ```html
      x <- as.POSIXct("2019-04-01")
      x + ddays(1)
      [1] "2019-04-02 CEST"
      ```
      
- intervals: You can use the commands to set time
      ```html
      years(1) / days(1)
      #> estimate only: convert to intervals for accuracy
      #> [1] 365
      ```
      ```html
      next_year <- today() + years(1)
      (today() %--% next_year) / ddays(1)
      #> [1] 365
      ```
      ```
