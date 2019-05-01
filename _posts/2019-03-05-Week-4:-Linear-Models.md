### Class
In today's lecture we got an insight into translating statistical models to R.

- Prepare the data, i.e. read the file and factorize the variables:
```html
data <-
  read_csv("<dataset>", col_types = "cccd") %>%
  mutate(
    device = as.factor(device),
    vision = as.factor(vision))
```
- Formulating the model, e.g. a model with two independent variables and their interaction:
```html
lm(<DV> ~ <IV1> + <IV2> + <IV>:<IV>, data=<dataset>)
```
- e.g. WITHIN design model with two independent variables and their interaction 
```html
import::from(lmerTest, lmer)
lmer(<DV> ~ (1|participant) + <IV1> * <IV2>, data=<dataset>)
```
- Create a ANOVA:
```html
import::from(psycho, analyze)
Model1 <- lm(<DV> ~ <IV1> * <IV2>, data=<dataset>)
anova_Model1 <- anova(Model1)
anova_Model1
```
- Analyzing interaction terms..
  - ..if *not* statistically significant
   ```html
   m_btw_main <-  update(m_btw, .~. - <IV1>:<IV2>)
     m_btw_main_pairwise <-
       glht(m_btw_main,
         linfct = mcp(
           <IV1> = "Tukey",
           <IV2> = "Tukey"))
    ```
  - ..if not statistically significant
   ```html
   m_main <-  update(Model1, .~. - <IV1>:<IV2>)
   ```
   


    
