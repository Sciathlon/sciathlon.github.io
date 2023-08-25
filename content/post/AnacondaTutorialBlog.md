---
title: "Anaconda packages and environments for bioinformatics: a tutorial"
date: 2023-05-14
draft: false
tags: ["Anaconda", "Bioinformatics", "Install", "Software"]
---

After abandoning this blog for several years I am back with different
content. I want to write tutorials on what I've learned doing
bioinformatics since I started my PhD, among other things and might be
interesting or helpful to others. I started using anaconda during my
postdoc in genomics and I use it every single day.

Today, I wanted to write a summary of things I've learned using anaconda
packages and environments for bioinformatics (but the same commands will
work for other types of packages as well). This is not a python tutorial
though. What I will show is information already available online, but it
is a compilation of what I found useful over the years in my day to day
work so it may save someone some time. There are quite a few things I've
learned in the past year that I wish I had known when I started, so here
they are.

# What is Anaconda ?

Anaconda is a distribution of python that was first introduced to create
a platform for python data science open source packages and libraries.
You can find more information about the company here:
<https://www.anaconda.com/about-us> . It simplifies package deployment
and management when you are doing dev, but it is also a source for so
many of the tools we use in bioinformatics and avoids the annoyingly
complex installs of the dozens to hundreds of tools we need to use for
our work. Not every single tool is installed there, and some distros are
not up to date or have issues (looking at you Augustus, you
headache-making demon) but most of the time it will save you hours to
days of problems.

# Why use Anaconda ?

-   You use it to install tools for data science including
    bioinformatics
-   It works on Windows, Linux, MacOS
-   It will avoid countless hours of install nightmares
-   You can use it to create separate environments so you don't have
    conflicts between versions of dependencies
-   It is super easy to install and use
-   It has most of your bioinformatics software needs
-   If you install the GUI, it comes with the Spyder IDE, which is my
    favorite if you code in python
-   The community is amazing!

Additional info from the company here:
<https://www.anaconda.com/why-anaconda> .

# What are some of the issues I need to be aware of ?

-   As I mentioned before, not every single soft you need is installed
    on it. For example in genomics, you can't install genemarkES or
    signalp6 with it because of the licensing.
-   Some software versions don't work anymore because of dependencies
    that are broken or incompatible
-   Less and less people seem to be relying on conda packages now and
    updating their packages because more and more people use Docker or
    Singularity images (but those are so annoying to setup sometimes!)
-   Anaconda vs miniconda (see below)
-   Some clusters don't have them, depending on your university or lab,
    because they can introduce safety liabilities. Many admins ban them
    (If they are angels and install all the tools we need themselves I'm
    ok with it, but generally it makes my life more difficult!)
-   if you use conda instead of mamba it can take absolute ages to
    download and install (see below)

# Conda install and most useful commands

## Install conda on your server or local machine

If you're not using the command line (which you shall remedy asap if
it's the case, because learning how to use it is fast and it will serve
you for the rest of your career so might as well get it over with now!)
you can find the distro here in the meantime which will install the
Anaconda distro of python you can use on the command line along with the
Spyder IDE if you're a GUI only:
<https://www.anaconda.com/download#downloads>

If you are using the command line:

-   On Windows I would advise you use either the command line from the
    WSL (Windows linux subsystem, you'll find plenty of tutorials online
    for your distro of Windows) or download git bash command line tool
    here: <https://git-scm.com/downloads> . I use both, I always loved
    the git bash one though. Then follow instructions below.
-   On Unix/Windows bash or WSL

The first thing you need to know about using conda is that unless you
have a very good reason, don't download anaconda but use miniconda
instead. It will save you from annoying headaches of dependency
incompatibilities, trust me.

    #Download the newest install file (just replace the name of the file after checking which version you want in the command below)
    cd /path/to/where/you/want/to/install
    wget https://repo.anaconda.com/miniconda/Miniconda3-py310_22.11.1-1-Linux-x86_64.sh
    #install
    bash Miniconda3-py310_22.11.1-1-Linux-x86_64.sh

During the install it asks you if you want to add conda to your path,
say yes. If something goes wrong you can do it using this:

    export PATH=/path/to/miniconda/miniconda3/bin:$PATH

    #export will put the path during the current session only, if you want the path to always be available you need to put it in your bashrc like so:
    source ~.bashrc

