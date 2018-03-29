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

We're going to do the same even though it might be the least used type of graphic in humanitarian work.  Why are  we starting off with it?  Because it's so easy!  Qplot produces a scatterplot by default when supplying an an x and a y. 

Let's do a scatterplot using the famous diamonds dataset.

`@instructions`
1.  Explore how a size (carat) affects a diamonds price by creating a  scatterplot on these two variables in the diamonds data set.  Put carat as x and price as y


Remember the format is:

qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)

`@hint`
did you load the library ggplot?
did specify the correct x and y values in the correct order?
did you specify the correct data frame?

`@pre_exercise_code`
```{r}
library(ggplot2)
```
`@sample_code`
```{r}
#load ggplot 


#look at diamonds dataset with str()


#run qplot using carat and price 



```
`@solution`
```{r}
library(ggplot2)

qplot(carat, price, data=diamonds)


```
`@sct`
```{r}
success_msg("Awesome! Isn't this easy?")
```





---
## Ex 2 - Scatter again with labels

```yaml
type: NormalExercise

xp: 100

key: 6c02af1e65
```

Now we're going to add a title and x and y axis labels to the scatter with _main_ , _xlab_ and _ylab_

Remember the format is:

qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)


`@instructions`
Adding to  the code in the last exercise

1. add the title "diamond prices and size" to the scatterplot with _main_
2. add labels to the x and y axis using _xlab_ and _ylab_ .  Label the x axis "size of diamond in carats" and label the y axis "price of diamond in dollars"



`@hint`
are you serious?


`@pre_exercise_code`
```{r}
library(ggplot2)
```
`@sample_code`
```{r}
#code from last time
qplot(carat, price, data=diamonds, color=clarity)


#add labels to the x and y by specifying xlab and ylab and title to main



```
`@solution`
```{r}
qplot(carat, price, data=diamonds, color=clarity, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size")



```
`@sct`
```{r}
success_msg("you got a plot, you got a title.  let's keep going")
```


