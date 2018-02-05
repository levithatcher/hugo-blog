+++
title = "Creating a simple R package"
date = "2015-11-29"
draft = false
showpagemeta = true
slug = "creating-r-package"
comments = false
+++

## Don't repeat yourself

Despite the [continued (and growing) excitement](http://blog.revolutionanalytics.com/2015/11/new-surveys-show-continued-popularity-of-r.html) about R, not everyone is well-versed on creating an R package. Why might this matter? Even if you’re not planning on submitting your code to CRAN or Github for others to see, a good software engineer strives to not repeat themselves. While in C# this means `classes`, `methods`, and `using` statements, in R this means (at a minimum) creating a package. (In a future post we’ll talk object oriented R code.) How does one make a package in R? Here’s a template using RStudio:

## Steps toward team-work

1) Click the Project dropdown in the top right of RStudio, select New Directory, and then select a R Package.

2) Set the package name, select its location, and select which .R source files will be a part of it. Click `Create Project`.

If you need a sample file and function, one can use this (within a file of any name):

```{r}
squares <‐ function(x) {
  return(x^2)
}
```

3) Clicking `Build and Reload` in RStudio builds the new package and loads it into the workspace–this is stated in the console and one can verify this under the Packages tab or by typing `search()` in the console. Note that `Build and Reload` also causes the package to appear under R’s library directory.

4) Verify you can call your function by typing (say) `squares(5)` in the console.

5) To double-check that the package can be called from anywhere, unload the package (mine is called RTesty) using:

```{r}
detach("package:RTesty", unload=TRUE)
```

6) Create a sample script in another directory, load the new project, and then make sure your function call works. Using my sample function above, this script was simply:

```{r}
library(RTesty)
squares(4)
```

And, of course, the console outputs 16. You've just started down a magical journey of code sharability.

Thanks for reading and, remember, don’t repeat yourself!