Normally conda is initialized during install, but in case something goes
wrong:

    conda init

If you don't remember which version you installed if it's been a while:

    conda --version

## Installing packages and creating environments

In this section I will indicate how to install conda packages and
environments using the command line as well as some useful options and
using examples of software I've installed. Read the whole section before
starting you installs!

Before you do anything, install mamba in you base conda, it will speed
up all your installs like you wouldn't believe and it's so much better
for solving issues between dependencies.

    conda install mamba -n base -c conda-forge

Installing a package in an existing environment (if you don't have one
loaded it is going to be installed in base, and generally you don't want
that, so be careful!):

    mamba install -c channel_name package_name

Creating environments:

    #Create a new environment with 1 or more packages
    mamba create  -n environment_name -c channel package_name1 package_name2 ...

    #Or if you don't have mamba:
    conda create  -n environment_name -c channel package_name1 package_name2 ...

    #Example with a single package:
    mamba create -n  busco -c conda-forge -c bioconda busco

    #Example with multiple packages:
    mamba create -n LongAssemb -c bioconda -c conda-forge -c defaults flye canu

Some installs are more complex and require a little more than that so
you can create the environment then install software inside it (make
sure you load the environment when you do!). Example with spades:

    mamba create -n spades python
    conda activate spades
    pip install spades
    conda deactivate

An example of an even more complex install here with Trinity:

    mamba create -n Trinity 
    conda activate Trinity
    mkdir softs/Trinity
    cd softs/Trinity
    wget https://github.com/trinityrnaseq/trinityrnaseq/releases/trinityrnaseq-v2.15.1.FULL.tar.gz
    tar -xvf  trinityrnaseq-v2.15.1.FULL.tar.gz
    make
    export TRINITY_HOME=/export/home/gaia/astewart/softs/Trinity/trinityrnaseq-v2.15.1
    mamba install --name Trinity  -c bioconda -c conda-forge samtools
    mamba install --name Trinity  -c bioconda -c conda-forge bowtie2
    mamba install --name Trinity  -c bioconda -c conda-forge jellyfish salmon
    mamba install --name Trinity -c conda-forge numpy

If you need specific versions of a software, specify it as so:

    mamba create -n eukrep -c bioconda scikit-learn==0.19.2 eukrep

To save time add the -y option to say yes to installing all the
dependencies

     mamba create -y -n environment_name-c channel_name package_name

If ever you need to remove an environment and all the software in it:

    conda env remove -n environment_name

Here I've shown everything with python3 in mind but you can load python2
in a separate environment:

    conda create -n python2env python=2

## Other useful commands

To list all the packages installed in your conda:

    conda list

To list all the environments installed in your conda:

    conda env list

To search for all the available versions of a software:

    conda search package_name

updata a version of a package (if inside an environment, activate it
first):

    conda update package_name

To update all packages in the env:

    conda update --all

To update conda:

    conda update -n base -c defaults conda 

For more info and commands see here:
<https://docs.conda.io/projects/conda/en/4.6.0/commands/info.html>

## To activate environments and use packages installed in them

In the command line:

    conda activate environment_name

In a script:

    source /path/to/miniconda3/bin/activate environment_name

To deactivate the environment you are in:

    conda deactivate

## To remove conda install

If you really need a clean install with nothing left you can use this:

    conda install anaconda-clean
    anaconda-clean (--yes option if you want to remove everything and don't want to be prompted for every packages)

But if you don't require a clean uninstall just use this to remove the
conda folder with all its contents:

    rm -rf dir_name

# Conclusion

Of course not everything is here, but most of what I've needed or
encountered is here. If you have trouble with anything, keep the reflex
of googling your error message, and go from there. Only after you've
exhausted every relevant thread, you can try posting a question on
StackOverflow <https://stackoverflow.com/>, Anaconda forum
<https://community.anaconda.cloud/> or a similar community, I know there
are discord servers where you can post as well. If you have colleagues,
server admins or friends who you can ask it's even better=) Anyway, I
hope this serves a purpose, at least for me it's a way to have
everything in one place. 
Till next time, cheers, 
Sciathlon.
