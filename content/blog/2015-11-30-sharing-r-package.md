+++
title = "Sharing an R package"
date = "2015-11-30"
draft = false
showpagemeta = true
slug = "sharing-r-package"
comments = false
+++

## Sharing is caring

Outside of posting your new R package to CRAN, how does one easily share a package with others? Even simply via email to coworkers or collaborators?
Since [we just talked about creating R packages](https://www.levithatcher.com/blog/creating-r-package/), let's learn how to share.

## Small steps toward a much better world

1) In RStudio open your package via the `Projects` menu in the top-right. This happens by either

- Selecting the project in the recent projects list or
- Looking for a local `Rproj` file in the package of interest

2) Navigate to the `Build` tab and click `More` -> `Build Source Package`

You'll then see something like this in the Console:

```
* checking for file 'RTesty/DESCRIPTION' ... OK
* preparing 'RTesty':
* checking DESCRIPTION meta‐information ... OK
* checking for LF line‐endings in source and make files
* checking for empty or unneeded directories
* building 'RTesty_0.1.tar.gz'
```

R and [devtools](https://cran.r-project.org/web/packages/devtools/devtools.pdf) is kindly helping to verify that your package meets minimum requirements for proper distribution. A new file will appear whose name ends with .tar.gz

3) Send this compressed tarball to your destination machine via email, etc. Put it in R’s library directory.

4) On the destination machine open RStudio and use install.packages on the newly-placed tarball. Note that R folder paths use forward slashes. Mine looks like this:

```{r}
install.packages("C:/Program Files/R/R‐3.2.2/library/RTesty_0.1.tar.gz", repos = NULL, type="source")
```

Note: this could also be done via `Tools` -> `Install Packages` -> under `Install from`, select `Package Archive File`

5) Verify that the package loads and works correctly by calling a function in the console (or in a script).

The library should load without errors and the output should match expectations. If you're following along, you can start with a super simple example like [this](https://www.levithatcher.com/blog/creating-r-package/).

_Note that it's highly advisable to push your code to a [remote repo like Github](http://happygitwithr.com/rstudio-git-github.html) (even if it's privately) so you're precious work isn't ever compromised by a hardware failure or stolen laptop._