### R4DS
#### Chapter 27 (R Markdown)
R Markdown `library(rmarkdown)` is like a notebook for R where comments and code (with output) can be combined and later knited to HTML.

- Formatting
Check this cheatsheet: [link](https://www.dropbox.com/s/wizjp87dozdo8rb/rmarkdown-cheatsheet.pdf?dl=0)

- Code chunks can be implented differently, i.e. chunk options
Call with ALT+CMD+I: and write just after ````{r <option>, <option>}

Option           |	Run code |	Show code |	Output |	Plots |	Messages |	Warnings
------           | -----------|------------|--------|-------|-----------|-------
eval = FALSE     |	   x      |           |   x     |    x   |       x    |x
include = FALSE  |	         |       x     |      x  |   x   |       x    |x
echo = FALSE	  |			   |      x      |        |       |           |
results = "hide" |				|            |    x    |       |           | 	
fig.show = "hide"|				|           |        |     x  |           |
message = FALSE  |				|            |        |       |     x      |
warning = FALSE  |			   |            |        |       |           |x


- Make tables:
```html
knitr::kable(
  <dataframe>[1:5, ], 
  caption = "Table title"
```

#### Chapter 13 (Relational Data)
This chapter is about relational data. Nice codes snippets are listed below:

- counts
  ```html
  <dataframe> %>% 
  count(<variable>) %>% 
  filter(n > 1)
  ```
