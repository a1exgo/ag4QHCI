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
- Create a mapping (aes()) of the data frame. Note that ggplot works in layers (add layer (geom_point are data points/scatters) over empty graph (ggplot) to get the desired graph):
```
ggplot(data = <df>) 
  + <GEOM_FUNCTION>(mapping = aes(<MAPPINGS>))
```
- The aes() function can be 'modified' by assigning the following defintion to a variable (categorical variables seem to work best): color=, size=, alpha=, shape=, e.g.:
```
  + geom_point(mapping = aes(x = displ, y = hwy, shape = class))
```

- Changes outside the aes() function need to be sepcified, as no variable mapping is defined. Colors are string, shapes are numbers:
![image](ag4QHCI/shapes-1.png)

