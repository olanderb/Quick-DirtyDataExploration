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
qplot(carat, price, data=diamonds)


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


---
## Ex 3 - Again the Scatter Plot, this time with colors

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: f31c87b30e
```

Ok, we're going to add to this to show you how to add in a color arguement.

`@instructions`

1.  Explore how a diamonds clarity also affects its price using the _fill_ arguement


Remember the format is:

qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)


`@hint`
did you load the library ggplot?
did specify the correct x and y values in the correct order?
did you specify the correct data frame?
did you specify the correct variable to fill?
x
`@pre_exercise_code`
```{r}
library(ggplot2)
```
`@sample_code`
```{r}

#run the same code as last exercise but set the color to clarity
qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size")

```
`@solution`
```{r}


qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size", color=clarity)

```
`@sct`
```{r}
success_msg("Hey, this is cool, do you see the clear relationship between color and prices")
```

---
## Ex 4 - Even more Scatter Plot, adding shapes

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: 2c9c07603f
```

Another option to add different dimensions is to assign a variable to _shape_ .  So lets do it.

`@instructions`

1.  Explore how a diamonds cut affects its price using the _shape_ arguement


Remember the format is:

qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)


`@hint`
did you load the library ggplot?
did specify the correct x and y values in the correct order?
did you specify the correct data frame?
did you specify the correct variable to shape?
x
`@pre_exercise_code`
```{r}
library(ggplot2)
```
`@sample_code`
```{r}

#run the same code as last exercise but set the shape to cut
qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size", color=clarity)

#maybe thats too noisy, get rid of the color=clarity option and set shape to cut


```
`@solution`
```{r}

qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size", color=clarity, shape=cut)

qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size", shape=cut)



```
`@sct`
```{r}
success_msg("Some times you have to take a little to get a little.  Putting shapes and color was messy but maybe there is another way. stay tuned")
```


---
## Ex 5 - Last time we scatter .  Scatter with facets

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: c7f853bd0d
```

Another powerful option to view dimensions is to assign a variable to _facets_ So lets do it.

`@instructions`

1.  Lets view the relationship between color, clarity, cut and price using the tricks we've learned before and _facets_ 

Remember the format is:

qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)


`@hint`
did you load the library ggplot?
did specify the correct x and y values in the correct order?
did you specify the correct data frame?
did you specify the correct variable to shape?
x
`@pre_exercise_code`
```{r}
library(ggplot2)
```
`@sample_code`
```{r}

#run the same code as last exercise but add cut to facets with 
qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size", color=clarity)

#maybe thats too noisy, get rid of the color=clarity option and set shape to cut


```
`@solution`
```{r}


qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size", color=clarity, facets=~cut)



```
`@sct`
```{r}
success_msg("Sweet.  Time for other geoms)
```


---
## Ex 6 - Boxing with box plots

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: bf285dea06
```

Boxplots are under-utilized and are a great way to view a lot of information.

`@instructions`

1.  Lets try out boxplots to see the distribution of diamond prices by diamond color 

Remember the format is:

qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)


`@hint`
did you load the library ggplot?
did specify the correct x and y values in the correct order?
did you specify the correct data frame?
did you specify the correct variable to shape?
x
`@pre_exercise_code`
```{r}
library(ggplot2)
```
`@sample_code`
```{r}

#this time put in x=color, y=price, data=diamonds and add geom="boxplot"


```
`@solution`
```{r}


qplot(color, price, data = diamonds, geom = "boxplot")


```
`@sct`
```{r}
success_msg("cool, but there are a lot of outliers.  what else can we do to explore this?")
```




