---
title: "How to install the Robitools"
date: 2023-05-19T12:14:13-04:00
draft: false
author: "Sciathlon"
output: md_document
tags: ["Ecology", "Metabarcoding", "R", "Bioinformatics", "eDNA"]
---

# Introduction

The OBITools are a set of tools meant to format, edit, filter and analyze environmental DNA (eDNA) next generation sequencing (NGS) data in the command line using bash. They were developed at the Laboratoire d'Ecologie ALpine (LECA), in Grenoble, France. There are many other pipelines for metabarcoding data analysis, but if you choose these, so as long as you can format your files for the OBITools (a sometimes non-trivial task, I know...), they are fairly easy to get a handle on.

The ROBITools packages are the set of tools to use in R after using the OBITools in bash. We use them for further filtering, follow-up analysis/database formatting/analysis of in silico PCRs done from the tool ecoPCR. 

This post is a short tutorial on how to install the ROBITools on either a WINDOWS or a UNIX system, the two that I use regularly. 


# UNIX

Under unix it is all really straightforward.

1.	Install the latest version of R https://cran.r-project.org/bin/windows/base/ (find out if your computer is 64bit or 32bit to select the right one) install standard parameters
2.	Install Rstudio (you can skip this step if you prefer the command line)
3.	Install Rtools compatible with your R version https://cran.r-project.org/bin/windows/Rtools/ (do NOT skip this step!)
4.	Download the packages Robitaxonomy, Robitools, Robiutils, RObiBarcodes from this website: https://git.metabarcoding.org/obitools (sometimes the site is unaccessible, just wait until it is back online, it can sometimes take a few days depending on the bugs being fixed)
5.	Go to Tools->install packages-> install from CRAN and select XML, igraph, devtools OR on the command line type for each package "install.packages("package_name")
6.	If you forgot any of these packages it will not work!
7.	Go to Tools->install packages->install from package archive (.zip) and install the downloaded ROBItools packages in this order and if it doesn’t work mix them up, but this order worked for me (they throw crazy amounts of warnings, do not be alarmed):
  a.	ROBIUtils.tar.gz
  b.	ROBITaxonomy.tar.gz
  c.	ROBITBarcodes.tar.gz
  d.	ROBITools.tar.gz
8.	And now, normally you can load them using the “library() command.

# Windows

Under windows, there are a couple extra steps.

1.	Install the latest version of R https://cran.r-project.org/bin/windows/base/ (find out if your computer is 64bit or 32bit to select the right one) install standard parameters
2.	Install you favorite IDE if you want one, such as Rstudio (you can skip this step if you prefer the command line)
3.	Install Rtools compatible with your R version https://cran.r-project.org/bin/windows/Rtools/ (do NOT skip this step!)
4.	Download the packages Robitaxonomy, Robitools, Robiutils, RObiBarcodes from this website: https://git.metabarcoding.org/obitools (sometimes the site is unaccessible, just wait until it is back online, it can sometimes take a few days depending on the bugs being fixed)
5.	unzip these packages if they are not already (but make sure that the folders within like src are directly under the package name directory and not below in the arborescence of folders or it will NOT work (ex: ROBITaxonomy/src and not ROBITaxonomy/ROBITaxonomy/src)
7.	On Rstudio, go to Tools->install packages-> install from CRAN and select XML, igraph, devtools OR on the command line type for each package "install.packages("package_name")
8.	Load devtools by using the command “library(devtools)”
9.	Use the following commands, one by one (make sure that your path is correct! If the folders don’t have exactly the name you’re inputting, or are not in the working directory, modify the path. Alternatively, use the “files” finder and the “More->set as directory in the bottom right corner panel. And don’t forget the quotes. And if at some point one of them doesn’t work, do another one and come to that one later. Do the taxonomy one last. Hey, no one said it had to be easy right? Yes, I still love/hate Windows^^):
  a.	build(“ROBITools”)
  b.	build(“ROBITutils”)
  c.	build(“ROBITBarcodes”)
  d.	build(“ROBITaxonomy”)
10.	Go to Tools->install packages->install from package archive (.zip) and install the downloaded ROBItools packages in this order and if it doesn’t work mix them up, but this order worked for me (they throw crazy amounts of warnings, do not be alarmed unless it's a proper error):
  a.	ROBIUtils.tar.gz
  b.	ROBITaxonomy.tar.gz
  c.	ROBITBarcodes.tar.gz
  d.	ROBITools.tar.gz
11.	And now, normally you can load them using the “library() command

Until next time,
Sciathlon
