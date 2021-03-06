---
date: "2016-04-09T16:50:16+02:00"
title: RMarkdown
output: 
  learnr::tutorial
weight: 9
---

### What is R Markdown?

R Markdown is a plain text file that has the extension <span style="color:red">.Rmd</span> It is: 

- [An authoring framework for data science](https://rmarkdown.rstudio.com/lesson-1.html)

- [A document format (.Rmd)](https://bookdown.org/yihui/rmarkdown/)

- [An R package named rmarkdown](https://rmarkdown.rstudio.com/docs/)

- [A file format for making dynamic documents with R](https://rmarkdown.rstudio.com/articles_intro.html)

- [A tool for integrating prose, code, and results](https://r4ds.had.co.nz/communicate-intro.html)

- [A computational document](http://radar.oreilly.com/2011/07/wolframs-computational-documen.html)

- Wizardry

[Alison Hill](https://alison.rbind.io) from [R Markdown Anatomy](https://rmd4medicine.netlify.com/slides/01-rmd-anatomy.html#1)

R Markdown can help generate:

- HTML documents
- Notebooks in which you’ve run code chunks individually
- PDFs that you can print out to follow along physically with the course
- This entire R course website

It enables you to:

- save and execute code and display its output
- create high quality reports that could include [LaTeX](https://www.latex-project.org/) equations

What is great about [R Markdown](https://rmarkdown.rstudio.com/) documents is that they are fully reproducible and support many static and dynamic output formats, to name a few: PDF, HTML, MS Word, Beamer...  You can incorporate narrative text and code of your data analysis to produce an elegantly formatted story telling journey.

It is a variant of [Markdown](https://daringfireball.net/projects/markdown/) that has embedded **R code chunks** (denoted by three back ticks), to be used with [knitr](https://yihui.name/knitr/) to make it easy to create reproducible web-based reports. 

To use **R Markdown** you will need to install the package from [CRAN](https://cran.r-project.org/) and load it with:


```r
install.packages("rmakdown", repos = "http://cran.us.r-project.org")
suppressPackageStartupMessages(library(rmarkdown))
```

#### 👉 Go to the following GitHub repo to download the material: <https://github.com/TanjaKec/RMd_Into>

### Starting with RMarkdown

**<span style="color:red">Task 1</span>:**
Open the file `RMarkdown_Intro.Rmd`

- Change the title of the Markdown Document from `My First Markdown Document` to `RMarkdown Introduction`.

-  Click the **"Knit"** button to see the compiled version of your sample code.


##### Congratulations! You’ve just Knitted your first Rmd document!!!! 👍😃

#### Basic Text editing

**<span style="color:red">Task 2</span>:**
Let’s format this document further by

- Changing the author of the document to your own name

- Rewriting the first sentence of the document to say "This is my first R Markdown document."

- Recompiling the document so you can see your changes

#### Adding a link

You can turn a word into a link by surrounding it in **hard brackets: [ ]** and then placing the link behind it in **parentheses: ( )**, like this:

`[RStudio](www.rstudio.com)`

**<span style="color:red">Task 3</span>:**
Make GitHub in the following paragraph link to https://github.com/DataTeka

#### Text formatting 

To embed formatting instructions into your document using Markdown, you
would surround text by:

- one asterisk to make it italic: *italic*

- two asterisks to make it bold: **bold** and

- backticks to make it monospaced: `monospaced`.

To make an ordered list you need to place each item on a new line after a
number followed by a period followed by a space:
1. order list
2. second item

💡! Note that you need to place a blank line between the list and any paragraphs
that come before it.

**<span style="color:red">Task 4</span>:**

- Make the following paragraph in your Rmd document look like this:

When analysing data,... The variables can be one of two broad types:

1) **Attribute variable**: are variables that have their outcomes described in terms of their characteristics or attributes;

2) **Measured variable**: are variables that have their outcomes taken from a numerical scale; the resulting outcome is expressed in numerical terms.

- Make the word Knit in the following paragraph italic.

#### Embedding the `R` code 
To embed an R code chunk you would use three back ticks:

<p><code  class="r"> ```{r} </code>

` chunk of code`

<p><code  class="r"> ``` </code>

**<span style="color:red">Task 5</span>**: Replace the `cars` data set with the `gapminder` data set. Don't forget to install and to load `gapminder` package using `install.packages("gapminder")` and `library(gapminder)` respectively.


#### Prevent printing of the `R` code

You can also embed plots by setting `echo = FALSE` to the code chunk to
prevent printing of the R code that generates the plot:

<p><code  class="r"> ```{r, echo=FALSE} </code>

` chunk of code`

<p><code  class="r"> ``` </code>

**<span style="color:red">Task 6</span>**: Replace the base boxplot of `mpg` vs. `cyl` by a `ggplot`'s boxplot to examine a relationship between `continent` and `lifeExp` (here we will use some of the `dplyr` functions too!).



```r
install.packages("dplyr", repos = "http://cran.us.r-project.org")
install.packages("ggplot2", repos = "http://cran.us.r-project.org")
suppressPackageStartupMessages(library(dplyr))
library(ggplot2)
# ggplot boxplot
ggplot(gapminder, aes(x = continent, y = lifeExp)) +
  geom_boxplot(outlier.colour = "hotpink") +
  geom_jitter(position = position_jitter(width = 0.1, height = 0), alpha = .2) +
  labs (title= "Life Exp. vs. Continent", 
        x = "Continent", y = "Life Exp.") +
  theme(legend.position = "none", 
        panel.border = element_rect(fill = NA, 
                                    colour = "black",
                                    size = .75),
        plot.title=element_text(hjust=0.5)) 
```

#### Adding **LaTex** equations

Finally, if you wish to add mathematical equations to your Markdown document you can easily embed [LaTeX]( LaTeX ) math equations into your report.

To *display equation* **in its own line** it needs to be surrounded by the double dollar symbol

`$$` `y = a + bx` `$$`, 

or to *embed an equation* **in line within the text** you would use only one dollar symbol: `$y = a + bx$`.

**<span style="color:red">Task 7</span>**: Display the equation in the *Including Mathematical Equations* paragraph into its own line.


#### Congratulations! You have got the basics to start creating your own fabulous dynamic documents… !!!! 👍😃


You would definitely find the following useful:

- [RMarkdown cheatsheet](https://www.rstudio.com/wp-content/uploads/2016/03/rmarkdown-cheatsheet-2.0.pdf)

- [The R Markdown Reference Guide](https://www.rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf)

- Book: [R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/)

- [Getting started with R Markdown](https://www.rstudio.com/resources/webinars/getting-started-with-r-markdown/)

- [R Markdown Quick Tour](https://rmarkdown.rstudio.com/authoring_quick_tour.html)

- [Advanced R Markdown – Tutorial::RStudio Conference 2017](https://www.rstudio.com/resources/videos/advanced-r-markdown-tutorial/)


-----------------------------
© 2021 Tatjana Kecojevic
