---
date: "2021-02-27T16:50:16+02:00"
title: Data Types
output: 
  learnr::tutorial
weight: 7
---

The examples we have used in the 'How to Use R' section are all dealing with numbers (quantitative numerical data). Those of you familiar with programming will know that numerical objects can be classified as real, integer, double or complex. To check if an object is numeric and what type it is, you can use the `mode()` and `class()` functions respectively.

Let us go back into our R project and type the following into the open script file and run the code.😃


```r
x <- 1:10
mode(x)
```

```
## [1] "numeric"
```

```r
class(x)
```

```
## [1] "integer"
```

In R to enter strings of characters as objects you need to enter them using quote marks around them. By default it expects all inputs to be numeric and unless you use quote marks around the strings you wish to enter, it will consider them as numbers and subsequently will return an error message.


```r
x <- c("UK", "Spain", "Serbia", "France", "Germany", "Italy")
mode(x)
```

```
## [1] "character"
```

It is common in statistical data to have attributes also known as categorical variables. In R such variables should be specified as **factors**. An attribute variable has a set of levels indicating possible outcomes. Hence, to deal with x as an attribute variable with five levels we need to make it a factor in R.


```r
x <- c("UK", "Spain", "Serbia", "France", "Germany", "Italy")
x <- factor(x)
x
```

```
## [1] UK      Spain   Serbia  France  Germany Italy  
## Levels: France Germany Italy Serbia Spain UK
```

{{% notice note %}}
💡: Note that R codes the factor levels in their alphabetical order. However, attribute variables are usually coded and you would usually enter them as such.
{{% /notice %}}


```r
quality <- factor(c(3, 3, 4, 2, 2, 4, 0, 1))
levels(quality)
```

```
## [1] "0" "1" "2" "3" "4"
```

```r
quality
```

```
## [1] 3 3 4 2 2 4 0 1
## Levels: 0 1 2 3 4
```

You might need to deal from time to time with **logical** data type. This is when something is recorded as TRUE or FALSE. It is most likely that you would use this data type when checking what type of data the variable is that you are dealing with. For example


```r
x <- c("UK", "Spain", "Serbia", "France", "Germany", "Italy")
is.numeric(x)
```

```
## [1] FALSE
```

```r
is.factor(x)
```

```
## [1] FALSE
```

### Lists

Lists are the R objects which contain elements of different types: numbers, strings, vectors and another list inside it. A list can also contain a matrix or a function as its elements. List is created using `list()` function.

In the following example a, b and c are called tags which makes it easier to reference the components of the list.


```r
l <- list("a" = c("Jana", "Stana"), "b" = TRUE, "c" = 4:9, "d" = 100)
l
```

```
## $a
## [1] "Jana"  "Stana"
## 
## $b
## [1] TRUE
## 
## $c
## [1] 4 5 6 7 8 9
## 
## $d
## [1] 100
```

A List can be accessed in similar fashion to a vector. You can use `$` operator, alternatively you can use `[ ]` brackets. Indexing with `[` as shown below will give you a sub-list not the content inside the component. To retrieve the content, you need to use `[[`. However, this approach will allow you to access only a single component at a time. Note that both approaches are the same except that `$` can do partial matching on tags.


```r
str(l)
```

```
## List of 4
##  $ a: chr [1:2] "Jana" "Stana"
##  $ b: logi TRUE
##  $ c: int [1:6] 4 5 6 7 8 9
##  $ d: num 100
```

```r
l$a[2]
```

```
## [1] "Stana"
```

```r
l[[1]][2]
```

```
## [1] "Stana"
```

```r
l$c[2]
```

```
## [1] 5
```

```r
l[[3]][2]
```

```
## [1] 5
```

Remember that Indexing with `[` as shown above will give you a sub-list, not the content inside the component. To retrieve the content, you need to use `[[`.


```r
l["a"]  # single [ returns a list
```

```
## $a
## [1] "Jana"  "Stana"
```

```r
l[["a"]]  # double [[ returns the content
```

```
## [1] "Jana"  "Stana"
```

