---
layout: post
categories: theory
---

### R4DS
#### Chapter 5 (Data Transformation)
This chapter is about data transformation that means bringing the data in shape for the analysis.

**Dplyr as data transformator's tool**
`library(Dplyr)`'s main manipulation commands are:

- `filter()` : filter data for certain values 
  useful for subsetting:
  ```html
  subset1 <- filter(<dataframe>, <variable1> == 1, <variable2> > 5)
    ```
- `arrange()` : reorders in a similar way as filter except that it changes the order of rows
  handy to order by variables' values:
  ```html
  arrange(<dataframe>, desc(<orderingvariable>))
  ```
- `select()` : filters variables/columns (shown as a tibble that 'zooms' into preferably big data set)
  ```html
  select(<variable1>, <variable2>:<variable4>)
    select(-<variable3>)
  ```
  - Moreover, there are some nice helper functions:
    `starts_with("abc")`: matches names that begin with “abc”.
    `ends_with("xyz")`: matches names that end with “xyz”.
    `contains("ijk")`: matches names that contain “ijk”.
    `matches("(.)\\1")`: selects variables that match a regular expression. This one matches any variables that contain repeated characters. You’ll learn more about regular expressions in strings.
    `num_range("x", 1:3)`: matches x1, x2 and x3
- `mutate()`: mutate adds new columns that are functions of existing columns, e.g. example from the book:
    ```html
    flights_sml <- select(flights,
      year:day,
      ends_with("delay"),
      distance,
      air_time
    )
    mutate(flights_sml,
    gain = dep_delay - arr_delay,
    speed = distance / air_time * 60
    )
    ```

    We can also keep the new variables (instead of adding new columns) with `transmute`:
    ```html
    transmute(flights,
    gain = dep_delay - arr_delay,
    hours = air_time / 60,
    gain_per_hour = gain / hours
    )
    ```
            
- `summarise()`: This function collapses a data frame to a single row. This funtction takes a vector of values and returns a single number. 
    ```html
    <dataframe> %>% 
    summarise (mean_anything = mean(<variable> na.rm = TRUE))
    ```
    better use it with `group_by` as in the example of the book (When dplyr verbs are used on a grouped data frame they’ll be automatically applied “by group”):
    ```html
    by_day <- group_by(flights, year, month, day)
    summarise(by_day, delay = mean(dep_delay, na.rm = TRUE))
    ```
