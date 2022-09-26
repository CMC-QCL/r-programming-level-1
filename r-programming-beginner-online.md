R Programming for Beginners (Online)
========================================================
author: Dr. Jeho Park
transition: none
autosize: true
css: custom.css

## Murty Sunak Quantitative and Computing Lab
### Workshop Series: Level 1

Some Housekeeping Stuff
========================================================
- **Files** at https://bit.ly/r-workshop-beginner-online
- **GitHub Repo** at https://github.com/CMC-QCL/r-programming-beginner-online.git 

QCL Workshop Participation Requirements: 
========================================================
Those of you attending this workshop as part of requirements for your research group, student employment, or fellowship position, you must attend the workshop fully, do all the hands-on exercises plus homework to be qualified. 

If you have to leave in the middle of the workshop, please leave a note on the chat for the record.

Recommendations for Engagement for Remote Participants:  
(1) Use your camera to show your attention,  
(2) Use gestures such as nodding, thumbs-up, and raising hand to signal you understanding/misunderstanding,  
(3) Type your questions in the chat or simply raise your virtual hand.

After you finish this workshop, you will be able to...
========================================================
* Run RStudio on your computer or log in to RStudio Cloud/RStudio Server
* Use RStudio Project environment 
* Create variables and check them from the "Environment" pane or ls()
* Run R commands on console and directly from the editor window.
* Create R Notebook and add Code Chunks
* Install new packages and load required packages
* Use built-in datasets
* Summarize data frames
* Import CSV files from local folder as well as from remote location
* Plot histogram, boxplot, and scatterplot

Agenda
========================================================
## Part I: R Computing Environment (50 - 60 min)
* Getting Started with R and RStudio
* R computing environment setup

## Part II: Working with Data (50 - 60 min)
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
* RStudio Cloud at https://rstudio.cloud

Please log in to your RStudio Cloud account. RStudio Cloud offers the same RStudio Desktop interface and more such as project sharing. 



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
sub <- a - b
mult <- a * b
div <- a / b
int_div <- a %/% b
exponent <- a ^ b
modulus <- a %% b
```


```r
# a comment is preceded by a hash sign
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
QCL R Workshop - [Your Name] - [Date] 



Some Gene-R-al Stuff
========================================================


```r
?hist # search for the usage of hist function
```


```r
??histogram # search for package documents containing the word "histogram"
```


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

* Run RStudio on your computer or log in to RStudio Server (or RStudio Cloud)
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
summary(auto) # try this if you did Exercise 2 above
```

Data Exploration - Visualization
========================================================
- Basic plots such as histogram, box plot, and scatter plot are within a few keystrokes away
- RStudio suggests the object name for auto-completion (type `boxp` and wait for it)


```r
hist(auto$weight) # Use help function for more plotting options
boxplot(auto$mpg ~ auto$cylinders) # Guess what will be on the y-axis
```
**Note that we used '$' to extract a variable (i.e., column) of a dataframe

**Note that we used '~' for boxplot. This is a R formula. The left side of tilde is a dependent variable. The right side of the tilde is an "independent variable" or "response variable". The right side of the formula is sometimes called predictor or feature.

Hands-On: Data Visualization - Scatter Plot
========================================================
Scatter plot is a very useful tool when you want to visualize a relationship between two variables. 

Exercise 3:
In this exercise, you want to create a scatter plot showing mpg on X axis and horsepower on Y-axis to see the relationship between the two variables.

In addition, change X label to "Miles per Gallon" and Y label to "Horsepower" and add a title "Horsepower vs. MPG" 

Data Visualization - Boxplot
========================================================

```r
boxplot(auto$mpg ~ auto$cylinders, data = auto, xlab = "Number of Cylinders", ylab = "Miles Per Gallon", main = "Mileage Data")
```

<img src="./r-programming-beginner-online-figure/boxplot.png" title="Data Wrangling" alt="Data Wrangling" width="80%" style="display: block; margin: auto;" />
Source: https://towardsdatascience.com/understanding-boxplots-5e2df7bcbd51

Data Wrangling
========================================================
Data wrangling, sometimes referred to as data munging, is the process of **transforming** and **mapping data** from one "raw" data form into another format with the intent of making it more appropriate and valuable for a variety of downstream purposes such as analytics. 

This may include further **munging**, **data visualization**, **data aggregation**, **training a statistical model**, as well as many other potential uses. 

Source: [Wikipedia](https://en.wikipedia.org/wiki/Data_wrangling)

<img src="./r-programming-beginner-online-figure/data-science-wrangle.png" title="Data Wrangling" alt="Data Wrangling" width="80%" style="display: block; margin: auto;" />

End of Session 2
========================================================
# Make sure you can 
* Use built-in datasets
* Summarise datasets (exp. Dataframe)
* Import CSV files from local folder as well as from remote location
* Plot histogram, boxplot, scatterplot, and barplot


To Be Eligible for Participation
========================================================
(1) Participate in the workshop.  
(2) Follow all the hands-on activities.  
(3) Create an R Notebook containing hands-on exercises.  
(4) Send the R Notebook file to qcl@cmc.edu (subject line: "QCL R Workshop - [Your Name] - [DATE]") as an attachment.


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
> - R Tutorial
https://datacarpentry.org/R-genomics/index.html


