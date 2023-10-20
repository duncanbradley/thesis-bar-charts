# Chapter 6: Axis Limits and Denominator Information Influence Magnitude Ratings in Bar Charts

* Data are in the `data` folder (this also contains the script for anonymising original data files)
* Analysis code is in the `axis-extension.qmd` (quarto) file

## Instructions for Using Docker To Generate the Manuscript Within a Fully-Reproducible Environment

This repository provides resources for re-creating the computational environment (R version, package versions) used for all data wrangling, data visualization, statistical modelling, and reporting. This will generate a fully interactive RStudio session, which will be running from a Docker container.

1. Download [Docker Desktop](https://www.docker.com) and launch it
2. Clone this repository to your local machine
3. Use the command line to navigate to the repository
4. Type `docker build -t thesis-bar-charts .` (where `thesis-bar-charts` is the repository name). This builds the Docker image.
5. Type `docker run --rm -p 8787:8787 -e PASSWORD=password thesis-bar-charts` to launch the Docker container.
6. In your browser's address bar, type `localhost:8787`
7. Enter `rstudio` as the username and `password` as the password. 
8. Open `axis-extension.qmd` and press Render to generate `axis-extension.pdf`

Note: Computationally intensive statistical models have been saved in `axis-extension_cache`. To speed-up rendering, these cached models are loaded instead of executing the code that generated them. To generate models from scratch, change the `eval_models` parameter in line 6 to `true`.

In case of a Sementation Fault error, add the following code to the script and then run `rmarkdown::render("axis-extension.qmd", output_file = "axis-extension.pdf")` in the RStudio console

```{r, setup-options}
knitr::opts_chunk$set(
  echo = FALSE, include = FALSE, warning = FALSE, message = FALSE
)
```
