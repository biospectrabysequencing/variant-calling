### Point 5 -- Data

The data for this project will consist of both simulated reads/sequences and actual biological reads and sequences.

#### Simulated Data

The use of simulated data is critical for assessing how each tool performs given very specific biases and error types. Using simulation, we can control with great precision both the type of bias to introduce as well as the amount of error in the data. Hence, generation of multiple levels of the independent variables as well as positive and negative controls is greatly facilitated. Since there are so many factors that contribute to the variability in alignment algorithms, we envision very many (thousands) of datasets to be constructed to tease out the various levels of the variables that will allow us to confidently benchmark the process. Key factors to be analysed include read type, read platform, read pairing, read length, insert size, read depth, GC bias, base quality, read quality, mapping quality, site depth, repeat content, allele frequency, and quality of the reference.

#### Existing Data

For the project we will use existing data that has been collected, or is planned to be, by the named researchers in the use cases. This data will derive from a variety of sources so that real examples of biological challenges can be assessed in the performance of the tools.

* Apple GBS dataset: >4500 apple accessions from the PFR cultivar breeding programme were geniotyped using GBS. 1200 of them were previsouly genotyped usng the 8k SNP array and grandparents were re-sequenced. 
* Snapper GBS
* Whole genome re-sequencing of manuka populations using pool sequencing. We are using the Illumina X Ten platform to generate >200X coverage of populations of 30 individuals. Our goal is to genotype at least 40 populations. 
* whole genome re-sequencing data for 10 apple (can get access to more than that with international partners) and 40 kiwifruit parents from the breeding programme at >30X read depth (Illumina Hiseq2000 sequencing from 2 years ago)
* Capture-based resequencing of tetraploid potato across and within populations developed as part of the clever culling discovery science project. Both individuals and pools at either 20,000 or 10,000 sites. This includes parents and some founders. There are/ will be over 300 lines individually (40X plus) and 50 pools of 20 siblings (150X coverage). Being capture-based the overlap should be more consistent than skim resequencing or GBS data. We will also have similar data for tetraploid kiwifruit next year. 
* Soybean data sets. Both WGS and GBS generated from the sames extraced DNAs (diploid, inbred) This is from the group at Lavall in Canada
* Willow data. These are polyploids of varying levels. (Larry Smart at Cornell)
* GBS data from various species from Tammy Steeves at Canterbury.

#### New Data generated

* What would be good for PFR??
*I think what would good would to evaluate the newest platforms for re-sequencing, eg Illumina Novagene6000 and PacBio Sequel long reads for polyploids. 
