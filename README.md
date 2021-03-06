# Scripts and data from Griffiths, J.S. et al. (in review) Evolutionary change in the Eastern oyster, *Crassostrea virginica*, following low salinity exposure.


Crosses were re-named for publication. The following table contains the cross name used in the manuscript and its associated naming scheme for sequencing and coding.
Cross | Coding_Name
--- | --- 
LA 1 | VB2 
LA 2 | VB3
LA 3 | VB3_R2
LA 4 | SL1 
LA 5 | SL2 
LA 6 | SL3 
LA 6 NS | SLNS3
TX 1 | AR2
TX 2 | AR3 
TX 3 | AR4 
TX 4 | AR5




## Fasta_Sequences_and_SNP_filtering

*Script*: q_trimgalore1_SE, q_bowtie_oysterbait, q_mpileup, q_popoo_make_synfile, q_stat_tests, SNP_filtering.sh

*Input files*: Raw reads found on NCBI (accession no.: PRJNA699020), *CROSS*-SE_exact_rc (e.g. AR20SE_exact_rc), *CROSS*-SE.fet (e.g. AR2-SE.fet), Supplemental_TableS1, Oyster-input-seq.fas

*Description*: Folder contains scripts for trimming raw sequences (q_trimgalore1_SE), aligning to Oyster-input-seq.fas, formatting files into mpileup format and syncfiles, andd finally running popoolation2 analyses (q_stat_tests), such as Fisher's exact test (example output file: *CROSS*-SE.fet) and the exact allele frequency estimates (example output file AR20SE_exact_rc). SNP_filtering.sh contains code for filtering SNPs from Fisher's exact test using starting frequency and increases in frequency post-selection.




## PCoA Analysis

*Script*: PCoA_oysters.R

*Input files*: all_pop_exact_cov20_200_new_rc_edit2, treatments_all.txt, treatments_larvae.txt, PCoA_larval_distances.txt

*Description*: Script contains code for running a Principal Coordinate Analysis for all samples (parents and larvae) and larvae samples only. The script also contains adonis functions for testing significance of groups. The treatments file contains treatment info for all samples. The distance file contains Manhattan distances for larval samples pre- and post-low salinity selection from the PCoA plot.




## Detecting increases in allele frequencies

*Script*: Manhattan_plot.R 

*Input files*: *CROSS*-SE_sig_edit5.fet (e.g. AR2-SE_sig_edit5.fet), cvirginica_exome_genome.txt

*Description*: After filtering output from Fisher's exact test (see SNP_filtering.sh script), this code will apply FDR correction on pvalues. It will then filter for significant genes where there are at least three significant SNPs per gene. Finally, data formatting is performed for plotting Manhattan plots for crosses that had genes under selection and crosses that did not. The file "cvirginica_exome_genome.txt" contains general genome/chromosome size info for the Manhattan plot.




## Annotation of Genes Under Selection

*Script*: Annotation.R

*Input files*: *CROSS*-SE_sig_edit5.fet (e.g. AR2-SE_sig_edit5.fet), Supplemental_TableS1

*Description*: Script contains code for determining if genes under seleciton for each cross were enriched in a particular functional or source category (information contained in the file "Supplemental_TableS1".




## SNP_position_Analysis

*Script*: SNP_position_enrichment_analysis.R

*Input files*: Annotated Probe Report for *CROSS*_start.txt (e.g. Annotated Probe Report for AR2_start.txt), Annotated Probe Report for *CROSS*_sig_SNPs.txt (e.g. Annotated Probe Report for AR2_sig_SNPs.txt), Supplemental_TableS1

*Description*: Script contains code for determining if genes under selection for each cross were more likely to be found upstream, downstream, or within the gene body. Input files contain SNP positions before selection (start files) and after selection for significant SNPs (sig files).
