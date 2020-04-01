R Programming for Beginners (Online)
========================================================
author: Jeho Park
date: April 1, 2020
transition: none
autosize: true
css: custom.css

## Murty Sunak Quantitative and Computing Lab
### Online Workshop Series: Level 1 - Coding

Some Housekeeping Stuff
========================================================
- **Sign-in** at http://bit.ly/s2020-10-r-L1
- **Files** at https://cmc-qcl.github.io/r-programming-beginner-online/
- **Interactive poll**: http://pollev.com/jehopark360

This workshop is...
========================================================
* This R Workshop for Beginners is designed:
  - To help you start using R.
  - To help you recall your memory of R programming.
  - For those who already have some basic knowledge of Statistics.

Agenda
========================================================
## Session 1 (Basics)
* Getting Started with R and RStudio
* General and basic information you need to know
* R computing environment setup

## Session 2 (Working with Data)
* Built-in datasets and data import
* Data exploration and data visualization
* Hands-on exercise

Getting Started with R and RStudio
========================================================
A Quick Start Guide for R Beginners

In this section, you will be guided to learn some very basic information about R and RStudio.

I will then check your R/RStudio environment to make sure that you can use R/RStudio afterwards.


What is R?
========================================================
* R is a statical programming language/environment.
* R is open source/free.
* R is widely used in academia and industry
* R is cross-platform.
* R is hard to learn.

What is not R?
========================================================
* S: R's ancestor
* S-Plus: Commercial; modern implementation of S
* SAS: Commercial; widely used in the commercial analytics.  
* SPSS: Commercial; easy to use; widely used in Social Science.
* MATLAB: Commercial; can do some Stats. 
* Python: Also can do some Stats; good in text data manipulation.

How to Get Help
========================================================
* Stack Overflow: http://stackoverflow.com/questions/tagged/r
* Cross-Validated: the statistics Q&A site http://stats.stackexchange.com/
* Google!
* Contact QCL: qcl@cmc.edu; we are located underneath the Cube!

What is RStudio?
========================================================
* Integrated Development Environment for R
* Nice combination of GUI and CLI
* Free and commercial version
* 4 main panes and multiple tabs
* Version control: Git and VPN
* Debugging 
* Documentation: R Markdown
  - install.packages("rmarkdown")
  - http://rmarkdown.rstudio.com/
* Presentation slides: R Presentation (this one!)

Check Point 1: Environment Check
========================================================
* R
* RStudio 

RStudio Cloud at https://rstudio.cloud

What Can We Do with RStudio?
========================================================
## RStudio Introduction (Let's check out different features RStudio offers)
<img src="./r-programming-beginner-figure/rstudio_image.png" width="1000">

Look Ma, R can do Math! 
========================================================

```r
1+1
```


```r
2+runif(1,min=0,max=1)
```


```r
3^2
```


```r
3*3
```


```r
sqrt(3*3) # square root function
```


```r
# comments are preceded by hash sign sqrt(3*3)
```

Even More Math! 
========================================================
* R can take integrals and derivatives, for example:

Numerical Integral of

$\displaystyle\int_0^{\infty} \frac{1}{(x+1)\sqrt{x}}dx$ 


```r
integrand <- function(x) {1/((x+1)*sqrt(x))} ## define the integrated function
```

```r
integrate(integrand, lower=0, upper=Inf) ## integrate the function from 0 to infinity
```

```
3.141593 with absolute error < 2.7e-05
```


Some R Vocabulary
========================================================
* **packages** are add on features to R  include data, new functions and methods, and extended capabilities. Think of them as ``apps'' on your phone. We've already installed several!
* **console** is the main window of R where you enter commands
* **workspace** is the working memory of R where all objects are stored
* **script** is where you store commands to be run in the terminal later, like syntax files in SPSS or .do files in Stata
* **function** is a set of commands doing something to R object(s) by getting inputs, do work, and return outputs. 


Some Gene-R-al Stuff
========================================================

```r
demo() # display available demos
```

```r
demo(graphics) # try graphics demo
```

```r
library() # show available packages on the computer
```

```r
search() # show loaded packages
```

```r
?hist # search for the usage of hist function
```


```r
??histogram # search for package documents containing the word "histogram"
```

Workspace of R
========================================================

R workspace stores objects like vectors, datasets and functions in memory (the available space for calculation is limited to the size of the RAM).


```r
a <- 5 # notice a in your Environment window
```


```r
A <- "text" 
```


