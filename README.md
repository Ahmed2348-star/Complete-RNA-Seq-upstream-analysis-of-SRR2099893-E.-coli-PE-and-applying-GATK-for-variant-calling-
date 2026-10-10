# Complete-RNA-Seq-upstream-analysis-of-SRR2099893-E.-coli-PE-and-applying-GATK-for-variant-calling-
In this repository we will go through complete upstream of SRR2099893 (for further details upon the experiment:https://www.ncbi.nlm.nih.gov/bioproject/PRJNA241795)

A quality control check has been done using fastQC and trimming low quality reads is done by Trimmomatic. 

with hisat2-build we built the index of the reference genome (Escherichia coli K-12 MG1655.) and after building the index , the process of alignment is done and bam file generated.

featureCounts is used here for the quantification process 

it is important to note that we should download the GTF annotation file which should be compatible with the reference genome  

Here comes the function of GTAK. Five GATK functions used here: 

AddOrReplaceReadGroup : to add the required Read-Group metadata 

MarkDuplicates : to identify the PCR or Optical duplicate and mark them in the BAM file to handle them in the following steps.

CreateSequenceDictionary: to make .dict file of the reference genome which is required in the following steps. 

SplitNCigarReads: to split reads into exonic segments and hard-clip any overhanging portions.

HaplotypeCaller : the main GTAK function which will be call all the variant by comparing reads with the reference genome and provide the location of the SNP , Insertion , Deletion and the REF , ALT and Phred-scaled confidence in the variant call. 




