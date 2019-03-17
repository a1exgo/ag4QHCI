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
ggplot(data = <df>) + 
  <GEOM_FUNCTION>(mapping = aes(<MAPPINGS>))
```
- 
