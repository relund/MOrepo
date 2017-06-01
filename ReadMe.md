
Multi-Objective Optimization Repository (MOrepo)
================================================

This repository is a response to the needs of researchers from the MCDM society to access multi-objective (MO) optimization instances. The repository contains instances, results, generators etc. for different MO problems and is continusly updated. The repository can be used as a test set for testing new algorithms, validating existing results and for reproducibility. All resarchers within MO optimization are welcome to contribute.

The repository has the following structure:

-   `instances` - A folder containing the instance sets. Each instance set in contained in a subfolder for each paper using the instances the first time.
-   `results` - A folder containing results for the instances. Results may be a set of nondominated points (or an approximation), upper and lower bounds etc. Results are not stored in the `instances` folder since different papers may have results for the same instances.
-   `misc` - A folder with stuff that cannot be included into the two folders above such as R packages, generators, converters etc.

Moreover a set of files in the root are included with documentation.

Maintainers of `MOrepo` are Lars Relund Nielsen, Sune Gadegaard, Thomas Stridsen and Kim Allan Andersen. Maintainers of instance sets, resluts etc. are Lars Relund <junk@relund.dk>, Thomas Stidsen <thst@dtu.dk>. Current contributors to the repository are S.L. Gadegaard, A Klose, L.R. Nielsen, Thomas Stidsen <thst@dtu.dk>.

Usage
-----

Instances can be downloaded in different ways depending on usage:

-   If you want the whole repository, download it as a zip file
-   Browse to a single instance and download it using the raw format at GitHub
-   Use the R package `MOrepoTools` to download instances

We recormend the last option and illustrate how it works. You don't need much knowledge about R to use the package. But of course it is preferable. You need [R](https://www.r-project.org/) and preferable [RStudio](https://www.rstudio.com/) installed on your computer. First you have to install the `MOrepoTools` package. From the R commandline write:

``` r
library(devtools)   # if the package is missing see ?install.package 
install_github("relund/MOrepo/misc/R/MOrepoTools/")
```

Now download instances and results using

``` r
library(MOrepoTools)
getInstance(name="SSCFLP", onlyList = TRUE)
getInstance(name="SSCFLP.*p6", onlyList = TRUE)
```

Problem classification
----------------------

Instances are classified into different classifications. The current classifications of MO optimization problems are:

-   Facility location
-   TSP

The set of problem classes is expanded as new problem instances is added to the repository. For instance problem classes may be

-   Knapsack
-   Assignment
-   Traveling salesman (TSP)
-   Set covering
-   Set partitioning
-   Set packing
-   Shortest path
-   Transhipment
-   Multi-commodity flow
-   Minimum cost network flow
-   IP/MILP (general problems with a mixture of constraints)

How to contribute
-----------------

All researchers are welcome to contribute to `MOrepo`. The repository mainly contains MO test instanses and results from variaous sources. However, also generators, format converters etc. related to MO optimization are welcome. Have a look at the documentation file [`contribute.md`](contribute.md) which describes different ways to do it.

<!-- ## Instance format 

 
 - Free MPS format
 - Raw with desc


meta.json content:

prefix: Prefix of the instances (equals folder name) (string)



## Solution format (JSON?)

A file named <instance_name>_sol<number>.json



instance: name of instance (string)
comments: misc comments about the results (string, null)
nDCard: Total number/cardinality of nondominated points (number, null)
suppCard: Number of supported nondominated points (number, null)
extCard: Number of extreme supported nondominated points (number, null)
critType: array of integer, real, null with length as number of criteria (array, null)
points: Array with nondominated points objects 0(array, null)
   
   A point object consists of 
   class: either us (unsupported), se (supported extreme), s (supported - may be extreme or nonextreme), sne (supported nonextreme), null (unknown)
   point: array of numbers
   
 (eller måske pointsClass i stedet for?)
optimal: (true, false, null)






## Validators


R package

- check a contribution
- download a set of test instances
- download solutions and plot
- download citation
- merge ndsets



 

 
 
## Instance numbering


## Biblography










The MCDM society would benefit from a joint multi-objective optimization repository with MOO instances and algorithms. In this talk we will present our ideas about the open-source Multi-Objective Optimization Repository (MOPR) and give an overview over current features and progress. The talk is also open for discussion about feature requests etc.   -->