```r
l[4]
```

```
## $d
## [1] 100
```

```r
l[[4]]
```

```
## [1] 100
```

- indexing can be done recursively


```r
l$a[2]
```

```
## [1] "Stana"
```

```r
l[["a"]][2]
```

```
## [1] "Stana"
```

- no tags: use numeric indices


```r
k <- list(c("Jana", "Stana"), TRUE, 4:9)
str(k)
```

```
## List of 3
##  $ : chr [1:2] "Jana" "Stana"
##  $ : logi TRUE
##  $ : int [1:6] 4 5 6 7 8 9
```

```r
k[[1]][2]
```

```
## [1] "Stana"
```

```r
k[[3]][2]
```

```
## [1] 5
```

```r
l[["a"]] <- "name"
l
```

```
## $a
## [1] "name"
## 
## $b
## [1] TRUE
## 
## $c
## [1] 4 5 6 7 8 9
## 
## $d
## [1] 100
```

You can delete a component from a list by assigning `NULL` to it.


```r
str(l)
```

```
## List of 4
##  $ a: chr "name"
##  $ b: logi TRUE
##  $ c: int [1:6] 4 5 6 7 8 9
##  $ d: num 100
```

```r
l[["d"]] <- NULL

str(l)
```

```
## List of 3
##  $ a: chr "name"
##  $ b: logi TRUE
##  $ c: int [1:6] 4 5 6 7 8 9
```

Adding the new components is easy.


```r
l[["new_d"]] <- 101
str(l)
```

```
## List of 4
##  $ a    : chr "name"
##  $ b    : logi TRUE
##  $ c    : int [1:6] 4 5 6 7 8 9
##  $ new_d: num 101
```

To make changes to a list you simply replace the specific elements, as shown 

```r
l[["c"]][3:6] <- 106:109  
str(l)
```

```
## List of 4
##  $ a    : chr "name"
##  $ b    : logi TRUE
##  $ c    : int [1:6] 4 5 106 107 108 109
##  $ new_d: num 101
```

### Data Frames

Statistical data usually consists of several vectors of equal length and of various types that resemble a table. These vectors are interconnected across so that data in the same position comes from the same experimental unit, ie. observation. R uses data frame for storing this kind of data table and it is regarded as a primary data structure.

Let us consider a study of share prices of companies from three different business sectors. As part of the study a random sample (n=15) of companies was selected and the following data was collected:


```r
share_price <- c(880, 862, 850, 840, 838, 799, 783, 777, 767, 746, 692, 689, 683, 661, 658)
profit <- c(161.3, 170.5, 140.7, 115.7, 107.9, 135.2, 142.7, 114.9, 110.4, 98.9, 90.2, 80.6, 85.4, 91.7, 137.8)
sector <- factor(c(3, 3, 3, 3, 3, 2, 2, 2, 2, 2, 1, 1, 1, 1, 1)) # 1:IT, 2:Finance, 3:Pharmaceutical
#
share_price
```

```
##  [1] 880 862 850 840 838 799 783 777 767 746 692 689 683 661 658
```

```r
profit
```

```
##  [1] 161.3 170.5 140.7 115.7 107.9 135.2 142.7 114.9 110.4  98.9  90.2  80.6
## [13]  85.4  91.7 137.8
```

```r
sector
```

```
##  [1] 3 3 3 3 3 2 2 2 2 2 1 1 1 1 1
## Levels: 1 2 3
```

Rather than keeping this data as a set of individual vectors in R, it would be better to keep all the data as a single object, i.e. data frame.

```
share.data <- data.frame(share_price, profit, sector)
share.data
```

Individual vectors from the data frame can be accessed using `$` symbol:

```
share.data$sector
```

When working in R you will also come across a [tibble](https://tibble.tidyverse.org). A tibble (`tbl_df`) is a data frame providing a nicer printing method, useful when working with large data sets. One of the main differences is that a tibble can have columns that are lists.

Now, as we have mastered the basics let us learn how to access existing data from R.

-----------------------------
© 2021 Tatjana Kecojevic
