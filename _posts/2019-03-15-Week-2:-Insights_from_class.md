---
layout: post
categories: theory
---
###R4DS
####Chapter 4, 6, 8
The chapters to read covered workflow suggestions about basics, scripts and projects. 
The basics chapter 4 introduced basic functions of R that included the language's requirements and variable creation.

####Class
**NOIR**
Week 2 covered constructs and operationalization methods. The concept NOIR  (nominal, ordinal, interval, ratio) regarding 'characteristic' operationalization will certainly follow the course's project. 

- N: Used to count frequencies, e.g. colors
- O: Puts outcomes in an order, e.g. ranking of colleges
- I: Measures gradual distances and facilates adding and subtracting and calculating of means, e.g. birthday, time periods
- R: Used when a zero-value is meaningful, e.g. time to complete a task

**Pipes**
- Pipes
Useful are a nice tool (or rather operator) within the dplyr package (provided by the margrittr package). With pipes we can 'break up' chained functions and forward a value, or the result of an expression, into the next function call/expression. For instance, it may help with a creating regression tables:
```html
<dataframe> %>%
        filter(<subsetting_variable> > 1) %>%
        lm(<dependent_variable> ~ <independent_variable1> + <independent_variable2>, data = .) %>%
        summary()
```
data aggregation works easier:
```html
<dataframe> %>% summary()
        

{% comment %}
Might you have an include in your theme? Why not try it here!
{% include my-themes-great-include.html %}
{% endcomment %}