```r
a
A
ls()
print(c(a,A))
print(a,A)
```

R Packages
========================================================
- R is known for its community and its huge collection of user-generated packages
- Packages are collections of R functions, data, and compiled code in a well-defined format. The directory where packages are stored is called the library.
- We will install the dplyr package, a popular package for data manipulation


```r
install.packages('dplyr') # you can also use RStudio's Packages tab

# You should load dplyr package first to use any functions and datasets in the package
library('dplyr') 
```

End of Session 1 (break check area)
========================================================
## We looked at general and basic features 
## Check if you can:

* Run RStudio on your computer or log in to RStudio Cloud
* Create a new project in RStudio 
* Create variables and check from the "Environment" pane
* Run R commands on console and directly from the editor window.
* Install new packages and load required packages


Session 2: Working with Data
========================================================
* Built-in datasets and data import
* Data exploration and data visualization
* Hands-on exercise

Built-in Datasets 
========================================================
- R's datasets package has some built in datasets that we will be using.

```r
data() # this will bring up a document, R data sets
```

- Let's look at CO2 datasets. The CO2 data frame has 84 rows and 5 columns of data from an experiment on the cold tolerance of the grass species Echinochloa crus-galli.

```r
help(CO2) # see what the dataset is about
CO2 # display all the contents of the data frame, CO2
```

#### Notice there's no CO2 dataframe in the Environment pane

Data Import
========================================================
## Data file import is very easy with RStudio

Follow the instructor and import "auto.csv" file!

Click-click-click-done!

Check if you have auto in your Environment.

Data Exploration - Head or Tail?
========================================================

```r
# The head function shows the first few entries in a dataframe.
head(CO2)
tail(CO2)
```

Data Exploration - Summary
========================================================

```r
# The summary function shows summary statistics.
summary(CO2)
```

```
     Plant             Type         Treatment       conc     
 Qn1    : 7   Quebec     :42   nonchilled:42   Min.   :  95  
 Qn2    : 7   Mississippi:42   chilled   :42   1st Qu.: 175  
 Qn3    : 7                                    Median : 350  
 Qc1    : 7                                    Mean   : 435  
 Qc3    : 7                                    3rd Qu.: 675  
 Qc2    : 7                                    Max.   :1000  
 (Other):42                                                  
     uptake     
 Min.   : 7.70  
 1st Qu.:17.90  
 Median :28.30  
 Mean   :27.21  
 3rd Qu.:37.12  
 Max.   :45.50  
                
```

Data Visualization
========================================================
- Basic plots such as histogram, box plot, and scatter plot are within a few key strokes away (type `boxp` and wait for it)


```r
hist(auto$weight) # Use help function for more plotting options
boxplot(auto$mpg ~ auto$cylinders)
plot(auto$mpg, auto$horsepower)
```
**Note that we used '$' to extract a variable (column/feature/etc) of a dataframe

Data Visualization - Boxplot
========================================================

```r
boxplot(auto$mpg ~ auto$cylinders, data = auto, xlab = "Number of Cylinders", ylab = "Miles Per Gallon", main = "Mileage Data")
```

Data Visualization - Scatterplot
========================================================

```r
plot(auto$horsepower, auto$mpg, xlab = "Horsepower", ylab = "Miles Per Gallon", main = " MPG vs. Horsepower")
```

Data Wrangling: a simple example
========================================================
# Let's look at simple data wrangling case
* First show the first few observations in iris dataset
* Find the mean sepal length of setosa (using __aggregate__ function)


Data Wrangling: a simple example (cont.)
========================================================


```r
# show the first few observations in iris dataset
head(iris)
# Show mean sepal length for different species
aggregate(mydata$Sepal.Length,by=list(mydata$Species),FUN=mean)
```


Hands-On!
========================================================
Create a barplot showing daily changes in the COVID-19 cases in the US

(1) Data can be found from The NY Times: Coronavirus in the US

https://www.nytimes.com/interactive/2020/us/coronavirus-us-cases.html

(2) Download a Zip file from the GitHub site

(3) Unzip the Zip file in your R workshop project folder

(4) Import us-counties.csv in your R Environment

(5) Use aggregate function to sum "cases" by "date"

(6) Use barplot to plot the counts by day

You have *15 minutes* to finish this task!


End of Session 2
========================================================
# Make sure you can 
* Use built-in datasets
* Summarise datasets (exp. Dataframe)
* Import CSV files
* Plot histogram, boxplot, scatterplot, and barplot
* Aggregate a variable in a dataframe (or tiblet) by another variable


