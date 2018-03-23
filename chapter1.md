---
title: Dirty Boxing with qplot
description: >-
  In this chapter we'll teach you how to use qplot to win a fight.  Mastering the ggplot2 language can be overwhelming at first and there is a helper function called qplot() (q for quick plot) which can be used to create the most common types of graphs.  You'll probably be suprised how powerful it is and may be even inspired to go up a weight class later with ggplot.


---
## Ex 1 - Scatter Plot

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: bb3bd2e856
```

A lot of courses start off with the scatter plot.  We're going to do the same even though it might be the least used type of graphic in humanitarian work.  Why are  we starting off with it?  Because it's so easy!  Qplot produces a scatterplot by default when giving an x and a y. 

Let's do a scatterplot using the famous diamonds dataset.

`@instructions`
1.  Explore how a size (carat) affects a diamonds price by creating a  scatterplot on these two variables in the diamonds data set.  Put carat as x and price as y

2.  Explore how a diamonds clarity also affects its price



`@hint`
did you load the library ggplot?
did specify the correct x and y values in the correct order?
did you specify the correct data frame?
did you specify the correct variable to fill?
remember qplots structure ? qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)

`@pre_exercise_code`
```{r}
library(ggplot2)
```
`@sample_code`
```{r}
#load ggplot 


#look at diamonds dataset with str()


#run qplot using carat and price 


#run the same but set the color to clarity
```
`@solution`
```{r}
library(ggplot2)

qplot(carat, price, data=diamonds)

qplot(carat, price, data=diamonds, color=clarity)
```
`@sct`
```{r}
success_msg("Awesome! Isn't this easy?")
```





---
## Ex 2 - Scatter again with more options

```yaml
type: NormalExercise

xp: 100

key: 6c02af1e65
```

  We're going to keep the same scatter but play with a couple more options to get you more excited about qplot.

Specifically, we're going to:

1.  add labels to the x and y axis using _xlab_ and _ylab_
2.  add in how the cut of a diamond affects the price usng _shape_
3.  explore changing the transparency of the graph by adjusting the _alpha_

`@instructions`
Adding to  the code in the last exercise

1.  add labels to the x and y axis using _xlab_ and _ylab_ .  Label the x axis "size of diamond in carats" and label the y axis "price of diamond in dollars"
2.  add in how the cut of a diamond affects the price usng _shape_
3.  explore changing the transparency of the graph by adjusting the _alpha_


`@hint`
remember qplots structure ? qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)

`@pre_exercise_code`
```{r}
library(ggplot2)
```
`@sample_code`
```{r}
#code from last time
qplot(carat, price, data=diamonds, color=clarity)


#add labels to the x and y by specifying xlab and ylab


#add shape arguement to formula, setting shape to cut


#it's hard to read so lets adjust the transparency, let's set the alpha to 1/3


```
`@solution`
```{r}
qplot(carat, price, data=diamonds, color=clarity, xlab="size of diamond in carats", ylab="price of diamond in dollars")


qplot(carat, price, data=diamonds, color=clarity,  xlab="size of diamond in carats", ylab="price of diamond in dollars", shape=cut)



qplot(carat, price, data=diamonds, color=clarity,  xlab="size of diamond in carats", ylab="price of diamond in dollars", shape=cut,  alpha = I(1/3))


```
`@sct`
```{r}
success_msg("ya boy!")
```




---
## Ex 3 - Scatter again with even more options

```yaml
type: NormalExercise
xp: 100
key: 4be3e93005
```

  Are you getting tired of the scatter.  Let's teach a few more options and then well move on 

Specifically, we're going to:

1.  add facets to have another way of comparing data
2.  change the background with a different style
`@instructions`
Adding to  the code in the last exercise

1.  add cut to _facets_




`@hint`
remember qplots structure ? qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)

`@pre_exercise_code`
```{r}
library(ggplot2)
```
`@sample_code`
```{r}
#code from last time
qplot(carat, price, data=diamonds, color=clarity)


#add facet element specifying cut






```
`@solution`
```{r}
qplot(carat, price, data=diamonds, color=clarity, facets=~cut)


```
`@sct`
```{r}
success_msg("ya boy!")
```








