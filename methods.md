### Point 4 -- Outline of methods (at least 1 page)

During the application of these methods, we will work according to the guidelines of reproducible research \cite{ReproducibleResearch2017} best practices \cite{BestPractices2017} in computational biology that have been developed from the _Better Analysis Faster_ programme. Specifically, we will implement the 4 Pillars that have been shown to be key for developing a "Best Practice".

The approach we will take consists of a number of components which together will comprise the analysis toolkit. There are a variety of options for each step, therefore the identification of those options and evaluation in terms of fitness for purpose will be necessary.  Our approach will, initially, leverage existing software tools, data sets and expert knowledge of biological systems thereby allowing us to make rapid progress. As each of the components have been sufficiently evaluated, they will be used to develop the integrated testing platform. In order to maximise the ability of external collaborators to contribute to the framework, we will develop collaboratively and transparently, using software development best practices, sharing code through GitHub accounts that already exist. The framework will be deployable using standard cloud systems requiring few additional dependencies. Through this work, PFR staff will be upskilled in the use of common cloud computing tools, expanding PFRs computational capability.

#### Variant Calling Pipeline Identification and Characterisation
A set of variant calling pipelines suitable for this work is to be identified and characterised in terms of the relationships of their component parts and their dependencies on other software. This work has been started by the Biospectra-by-Sequencing project and is summarized below. (will send table as a word doc. I can't get the bloody thing coded right) We will be working directly with the developers of at least 3 of these pipelines which will allow us to leverage their detailed knowledge of those pipelines.  While this table has been constructed with pipelines suitable for GBS data, many of their components (e.g. aligners, variant callers, etc.) are used with standard resequencing projects for variant discovery and are applicable to the whole of this project. 

#### Cloud Integration Tool Evaluation

Deploying modern, cloud based software tools will allow us to develop, test and run analysis frameworks in a reproducible, automateble and self-documenting manner. Tools such as Docker containers will provide the software environment and unit of reproducibility. Control systems (e.g. Kubernetes) will manage multiple instances of Docker containers to allow for rapid analysis of large numbers of tests. Automation servers such as Jenkins will assist in both evaluating the frameworks as they are developed, and run those frameworks on our testing data sets as well as arbitrary data sets. PFR staff will work directly with NZ based cloud computing experts to rapidly and effectively take advantage of these technologies.

#### Pipeline Framework Evaluation
Developing the evaluation framework with the appropriate framework type will be critical. There are over a dozen possible framework types from which to choose \cite{Leipzig_2016}. The selection of the framework type is substantially dependent on the nature of the variant calling pipelines and the computational environments in which they will be run. Once the pipelines and computational environments have been characterised as described above, One or more of the available frameworks will be selected and a small pilot suitability study will be conducted.

|Pipeline Name|DOI|Year Published|Denovo / Reference|Demultiplexer|Trimmer / Read QC Filter|Aligner|SNP Caller|Special format of fastq filenames|Hardcoded enzyme|Download|Output file types|
|------|------|------|------|------|------|------|------|------|------|------|------|
|TASSEL UNEAK|10.1371/journal.pgen.1003215|2013|Denovo|Built In|None|N/A|Built IN|Yes|Yes|http://www.maizegenetics.net/tassel|hmp|
|STACKS|10.1111/mec.12354|2013|Denovo / Reference|Built In|Built In|BWA / Bowtie2 / GSnap|Built IN|No|Yes|http://catchenlab.life.illinois.edu/stacks/|Database with export.|
|IGST-GBS|10.1371/journal.pone.0054603|2013|Reference|FastX toolkit (https://github.com/agordon/fastx_toolkit)|FastX toolkit|BWA|sam tools (https://github.com/samtools/samtools)|No|?|Not publicly available|vcf|
|TASSLE 3|10.1371/journal.pone.0090346|2014|Reference|Built In|None|BWA / Bowtie 2|Built In|Yes|Yes|http://www.maizegenetics.net/tassel|hmp|
|pyRAD|10.1093/bioinformatics/btu121|2014|Denovo|Built In|Built in but only recommend for very messy single end GBS or ddRAD|Muscle|Built In|NO|No. Can specify enzyme cutsite overhang in parameter file|https://github.com/dereneaton/pyrad/releases|Text (.loci, .phy, .nex, .snps, .vcf and others),|
|AftrRad|10.1111/1755-0998.12378|2015|Denovo|Built In|Built in but just removes bad reads|Mafft|Built In|No|No needs recognition sequence|https://github.com/mikesovic/AftrRAD|Text (translation scripts)|
|GBS-SNP-CROP|10.1186/s12859-016-0879-y|2016|Both|Built In|Trimmomatic (trims before demultiplexing!)|BWA|samtools mpileup|yes and for each step name and location expectation|No needs recognition sequence|https://github.com/halelab/GBS-SNP-CROP|SNP matrix, TASSEL hmp, PLINK tped|
|GibPSs|10.1111/1755-0998.12510|2016|Denovo|Built In|Built in but just removes bad reads|Matching Built in|Built In|No|No needs recognition sequence|https://github.com/ahapke/gibpss|Database with export.|
|NGSEP|10.1186/s12864-016-2827-7|2016|Reference|Built In|Built in Removes adapter|Bowtie2|Built In|No|unknown|https://sourceforge.net/projects/ngsep/|vcf|
|FastGBS|10.1186/s12859-016-1431-9|2017|Reference|Sabre (https://github.com/najoshi/sabre)|Removes adaptor with cutadapt (https://github.com/marcelm/cutadapt/)|BWA|Platypus (http://www.well.ox.ac.uk/platypus)|Yes|Enzyme cutsite overhang is not checked|https://bitbucket.org/jerlar73/fast-gbs|vcf|
|ipyRAD|NA|NA|Denovo, Reference, Denovo+Reference|Built In|Built in|BWA / SMALT|Samtools/bedtools|No|No. Can specify enzyme cutsite overhang in parameter file|https://github.com/dereneaton/ipyrad|Varint VCF; ipyrad .loci; phylogenetic and structure (.phy, .nex and .str); SMARTPCA etc (.geno); MAP (.snps.map)|
|TASSEL 5|NA|NA|Reference|Built In|Built In|BWA / Bowtie2|Built In|Yes|Yes|http://www.maizegenetics.net/tassel|Database with export|


#### Data Sets

**In silico experiments**

Multiple genomic read aligners, assemblers, and variant callers will be assessed on their performance using many sets of simulated read data. The read data will be constructed by permutation from a “known-good” source, such as one of the human chromosomes. The controls will be sets of “perfect reads” (positive) generated as an idealization of the sequencing process, and sets of random reads (negative). Between the two extremes, many levels of read permutation will be examined allowing for variability in multiple factors including specified type, insert size, base quality (error rates), mapping quality, and allele frequency. The in-silico permutation process mimics the introduction of sequencing errors as well as the introduction of sequencing biases, the incorporation of a range of allele frequencies, and other sources of known problems in alignment algorithms. Due to our ability to construct our datasets with fine precision and then critically analyse the results, we will be able to ascertain the downstream affects of each type of problem. Each tool will be run on the sample data sets, and then the results evaluated using the appropriate standard criteria, including the ability to handle polyploid data correctly and efficiently.

**Biological Experimental Datasets**

Using biological, experimentally collected datasets, the same performance assessments will be completed. In these analyses, we will examine "real" data that will contain some but not necessarily all the problems manifested in the simulated data. However, it is critical that we also establish a close coupling between our constructed data and biologically sourced data for purposes of validation. 

#### Assessment of Variant Calls

Here again, we will leverage existing tools to provide a rapid start and then modify or extend them as needed. The software tool used to compare variant calling results in the 2016 paper by Torkamaneh et al has been made available by them for this project. The tools used at Cornell's Genomic Diversity Facility for reporting and visualising results of running the TASSEL and UNEAK GBS pipelines have been provided as well. 

In addition to the software tools mentioned above, the combination of sequence data sets, meta data about those data sets, and our collaborator's knowledge of the genetics of the organisms / populations from which the sequence data were derived will strongly contribute to the assessments conducted. 

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