---
title: 'Getting Started in Qplot with Scatterplots and Bar Charts'
description: 'In this chapter we''ll introduce you to the basic options of qplot and creae two different types of plots - scatterplots and bar charts.'
---

## Ex 1 - Scatter Plot

```yaml
type: NormalExercise
key: bb3bd2e856
lang: r
xp: 100
skills: 1
```

A lot of data viz courses start off with the scatter plot.  We're going to do the same even though it isn't so frequently used in humanitarian data analysis.  Why are  we starting off with it?  Because it's so easy and powerful!  Qplot produces a scatterplot by default when supplying an x and a y. 

Let's do a scatterplot using the famous diamonds dataset.

`@instructions`
1.  Explore how a size (carat) affects a diamonds price by creating a scatterplot on these two variables in the diamonds dataset.  Put carat as x and price as y


Remember qplots basic format is:

qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)

`@hint`
did you load the library ggplot?
did specify the correct x and y values in the correct order?
did you specify the correct data frame?

`@pre_exercise_code`
```{r}

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
key: 6c02af1e65
xp: 100
```

Now we're going to add a title and x and y axis labels to the scatter with _main_ , _xlab_ and _ylab_
This may not seem like a big deal, but using a little code to build the titles and labels can save you a little time later down the road.

Remember qplots basic format is:

qplot(x, y, data=, color=, fill=, shape=, size=, alpha=, geom=, method=, formula=, facets=, xlim=, ylim=, xlab=, ylab=, main=, sub=)

`@instructions`
Adding to  the code in the last exercise

1. add the mian title "diamond prices and size" to the scatterplot with _main_
2. add labels to the x and y axis using _xlab_ and _ylab_ .  Label the x axis "size of diamond in carats" and label the y axis "price of diamond in dollars"

`@hint`
its pretty easy so you shouldnt need a hint

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
key: f31c87b30e
lang: r
xp: 100
skills: 1
```

Ok, we're going to add to this to show you how to add in a color arguement to add another dimension to your analysis and presentation.

`@instructions`
1.  Explore how a diamonds clarity also affects its price using the _color_ arguement

*for the astitute users out there, we will touch on the difference between color and fill later on 

Remember qplots basic format is:

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
success_msg("Hey, this is cool, do you see the clear relationship between color and prices?  ")
```

---

## Ex 4 - Even more Scatter Plot, adding shapes

```yaml
type: NormalExercise
key: 2c9c07603f
lang: r
xp: 100
skills: 1
```

Another option to add different dimensions is to assign a variables to _shape_.  Let's try it.

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

#well maybe that is too much information, get rid of the color=clarity option and set shape to cut


```

`@solution`
```{r}

qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size", color=clarity, shape=cut)

qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size", shape=cut)



```

`@sct`
```{r}
success_msg("Hmm, too busy to tell us very much.  Putting shapes and color was messy but maybe there is another way to look at multiple dimensions. next up")
```

---

## Ex 5 - Last time we scatter .  Scatter with facets

```yaml
type: NormalExercise
key: c7f853bd0d
lang: r
xp: 100
skills: 1
```

Another powerful option to view dimensions is to assign a variable to _facets_ .

We'll get into the details of facets later, for now you just need to know that you to add one ~ and the name of the variable you want to facet. so to facet by clarity we would insert the argument "facet=~clarity"

Better to do it than talk about it.  Let's go.

`@instructions`
1.  Lets view the relationship between color, clarity, cut and price using the options we've learned up to now and  we've learned before and _facets_ 

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

#run the same code from the before and add cut to the facet arguement
qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size", color=clarity)



```

`@solution`
```{r}


qplot(carat, price, data=diamonds, xlab="size of diamond in carats", ylab="price of diamond in dollars", main="diamond prices and size", color=clarity, facets=~cut)



```

`@sct`
```{r}
success_msg("Sweet.  let's use bar charts")
```

---

## Ex 6 - Still keeping it easy - Bar Charts.

```yaml
type: NormalExercise
key: bf285dea06
lang: r
xp: 100
skills: 1
```

We're going use a new data set and a barchart to practice and build on some of the options we've been practicing.  If you thought buidling a scatterplot was easy, building a bar chart was even easier.  If you only supply one variable qplot by default builds a bar chart. SO Lets build some easy barcharts to explore WFP's mVAM data

`@instructions`
1.  Get a feel for the data set using str()
2.  Create a barchart of the number of survey respondents by interview language by supplying and x value and the dataset
3.  Add the region (adm1_name) to facets to view the number of resondents by interview language by region


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
GIN_mVAM_012018 <- read.csv("https://assets.datacamp.com/production/repositories/2626/datasets/9d1175b385139d6d8c09241908a9e9f5166fe528/GIN_mVAM_012018.csv")
```

`@sample_code`
```{r}

#explore the data set GIN_mVAM_012018 (which is already loaded for you) 


#create a barchart of the number of survey respondents by interview language "Langue"


#Add the region "ADM1_NAME" to facets to the plot above to  view the number of resondents by interview language by region


```

`@solution`
```{r}


qplot(color, price, data = diamonds, geom = "boxplot")


```

`@sct`
```{r}
success_msg("cool, but there are a lot of outliers.  what else can we do to explore this?")
```

---

## Ex 7 -  Bar Charts II - playing with color, fill and transparency options.

```yaml
type: NormalExercise
key: 2905399838
lang: r
xp: 100
skills: 1
```

Now we can explore more options for colors.  As we explored in the scatterplot exercise we can assign colors to a variable, but we can also  assign specific colors instead of having qplot picking the for us.  We can also set the outline color and not the fill or vice versa or both and we can also adjust the transparency.  Here is a little explanation of the 3 arguements we will be exploring:

For line plots, _color_ associates levels of a variable with line color. For density and box plots, _fill_ associates fill colors with a variable. In a bar chart like we are creating, _color_ is the outline color and _fill_ is, well, the fill color.  Seeeing is believing.

_alpha_: Alpha sets the transparency expressed as a fraction between 0 (complete transparency) and 1 (complete opacity).  It might seem like simply aesthetics, but this could be quite useful if you have overlapping elements (think of a lot of bars on top of each other.  

One more thing, to assign specific colors and transparencies rather than have qplot guess that it is some variable , you need to use the I() in the arguments.   The I() function inhibits the interpretation of its arguments.

`@instructions`
1.  Using the sample code from last exercise, set the fill color to the variable Langue
2.  Set the fill color to the color "Red"  - remember in qplot you have to you the I() arguement.
3.  Set the fill color to the color "Red"  and the fill color to "Blue" - remember in qplot you have to you the I() arguement.
4.  Keeping everything the same, set the transparency with _alpha_ to 0.1
5.  Just to see, set the transparency with _alpha_ 0.5



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
GIN_mVAM_012018 <- read.csv("https://assets.datacamp.com/production/repositories/2626/datasets/9d1175b385139d6d8c09241908a9e9f5166fe528/GIN_mVAM_012018.csv")
```

`@sample_code`
```{r}

#assign the variable Langue to the fill  option in the code below
qplot(Langue, data = GIN_mVAM_012018, facets=~ADM1_NAME)

#assign the color "Red"  to the fill color option in the code below


#fill and color  - use the code above and set the fill to "RED" and the color to "BLUE"


#alpha - Keeping everything the same, set the transparency with _alpha_ to 0.1


#alpha - just to see, set the transparency to 0.5


```

`@solution`
```{r}


qplot(color, price, data = diamonds, geom = "boxplot")


```

`@sct`
```{r}
success_msg("cool, but there are a lot of outliers.  what else can we do to explore this?")
```
