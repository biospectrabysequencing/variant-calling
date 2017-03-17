### Point 4 -- Outline of methods (at least 1 page)

Throughout the section of methods we will work according to reproducible research \cite{ReproducibleResearch2017} best practices \cite{BestPractices2017} in computational biology that have been developed from the _Better Analysis Faster_ programme.

**in silico experiments**

Multiple genomic read aligners, assemblers, and variant callers will be assessed on their performance using many sets of simulated read data. The data will be obtained by permutation from a “known-good” source, such as one of the human chromosomes. The controls will be sets of “perfect reads” generated as an idealization of the sequencing process, for the specified type, with a specific allele frequency. The idealized reads will then be permuted in a fashion that mimics both the introduction of sequencing errors as well as the introduction of sequencing biases and the incorporation of a range of allele frequencies. Each tool will be run on the sample data sets, and then the results evaluated using the appropriate standard criteria, including the ability to handle polyploid data correctly and efficiently.

**biological experimental datasets**

Using biological experimentally collected datasets the same performance assessments will be completed.

**framework development**

In order to maximise the ability of external collaborators to contribute to the framework we will develop transparently, using software development best practices, sharing code through GitHub accounts that already exist.

The framework will be deployable using standard cloud systems requiring few additional dependencies.


Development external, using external system to facilitate transparency and accessibility of work with collaborators.

Development of Cloud capability.


#### scoping?

* IBD and Mendelian sanity checks
* pooling and population genetics
* genome free
* simulations
* GBS and resequencing
* polyploid
* making sense of reports - what methods here?
* visualisations
* confident curation.
