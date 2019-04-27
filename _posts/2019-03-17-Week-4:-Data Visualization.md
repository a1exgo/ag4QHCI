### R4DS
#### Chapter 3 (Data visualisation)
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
   geom_point(mapping = aes(x = <variable>, y = <variable>, shape = <variablethatdefinesthefacetting>))
```

- Changes outside the aes() function need to be sepcified, as no variable mapping is defined. Colors are string, shapes are numbers:
![image](https://d33wubrfki0l68.cloudfront.net/2705b59d57362a103f0dad04b0ccfdeff9a101d2/3dc1b/visualize_files/figure-html/shapes-1.png)

- Faceting enables the possibility to show graphs depending on certain aspects of a (mostly categorical) variable, e.g. using class as 'faceted' variable (and the number of rows that should be displayed, alternatively ncol= can be used analogously):
```
   facet_wrap(~ <variable>, nrow = 2)
```
   - Facet grid on the other hand creates axes and puts the different facets in it. Moreover one has to specify whether facets should be presented vertically (. ~ <variable>) or horizontally (<variable> ~ .). One should usually put the variable with more unique levels in the columns (unless one wants a very long paper..)
   
 (..)
 
 - In general, ggplot2 can be controlled by the following code structure (a.k.a layered grammar of graphics):
 
```html
ggplot(data = <DATA>) + 

  <GEOM_FUNCTION>(
     mapping = aes(<MAPPINGS>),
     stat = <STAT>, 
     position = <POSITION>
  ) +
  <COORDINATE_FUNCTION> +
  <FACET_FUNCTION>
```

#### Chapter 28 (Graphics for communication)
This chapter is about incorporating the target group's view into the creation process of plots. To achieve this, the chapter involves again ggplot2 and dplyr and additionally ggrepel and viridis.

Specifically the chapter focuesses on implementing/manipulating/adding the following to the graphs:
- Labels
Can be added with the following layer:
```
labs( title = "This is my title to the graph I created in the lines above"
      subtitle = "This adds a smaller title below the title"
      caption = "This adds a caption in the lower rights          )
```
Moreover, we can use the function also to name the axes:
```
labs( x = "Name for the x-axis",
      y = "Name fot the y-axis",
    colour = "Car type"
```

- Anotations
- Scales
- Zooming
- Themes
 

