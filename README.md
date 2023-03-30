# Stukel et al manuscript data

Files are divided between the Kikihia and Maoricicada datasets

#### Data
`data` folders contain the data alignments used for phylogenetic analysis. 

`nuclear_loci_alignments` folders contain individual AHE loci alignments and concatenated alignments. The files beginning with `L` are the individual loci produced by the scripts in the `Simon-target-capture-pipeline` repository, after being further trimmed (hence the `*hmm`, see `scripts` folder). The `COMBINED.phy` file is a concatenated phylip alignment, which is associated with a `partitions.prt` file. The `COMBINED.nex` file is a corresponding nexus file with included partition information (used as input for SVDQuartets).

`mtdna_alignments` folders contain the mitochondrial genome alignments along with alignments for each individual mitochondrial gene, except for the trnas, which are combined together into a single file. The `partitions.prt` file is the partition file for the mitogenome alignment.

The `buckley_et_al_reanalysis_from_genbank` folder contains the alignment used for reanalyzing the nuclear genes only from Buckley et al. 2006. The sequences were downloaded from GenBank.

#### Scripts
`scripts` folders mainly contain the scripts used for aligning and trimming the alignments produced by the scripts in the separate `Simon-target-capture-pipeline` repository.

`exclude_few_taxa.sh` removes loci with fewer taxa than a cutoff threshold.

`hmmclean.sh` uses the program HmmCleaner to internally trim the alignments.

`mafft_align.sh` uses MAFFT to align and re-align alignments.

`customtrim.py` trims the ends of alignments to a certain missing data cutoff threshold. We used a threshold of 25% missing data, meaning that we trimmed from the ends to the first position with at least 75% of taxa having data at that position.

`concat.py` is the script used to concatenate the individual loci together into a phylip file with a corresponding partition file, or a nexus file containing partition information.

`compile_sh_trees.sh` is a script used later in phylogenetic analysis that uses `newick_utilities` to collapse internal branches of our individual gene trees based on a threshold, in our case SH-aLRT = 0, and then combine them into a single file containing all gene trees. These trees were used as input for ASTRAL and for concordance factor and internode certainty analyses.

#### Trees
`trees` folders contain the tree files and corresponding log files for all of our analyses.

`nuclear_concat`, `nuclear_astral`, and `nuclear_svdq` folders correspond to the concantenated ML, ASTRAL, and SVDQuartets trees and their analysis log files respectively.

`mtdna` folders contain the mitochondrial genome trees as well as the individual mitochondrial gene trees.

`mtdna_nuclear_combined` folders contain the trees inferred from concatenating the nuclear and mitochondrial genes together.

`concordance_factors` folders contain the nuclear trees annotated with gene concordance factors and site concordance factors.

`internode_certainty` folders contain the nuclear trees annotated with the three measures of internode certainty generated from the program `QuartetScores`.

The `buckley_reanalysis` folder contains the tree generated from only the nuclear genes taken from Buckley et al. 2006.

