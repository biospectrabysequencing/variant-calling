### Point 4 -- Outline of methods (at least 1 page)

During the application of these methods, we will work according to the guidelines of reproducible research \cite{ReproducibleResearch2017} best practices \cite{BestPractices2017} in computational biology that have been developed from the _Better Analysis Faster_ programme. Specifically, we will implement the 4 Pillars that have been shown to be key for developing a "Best Practice".

**In silico experiments**

Multiple genomic read aligners, assemblers, and variant callers will be assessed on their performance using many sets of simulated read data. The read data will be constructed by permutation from a “known-good” source, such as one of the human chromosomes. The controls will be sets of “perfect reads” (positive) generated as an idealization of the sequencing process, and sets of random reads (negative). Between the two extremes, many levels of read permutation will be examined allowing for variability in multiple factors including specified type, insert size, base quality (error rates), mapping quality, and allele frequency. The in-silico permutation process mimics the introduction of sequencing errors as well as the introduction of sequencing biases, the incorporation of a range of allele frequencies, and other sources of known problems in alignment algorithms. Due to our ability to construct our datasets with fine precision and then critically analyse the results, we will be able to ascertain the downstream affects of each type of problem. Each tool will be run on the sample data sets, and then the results evaluated using the appropriate standard criteria, including the ability to handle polyploid data correctly and efficiently.

**Biological Experimental Datasets**

Using biological, experimentally collected datasets, the same performance assessments will be completed. In these analyses, we will examine "real" data that will contain some but not necessarily all the problems manifested in the simulated data. However, it is critical that we also establish a close coupling between our constructed data and biologically sourced data for purposes of validation.

**Framework development**

In order to maximise the ability of external collaborators to contribute to the framework, we will develop transparently, using software development best practices, sharing code through GitHub accounts that already exist.

The framework will be deployable using standard cloud systems requiring few additional dependencies.

Development external, using external system to facilitate transparency and accessibility of work with collaborators.

Development of Cloud capability.


#### scoping?

* IBD and Mendelian sanity checks: Built into the simulated reads?
* pooling and population genetics
* genome free: So what is the reference?
* GBS and resequencing: Could simulate these pretty easily.
* polyploid: Control of allele frequencies in simulated data?
* making sense of reports - what methods here?
* visualisations: Should address graphs of key metrics
* confident curation. ???

_These scoping suggestions could be elaborated on in these methods...Charles_

# Outline of methods/approach (at least one page)
The approach we will take to the work consists of a number of components which together will comprise the analysis toolkit.

## Pipeline Framework Evaluation
* Leipzig 2016

## Cloud Integration Tool Evaluation
* Docker containers
* Kubernetes cluster container managment
* Jenkins open source automation server

## Variant Calling Pipeline Identification and Characterisation
A set of variant calling pipelines suitable for this work need to be identified and characterised in terms of the relationships of their component parts and their dependencies on other software. This work has been started by the Biospectra-by-Sequencing project and is summarized below. (will send table as a word doc. I can't get the bloody thing coded right)
* Davy et al 2017 (BBS poster from PAG)
## Data Sets

## Assessment of Variant Calls
* Laval 2016
* Cornell Genomics Diversity Facility Reporting Code
* Biological reality check.
## Reporting
### Data
### Visualisation
### Baselines / Flags

