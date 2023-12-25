---
layout: default
title: Fix my code
nav_order: 10
---

### Intro

We are working with the iris dataset today

```{r}
# this is to make the iris dataset show up in the R environement 
iris = iris

# Get an overview of the iris dataset 
summary(iris)
```

### Exercise 1

```{r}
# Why is this code not working? 
  #We know the length should be 150 from looking at the data in the Environement 
length(iris$species)


```

### Exercise 2

```{r}
# calculate the median iris$Species

```

### Exercise 3

```{r}
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

### Answers

```{r}

# Exercise 1
  # Species needs to be capitalized 
length(iris$Species)




# Exercise 2
  # Error in median.default(iris$Species) : need numeric data 
  # Species is a character variable, not numeric 
# You can't do this because it does not make sense. The code below calculates the median for the Sepal.Length column
median(iris$Sepal.Length)




# Exercise 3
# we did not include sepal width in our iris.summarized data so R does not know what you are asking it for. 
# It is saying, this does not exist. 
# this can be solved either by swithing your question to Sepal.Length 
print(iris.summarized$max.sl)
  # ouput [1] 5.8 7.0 7.9
# or solved by adding Sepal.Width to the summarized iris dataset
iris.summarized = ddply(iris, # take the iris dataset
                        c("Species"), # for each Species
                        summarise, # summarize the 
                        mean.sl = mean(Sepal.Length), # mean Sepal.Length 
                        min.sl = min(Sepal.Length), # minumum Sepal.Length
                        max.sl = max(Sepal.Length), # maximum Sepal.Length
                        mean.sw = mean(Sepal.Width), # same as 3 above but with width 
                        min.sw = min(Sepal.Width), 
                        max.sw = max(Sepal.Width)) 
# try the print function again
print(iris.summarized$max.sw)
# ouput is [1] 4.4 3.4 3.8 
```
