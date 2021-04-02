R Programming for Beginners (Online)
========================================================
author: Jeho Park
date: February 10, 2021
transition: none
autosize: true
css: custom.css

## Murty Sunak Quantitative and Computing Lab
### Online Workshop Series: Level 1 - Coding

Some Housekeeping Stuff
========================================================
- **Files** at https://bit.ly/r-workshop-beginner-online
- **GitHub Repo** at https://github.com/CMC-QCL/r-programming-beginner-online.git 

QCL Workshop Participation Requirements: 
========================================================
Those of you attending this workshop as part of requirements for your research group, student employment, or fellowship position, you must attend the workshop fully, do all the hands-on exercises plus homework to be qualified. 

If you have to leave in the middle of the workshop, please leave a note on the chat for the record.

Recommendations for Engagement:  
(1) Use your camera to show your attention  
(2) Use gestures such as nodding, thumbs-up, and rasing hand to signal your understanding/misunderstanding  
(3) Unmute yourself to ask questions anytime   

After you finish this workshop, you will be able to...
========================================================
* Run RStudio on your computer or log in to RStudio Cloud/RStudio Server
* Use RStudio Project environment 
* Create variables and check them from the "Environment" pane or ls()
* Run R commands on console and directly from the editor window.
* Create R Notebook and add Code Chunks
* Install new packages and load required packages
* Use built-in datasets
* Summarise datasets (exp. Dataframe)
* Import CSV files from local folder as well as from remote location
* Plot histogram, boxplot, scatterplot, and barplot
* Aggregate a variable in a dataframe (or tiblet) by another variable (when time permits)

Agenda
========================================================
## Part I: R Computing Environment (30 - 40 min)
* Getting Started with R and RStudio
* R computing environment setup

## Part II: Working with Data (60 - 70 min)
* Built-in datasets and data import
* Data exploration and data visualization
* Hands-on exercise

Getting Started with R and RStudio
========================================================
A Quick Start Guide for R Beginners

In this section, you will be guided to learn some very basic information about R and RStudio.

I will then check your R/RStudio environment to make sure that you can use R/RStudio afterwards.

What is RStudio?
========================================================
* Integrated Development Environment for R
* Nice combination of GUI and CLI
* Free and commercial version
* 4 main panes and multiple tabs
* Version control: Git and VPN
* Debugging 
* Documentation: R Markdown and Notebook
  - install.packages("rmarkdown")
  - http://rmarkdown.rstudio.com/
* Presentation slides: R Presentation (this one!)

