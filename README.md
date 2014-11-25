NDL R Tutorial 
========================================================
author: Ryan Mears
date: March 24, 2014
transition: linear



Overview
========================================================

[Tutorial Webpage][Tutorial webpage]
[Tutorial webpage]: http://doesmindmatter.github.io/NeuralDynamics-RTutorial

*Working with data in R with the RStudio GUI*

- **Get** and **Shape** data into tidy arrangements
- **Analyze** and **Summarize** data with R packages
- **Explore** and **Present** with data visualization and publication quality tables and plots

Installing R and RStudio
====================================
type: section

R
====================================

Install [R][R-prog]
[R-Prog]: http://cran.us.r-project.org/

![The R Foundation for Statistical Computing][cranr]
[cranr]: NDL_R_tutorial-figure/CranR.png "The R Foundation for Statistical Computing"


RStudio
====================================

Install [RStudio][RS-Prog]
[RS-Prog]: http://www.rstudio.com/ide/download/desktop

![RStudio][cranr]
[cranr]: NDL_R_tutorial-figure/rstudio-mac.png "RStudio"


Get and Shape Data
====================================
type: section


Reading Data and Code
========================================================

  - read.csv()
```{r}
getwd()
```
  - source()
```{r}
getwd()
```


Data and Code in R
========================================================

- [data types][ARP-data]
  - vectors
  - arrays and matrices
  - data frames
  - lists
- [functions][ARP-fn]

[ARP-data]: http://adv-r.had.co.nz/Data-structures.html
[ARP-fn]: http://adv-r.had.co.nz/Functions.html


Create variables
========================================================
<small>
- c()
```{r}
hc_subjs <- c('sbj101','sbj102','sbj105')
sz_subjs <- c('sbj103','sbj104','sbj106')
```
- seq()
  - seq_len(6)  
  `r seq_len(6) `
  - seq(from = -2, to = 3, by = 1)  
  `r seq(from = -2, to = 3, by = 1) `
- rep()
  - rep(c('HC','SZ'), times = 1, each = 3)  
  `r rep(c('HC','SZ'), times = 1, each = 3) `
  - rep(c('HC','SZ'), times = 3, each = 1)  
  `r rep(c('HC','SZ'), times = 3, each = 1) `
</small>

Create variables
========================================================

```{r}
x <- seq_len(6)
subjs <- c(hc_subjs,sz_subjs)
cbind(x,subjs)
```

Create variables
========================================================
- cbind()
```{r}
  hc_2 <- cbind(hc_subjs,"hc")
  sz_2 <- cbind(sz_subjs,"sz")
  sz_2
```
***

- rbind()
```{r}
 grp_subjs <- rbind(hc_2,sz_2)
  colnames(grp_subjs)<-c("subj","group")
  grp_subjs
```

Examine variables
========================================================

- print() 
```{r}
print(hc_subjs)
```
- length()
```{r}
length(hc_subjs)
```
- dim()
```{r} 
dim(grp_subjs)
```


***

- str()
```{r}
str(grp_subjs)
```


Index and Select
========================================================

- Indices
```{r}
grp_subjs[1,1]
grp_subjs[1,]
```
***

- Booleans
```{r}
grp_subjs[,2]=='hc'
```

Index and Select
========================================================


- grep(), grepl(), gsub(), substr()


Convert and Combine
========================================================

- paste(), paste0(), cat()
- join()
- expand.grid()


Subset and Reshape
========================================================

- filter()
- select()
- reshape()
- melt()
- cast()
- **ply()

Analyze and Summarize
====================================
type: section


Compute Parameters
========================================================

- mutate()


Compare Means
========================================================

- ttest()

ANOVA
========================================================

- ezANOVA()

```{r, echo=FALSE}
plot(cars)
```


Explore and Present
========================================================
type: section


Plot
========================================================

- plot()
- ggplot()
- ggvis()

Present Results for Publication
========================================================

- stargazer()

Dynamic Documents
========================================================

- knit()

Resources
========================================================
type: subsection

- **Papers**
  - [Tidy Data][TD-P]
  - [Plyr][SAC-P] ([tutorials][P-T])  
- **Cheat Sheets**
 - [R][R-Cs]
 - ggplot [1][G2-Cs1] & [2][G2-Cs2]
 - Matlab to R [1][M2R1-Cs] & [2][M2R2-Cs]
- **Wikis**
  - [ggplot2][gg2-wiki] & [plyr][plyr-wiki] & [ggvis][ggvis-wiki]
  - [Advanced R Programming][ARP-wiki]

***

- **Webpages**
  - [QuickR][qr-web]
  - [Rseek][Rseek-web] & [CRAN-R][cranr-web] 
- **Books**
  - [GGPlot2][GG2-B]
  - [R in Action][RiA-B]
  - [The Art of R Programming][ARP-B]
  - [RStudio][RS-B]
  - [Lattice][L-B]
  - [R in a Nutshell][RN-B]


[TD-P]: http://vita.had.co.nz/papers/tidy-data.pdf "Tidy Data"
[SAC-P]: http://www.jstatsoft.org/v40/i01
[P-T]: http://plyr.had.co.nz/09-user/
[R-Cs]: http://cran.r-project.org/doc/contrib/Short-refcard.pdf
[G2-Cs1]: http://docs.ggplot2.org/0.9.2.1/index.html
[G2-Cs2]: http://www.ceb-institute.org/bbs/wp-content/uploads/2011/09/handout_ggplot2.pdf
[M2R1-Cs]: http://mathesaurus.sourceforge.net/octave-r.html
[M2R2-Cs]: http://cran.r-project.org/doc/contrib/Hiebeler-matlabR.pdf
[gg2-wiki]: http://ggplot2.org/
[plyr-wiki]: http://plyr.had.co.nz/
[ggvis-wiki]: http://ggvis.rstudio.com/
[ARP-wiki]: http://adv-r.had.co.nz/
[qr-web]: http://www.statmethods.net/
[Rseek-web]: http://rseek.org/
[cranr-web]: http://cran.r-project.org/web/views/
[GG2-B]: http://hollis.harvard.edu/?itemid=|library/m/aleph|012131369
[RiA-B]: http://hollis.harvard.edu/?itemid=|library/m/aleph|012941333
[ARP-B]: http://hollis.harvard.edu/?itemid=|library/m/aleph|012998891
[RS-B]: http://hollis.harvard.edu/?itemid=|library/m/aleph|013081378
[L-B]: http://hollis.harvard.edu/?itemid=|library/m/aleph|012131371
[RN-B]: http://hollis.harvard.edu/?itemid=|library/m/aleph|013621640
