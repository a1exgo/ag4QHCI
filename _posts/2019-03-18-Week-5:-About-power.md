

### INTS
#### Chapter 10 (Statistical Power)
This chapter introduced the concept of statistical power. Instead of thinking of effect size, this concept turns the question in another direction. Here we are much more intersted in what is the chance our experiment will find an effect of a particular size, *if* it exists. 

In terms of statistical language we care about the correct propability of rejections of H0's when the effect size is true. Whereas the Beta error (or Type II error) indicates the propability of *not* rejecting a H0 altough it is through, the power is the oposite (i.e. 1-Beta).


As the rejection of H0 depends on H1. We need to focus on the determinants that influence hypothesis testing (figures in the formula) in order to calculate the statistical power, i.e. power depends on:

- the design, for example independent groups
- chosen α, e.g. .05 (Lower α means it’s harder to reject H0, so more misses (Type II errors) and lower power)
- target effect size, e.g. δ = 0.5 (Larger δ gives higher power, sometimes dramatically higher.)
- N, the size of each group. (Larger N gives higher power.)

To illustrate the relationship between the last three (α, effect size, N) we can calculate it with a tool like GPower. The following example shows what N is needed given α=0.05 and effect size=0.5 (medium size):
![image](https://github.com/a1exgo/ag4QHCI/blob/master/Gpower.png?raw=true)

The same point calculated in GPower can be seen in the figure below (blue circle). Moreover, this picture from the book illustrates Power-N combinations for α=0.05.
![image](https://github.com/a1exgo/ag4QHCI/blob/master/ITNS_statpower.png?raw=true)

### Class: Project Announcement
In the lecture we were introduced to study design techniques and the helpful tool touchstone (https://develop.touchstone2.org). We distinguish the following 'parameters' of an experiment:
- Within- or between-subject design?
- Experiment conditions and balancing: 
  1. Fixed & random order (Attention: order effects!)
  2. Complete counterbalancing (=full permutations leads to super high N requirements)
  3. Partial Counterbalancing (=subset of permutation where some orders are overrepresented, efficient way to go)
  
Two papers were presented for the project: Correll & Heer, (2017), Dimara et al., (2017). Our group decided on Corell & Heer (2017)'s study that evaluates the precision of the regression by eye technique.
