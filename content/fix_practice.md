---
layout: default
title: Fix my code
nav_order: 10
---

# Fix my code

## Intro

We are working with the iris dataset today

```r
# this is to make the iris dataset show up in the R environement 
iris = iris

# Get an overview of the iris dataset 
summary(iris)
```

## Exercise 1

```r
# Why is this code not working? 
  #We know the length should be 150 from looking at the data in the Environement 
length(iris$species)


```

## Exercise 2

```r
# calculate the median iris$Species

```

## Exercise 3

```r
# install the package if you need to
#install.packages("plyr")

# run the code below as is. 
# load plyr package 
library(plyr)
# Check that plyr is loaded in your packages tab  

# create a new dataframe that is the iris dataset summarized
iris.summarized = ddply(iris, # take the iris dataset
                        c("Species"), # for each Species
                        summarise, # summarize the 
                        mean.sl = mean(Sepal.Length), # mean Sepal.Length 
                        min.sl = min(Sepal.Length), # minumum Sepal.Length
                        max.sl = max(Sepal.Length)) # maximum Sepal.Length

# check that iris.summarized is in your R environement 


# let's say we are curious about Sepal.Width now
print(iris.summarized$max.sw)
# it prints NULL
```

## Answers
Click the dropdown to reveal the answers

<details><summary><strong> Exercise 1 </strong></summary>
<p>Species needs to be capitalized. </p>

<strong>length(iris$Species)</strong>
<p></p>
</details>


<details><summary><strong> Exercise 2 </strong></summary>
<p>Error in median.default(iris$Species) : need numeric data </p>

<p>Species is a character variable, not numeric </p>

<p>You can't do this because it does not make sense to calculate the median of a list of species names. The code below calculates the median for the Sepal.Length column</p>
<strong>median(iris$Sepal.Length)</strong>
<p></p>
</details>

<details><summary><strong> Exercise 3 </strong></summary>
<p>We did not include sepal width in our iris.summarized data so R does not know what you are asking it for. </p>

<p>It is saying, this does not exist. </p>

<p>This can be solved by switching our question to Sepal.Length </p>

<strong>print(iris.summarized$max.sl)</strong>
<p><i>ouput [1] 5.8 7.0 7.9</i></p>
</details>
