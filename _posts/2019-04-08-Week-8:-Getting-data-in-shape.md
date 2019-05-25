---
layout: post
categories: theory
---

### R4DS
#### Chapter 5 (Data Transformation)
This chapter is about data transformation that means bringing the data in shape for the analysis.

**Dplyr as data transformator's tool**
`library(Dplyr)'s main manipulation commands are:

- filter() : filter data for certain values 
  useful for subsetting:
  ```html
  subset1 <- filter(<dataframe>, <variable1> == 1, <variable2> > 5)
    ```
- arrange() : reorder
- select() : filters variables (showns as columns a tibble) 
  ```html
  select(<variable1>, <variable2>:<variable4>)
    select(-<variable3>)
  ```
  There are a lot of helper functions that can be shown with `?select`
- mutate () ) 
- summarise ()