Check Point 1: Environment Check
========================================================
For your R'ing, make sure that you have
* R (https://www.r-project.org/) 
* RStudio Desktop (https://rstudio.com/products/rstudio/download/)

For today's workshop, we will be using 
* CMC RStudio Server at https://webapps.cmc.edu/rstudio/

Please log in to your RStudio Server account. RStudio Server offers the same RStudio Desktop interface and more such as project sharing. 

For non-CMC folks, we have provided generic training accounts (e.g., ruser1). These accounts will be available to you for 2 weeks after the workshop.


RStudio Project
========================================================
* Each project has its own folder to contain all the files you create for the project.
* History and Environment will be saved and be restored when you reopen the project.
* Version control (Git/GitHub) can be effectively used.

For more information about Git/GitHub use for R, please see https://happygitwithr.com/rstudio-git-github.html.


R's Arithmetic Operators
========================================================
That's right! R is a programming languge.

```r
a <- 16 # assignment operator! Is it an arrow sign?
b <- 3
add <- a + b
sub = a - b
mult = a * b
div = a / b
int_div = a %/% b
exponent = a ^ b
modulus = a %% b
```


```r
# comments are preceded by hash sign
```

Workspace
========================================================

R workspace stores objects like vectors, datasets and functions in memory (the available space for calculation is limited to the size of the RAM).


```r
ls()
```

[Hands-On] Now it's your turn
========================================================

Let's create a R Notebook and start the hands-on exercise in the Notebook document.

* Click on _File > New File > R Notebook_
* Save it as _QCL-R-Workshop-[your_initial]_
* And follow my instructions

Exercise 1:

Create a variable x containing pi times pi, and another variable y containing a square root of x. Show the values as an output.

Homework
========================================================
After finishing all the workshop exercises (Part I and Part II) on the R Markdown file you just created, submit the Rmd file (QCL-R-Workshop-[your_initial].Rmd) via email to 

qcl@cmc.edu

Email Subject Line should be:  
QCL R Workshop - [Your Name] - 2/10/2021 



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

End of Part I (break check area)
========================================================
## We looked at general and basic features 
## Check if you can:

* Run RStudio on your computer or log in to RStudio Server
* Use RStudio Project environment 
* Create variables and check them from the "Environment" pane or ls()
* Run R commands on console and directly from the editor window.
* Create R Notebook and add Code Chunks
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

Point-and-Click

Check if you have *auto* in your Environment.

Hands-On: Data Exploration - Head or Tail?
========================================================
When you have a large dataset, it's impossible and inconvenient to display the whole contents of the dataset on the screen. You will want to check the first few rows or the last few rows of the dataset. 

Exercise 2:

In this exercise, you will create a Code Chunk in the Notebook doing the following:
(1) Import "auto.csv" as auto_data
(2) Output the first row of auto_data using R's built-in function
(3) Output the last row of auto_data using R's built-in function

Data Exploration - Summary
========================================================

```r
# The summary function shows summary statistics.
summary(CO2)
# summary(auto) # try this if you did Exercise 2 above
```

Data Visualization
========================================================
- Basic plots such as histogram, box plot, and scatter plot are within a few key strokes away (type `boxp` and wait for it)


```r
hist(auto$weight) # Use help function for more plotting options
boxplot(auto$mpg ~ auto$cylinders)
```
**Note that we used '$' to extract a variable (i.e., column) of a dataframe

**Note that we used '~' for boxplot. This is a R formula. The left side of tilde is a dependent variable. The right side of the tilde is an independent variable(s) (like y = x + 1). The right side of the formula is sometimes called predictor or feature.

Hands-On: Data Visualization - Scatter Plot
========================================================
Scatter plot is a very useful tool when you want to visualize a relationship between two variables. 

Exercise 3:
In this exercise, you want to create a scatter plot showing mpg on X axis and horsepower on Y-axis to see the relationship between the two variables.

In addition, change X label to "Miles per Gallon" and Y label to "Horse Power" and add a title "Horse Power vs. MPG" 

Data Visualization - Boxplot
========================================================

```r
boxplot(auto$mpg ~ auto$cylinders, data = auto, xlab = "Number of Cylinders", ylab = "Miles Per Gallon", main = "Mileage Data")
```

Data Wrangling
========================================================
Data wrangling, sometimes referred to as data munging, is the process of **transforming** and **mapping data** from one "raw" data form into another format with the intent of making it more appropriate and valuable for a variety of downstream purposes such as analytics. 

This may include further **munging**, **data visualization**, **data aggregation**, **training a statistical model**, as well as many other potential uses. 

Source: [Wikipedia](https://en.wikipedia.org/wiki/Data_wrangling)

<img src="./r-programming-beginner-online-figure/data-science-wrangle.png" title="Data Wrangling" alt="Data Wrangling" width="80%" style="display: block; margin: auto;" />

Data Wrangling: a simple example
========================================================
## Let's look at a simple data wrangling case
In this example, we use iris dataset (try ?iris from your console.)

* First show the first few observations in iris dataset
* Now try `str(iris)` to see the structure of the dataset
* Find the mean sepal length of setosa (using `aggregate` function)


Data Wrangling: a simple example (cont.)
========================================================


```r
# show the first few observations in iris dataset
head(iris)

# check the structure of the iris dataset
str(iris)

# Show mean sepal length for each different specie
aggregate(Sepal.Length ~ Species, data = iris, FUN = mean)
```

(Note: an aggregate function is a function outputing one single summary value from the values of grouped multiple observations. For example, sum, mean, count, etc.)

R Formula (A side note)
========================================================
At this stage, you might be wondering what the tilde (~) was for in the box plot and aggregate example as in:

boxplot(**auto$mpg ~ auto$cylinders**)  
aggregate(**Sepal.Length ~ Species**, data = iris, FUN = mean)

For example, **y ~ x** is called *fomula* in R where the left-hand side of a tilde (~) is the "dependent variable" and the right-hand side is the "independent variables." In most cases, you read it as y is a function of x. In the aggregate case, you read it as "y is grouped according to x." The FUN argument tells how they are computed. In our example, the Sepal.Length values are averaged using the mean function. 


(Stretch) Hands-On! COVID-19 Cases in the U.S.
========================================================
Create a barplot showing daily changes in the new COVID-19 cases in the US.

(1) Data can be found from The NY Times: Coronavirus in the US   
Here's the [report](https://www.nytimes.com/interactive/2020/us/coronavirus-us-cases.html) and [data description](https://www.nytimes.com/article/coronavirus-county-data-us.html)  
(2) Open the GitHub repository where they store the up-to-date datasets  
(3) Find the **raw** CSV file URL for U.S.State-Level Data (us-states.csv); copy the link address.  
(4) Save the link address as fileurl variable.  
(5) Import us-states.csv to your R Environment   
(6) Use aggregate function to sum "cases" by "date"  
(7) Use diff function to calculate the difference between two consecutive days.  
(8) Use barplot to plot the new cases by day 

You have *15 minutes* to finish this task!

(Stretch) Hands-On! (Continue)
========================================================
Exercise 4:
Create a barplot showing daily changes in the new COVID-19 cases in the US.


```r
fileurl <- "https://raw.githubusercontent.com/nytimes/covid-19-data/master/us-states.csv"

library(readr)
us_states <- read_csv(fileurl) # you may directly put the URL
data_covid <- aggregate(  _add_your_code_here_  )
new_cases <- diff( _add_your_code_here_   )
barplot(new_cases)
```

End of Session 2
========================================================
# Make sure you can 
* Use built-in datasets
* Summarise datasets (exp. Dataframe)
* Import CSV files from local folder as well as from remote location
* Plot histogram, boxplot, scatterplot, and barplot
* (Aggregate a variable in a dataframe (or tiblet) by another variable)

To Be Eligible for Participation
========================================================
(1) Participate in the workshop.  
(2) Follow all the hands-on activities.  
(3) Create an R Notebook containing hands-on exercises.  
(4) Send the R Notebook file to qcl@cmc.edu (subject line: "QCL R Workshop - [Your Name] - 2/10/2021") as an attachment.


Links and References
========================================================
> Useful links:
> 
> - R tutorial sites: there are many tutorial sites to learn R; just search R tutorial from Google
> - R Markdown cheat sheet: http://shiny.rstudio.com/articles/rm-cheatsheet.html.
> - Important Package for Data Science: tidyverse (https://www.tidyverse.org/) 

----  
> References: 
> - The R-Bootcamp by Jared Knowles: http://jaredknowles.com/r-bootcamp/,
> - Advanced R by Hadley Wickham: http://adv-r.had.co.nz**
> - RStudio Cloud Primers: https://rstudio.cloud/learn/primers