Further Study
========================================================
# Linear Regression


Linear Regression
========================================================
> Linear regression is used to predict the value of an outcome variable Y based on one or more input predictor variables X. The aim is to establish a linear relationship (a mathematical formula) between the predictor variable(s) and the response variable, so that, we can use this formula to estimate the value of the response Y, when only the predictors (Xs) values are known.

$$
Y = \beta_0 + \beta_1 X + ε
$$

where $Y$ is the response, $X$ is the predictor, and $ε$ is a random error term.

The linear model describes a straight line relationship between the response variable Y and predictor X.


Linear Regression (cont.)
========================================================
__Data and Method__

Consider a set of paired observations of speed and stopping distance of cars. Will there be a linear relation between stopping distance and speed of a car? Let's find out.

We will use "cars" dataset which is already installed.

Try ?cars

First we will create a scatter plot from the cars data. Then we will try fitting the relation using the lm function (fitting linear models) in stats package.

Linear Regression (cont.)
========================================================
__Graphical Analysis__ 

Let's first visually check the relatioship between two variables, speed and dist.

```r
# [Q] what kind of plot shows realtionship between two variables?
```

Linear Regression (cont.)
========================================================
__Graphical Analysis__ 

Let's first visually check the relatioship between two variables, speed and dist.

```r
plot(x=cars$speed, y=cars$dist) #simple scatterplot
scatter.smooth(x=cars$speed, y=cars$dist, main="Dist ~ Speed")  # scatterplot with smooth curve
```

Linear Regression (cont.)
========================================================
__Linear Model__ 

The R function for linear regression is lm (i.e., linear model). It takes two arguments: formula and data.

The formula that specifies a simple linear regression model $dist = \beta_1 + \beta_1 speed + ε$ is simply

**dist ∼ speed**


```r
lm(dist ~ speed, data=cars)
```
__The function lm displays only the estimated coefficients, but the object returned by lm contains much more information.__

Linear Regression (cont.)
========================================================
__Fitting the model__ 

Let's save the result:

```r
linearmodel <- lm(dist ~ speed, data=cars) #save the result
intercept <- linearmodel$coefficients[[1]]
slope <- linearmodel$coefficients[[2]]
```

Let's plot the line:

```r
plot(cars, main="dist = -17.579 + 3.932 speed", 
     xlim=c(0, 25), ylim=c(-10,130)) # simple scatter plot
abline(intercept, slope) # adding a line manually
```

Linear Regression (cont.)
========================================================
__Linear Regression Diagnostic__

We want to know how good this model we just found is. 
- Is it statistically significant? 
- How good the model predict the value of response variable w.r.t a new value of the predictor variable. 
- How can we check?


```r
# summary of the model statistics
```


Linear Regression (cont.)
========================================================
__Linear Regression Diagnostic__

We want to know how good this model we just found is. 
- Is it statistically significant? 
- How good the model predict the value of response variable w.r.t a new value of the predictor variable. 
- How can we check?


```r
summary(linearmodel) 
```
Look at p-Values and r-squared for now. 

Linear Regression (cont.)
========================================================
__Linear Regression Diagnostic__

> In Linear Regression, the Null Hypothesis is that the coefficients associated with the variables is equal to zero (no effect). With the p-Value < 0.05, we can reject the null hypothesis. 

> R-squared value tells you that how good the model represent the actual population. It's called a goodness-of-fit measure for linear regression models. This statistic indicates the percentage of the variance in the dependent variable that the independent variables explain collectively.
  
Linear Regression (cont.)
========================================================
__The most common metrics to check the model's quality__ (http://r-statistics.co/Linear-Regression.html)
![Common Metrics](r-programming-beginner-figure/Linear_Regression_With_R.png)


Links and References
========================================================
> Useful links:
> 
> - R tutorial sites: http://jaredknowles.com/r-bootcamp/ and http://adv-r.had.co.nz/
> - R search site: http://rseek.org
> - R Markdown cheat sheet: http://shiny.rstudio.com/articles/rm-cheatsheet.html

**(Adapted from several publicly available resources such as 1) the R-Bootcamp by Jared Knowles: http://jaredknowles.com/r-bootcamp/, 2) Advanced R by Hadley Wickham: http://adv-r.had.co.nz</small>
<small>(Slides are made with the R Presentations tool in RStudio)**