---
title       : "Introducing Shiny and RStudio"
subtitle    : 
author      : "Assa Yeroslaviz"
job         : "Dept. Computatational Biology"
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax, quiz, bootstrap, interactive]  # {mathjax, quiz, bootstrap}
ext_widgets : {rCharts: [libraries/nvd3, libraries/leaflet, libraries/dygraphs]}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
logo        : bioinfo-core.jpg
assets      : {assets: ../../assets}

--- .class #id

<style type="text/css">
body {background:grey transparent;
}
</style>

## Topics

1. why RStudio?
2. Creating presentations with R.
3. why using Shiny?
4. Advantages of using Shiny.
5. examples.

--- 


## RStudio

RStudio offers multiple advantages compare to the normal terminal / command line 

<font color="#3366ff">
  <b>user friendly and easy-to-use IDE </b>
</font>

![GUI](https://s26.postimg.org/g1f9iy5ah/Rstudio.png)

---

## RStudio

RStudio offers multiple advantages compare to the normal terminal / command line 

<font color="#3366ff">
<b> source codes, STDOUT, images and results are in the same windows. </b>
</font>

<img class='center' src='https://s26.postimg.org/t4aw27vih/Rstudio1.png' height=450px width=600px />

---

## RStudio

RStudio offers multiple advantages compare to the normal terminal / command line 


> - Open source
> - It runs on every OS and there is a <font color="#3366ff">server version</font>
> - Various features adn add-ons to increase efficiency. 
> - Continuously under development but very stable. 


---

## RStudio

RStudio offers multiple advantages compare to the normal terminal / command line 

> - using the projects in RStudio you can isolate code and results from diﬀerent projects.	
> - Restart where you left oﬀ.
> - Have all the output under one roof (the R environment,  the object, the plots, etc. )
> - it can automatically creates documentation of your results, comments etc.
> - can creates html, pdf  or word documents
> - presentations are also possible

---.segue bg:grey

## Creating presentation using RStudio

---

## ioslides

- based on the [rmarkdown](http://rmarkdown.rstudio.com/) language.

![](./assets/img/rmarkdown.png)

-it has several layouts and advanced options. 

--- 
## ioslides

<b> header </b> 


```r
---
title: "Introducing Shiny and RStudio"
author: "Assa Yeroslaviz - Dept. Computational Biology"
output: 
  ioslides_presentation:
        widescreen: true
        transition: faster
---
```

---

## ioslides

<b> Slide with Bullets </b>

- Bullet 1
- Bullet 2
- Bullet 3

---

## ioslides

<b> Slide with R Output </b>


```r
summary(cars)
```

```
##      speed           dist       
##  Min.   : 4.0   Min.   :  2.00  
##  1st Qu.:12.0   1st Qu.: 26.00  
##  Median :15.0   Median : 36.00  
##  Mean   :15.4   Mean   : 42.98  
##  3rd Qu.:19.0   3rd Qu.: 56.00  
##  Max.   :25.0   Max.   :120.00
```

---

## ioslides

<b> Slide with Plot </b>


```r
library(ggplot2)

sizes <- expand.grid(size = (0:3) * 2, stroke = (0:3) * 2)
ggplot(sizes, aes(size, stroke, size = size, stroke = stroke)) + 
  geom_abline(slope = -1, intercept = 6, colour = "white", size = 6) + 
  geom_point(shape = 21, fill = "red") +
  scale_size_identity()
```

<img src="figure/unnamed-chunk-2-1.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />

---  .class #id

## slidify

advanced possibilities for interactive presentations

for more information see [slidify](http://slidify.org/) (http://slidify.org/)

similar functionality as Latex


--- 

## Install packages

- `Slidify` works in R, so you need to download [that](http://cran.r-project.org) if you haven't yet.
- You also need to make sure you have all of the necessary dependencies installed on your computer
- Open R and copy and paste the following code into the console (you only need to do this once)


```r
install.packages("devtools")  
install_github('slidify', 'ramnathv')  
install_github('slidifyLibraries', 'ramnathv')
```

--- .segue .dark 

<q> <font color="white"> A framework is a collection of stylesheets, javascripts and layouts that control the style and appearance of a slide deck. </font> </q>


--- .centrepre &vcenter bg:lightgoldenrodyellow

## frameworks

    ---
    title: Frameworks
    framework: revealjs
    mode: selfcontained
    ---
     
    ## Slide 1
     
    Some content
     
    --- 
     
    ## Slide 2
     
    Some content

--- 

## frameworks

<iframe src='./demos/frameworks/solarized/index.html'></iframe>

---

## frameworks

<iframe src='./demos/frameworks/vertical/index.html'></iframe>

---

## Publishing

slidify allows the user to directly publish or share the results as well as the analysis method via different repositories.
This is easily done with e.g. 

- [github](github.com)
- [rpubs](rpubs.com)
- [dropbox](dropbox.com)


```r
library(slidify)
publish_github("myDeck", username="frymor")
```

```
## Publishing deck to frymor/myDeck
```

```
## You can now view your slide deck at http://frymor.github.com/myDeck
```










--- &twocol

## 

### Two Columns

This text should span the entire slide.

*** =left

## Left

This text should float to the left.

*** =right

## Right

This text should float to the right.

---

## Read-And-Delete

1. Edit YAML front matter
2. Write using R Markdown
3. Use an empty line followed by three dashes to separate slides!

--- .class #id 

## creates a presentation


slidify





