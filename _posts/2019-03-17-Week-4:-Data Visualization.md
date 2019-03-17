---
layout: post
categories: theory
---

### R4DS
#### Chapter 3
This chapter conptualizes the use of the package ggplot. As a prerequisit tidyverse is necessary.

- Test data frames (=<df>) with:
```
ggplot::<df>
```
- Create a mapping (aes()) of the data frame. Note that ggplot works in layers (add layer (geom_point are data points/scatters) over empty graph (ggplot) to get the desired graph). Note that the + needs bo be at the end of each line it is used:
```
ggplot(data = <df>) +
   <GEOM_FUNCTION>(mapping = aes(<MAPPINGS>))
```
- The aes() function can be 'modified' by assigning the following defintion to a variable (categorical variables seem to work best): color=, size=, alpha=, shape=, stroke=, fill=, group=. E.g.:
```
   geom_point(mapping = aes(x = displ, y = hwy, shape = class))
```

- Changes outside the aes() function need to be sepcified, as no variable mapping is defined. Colors are string, shapes are numbers:
![image](https://d33wubrfki0l68.cloudfront.net/2705b59d57362a103f0dad04b0ccfdeff9a101d2/3dc1b/visualize_files/figure-html/shapes-1.png)


