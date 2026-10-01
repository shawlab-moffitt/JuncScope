# 2026.06.24 - AO
- [update] updated junctionDB table

# 2026.07.08 - AO
- [feature] QC step readout, is optional, is in config, will add extra time
- [feature] velocyto function added, is optional, is in config, will add extra time
- [feature] juncScope setup will now write out a slurm array batch job file

- [update] config file not required, can enter required command on comman line during project setup

- [bug-fix] Fixed NA barcode lines being output from only raw IDs available

- [to-do] Organize summarized result output
- [to-do] ~~Allow velocyto loom files to be made externally and included in input~~
- [to-do] ~~Derive intron/exon ratio per sample and per barcode from loom file~~
- [to-do] Generate easy to load in R Seurat output
- [to-do] Test scanpy single cell python library for clustering use

# 2026.07.10 - AO
- [update] Updated skeleton json config file with added parameters
- [update] Updated README.md tutorial setup and text
- [update] Conda environment now includes requirments for velocyto and scvelo steps
- [update] Allow velocyto loom files to be made externally and included in input
- [update] Derive intron/exon ratio per sample and per barcode from loom file
- [update] Adjusted barcode summary merge of all samples to include intron/exon ratio columns if available

- [bug-fix] Edited the slurm script output to be an independent environment. You can now deploy the batch script while inside you conda environment

# 2026.07.15 - AO
- [bug] ~~Running main script wthout `--setup-only` argument wrongly assumes running only one sample~~
	~~Error Text: TypeError: main.<locals>._run_one() missing 1 required positional argument: 'loom_file'~~

- [to-do] ~~Make output after setup more clear on run options~~
- [to-do] Check lst file format, see if full direct path required
- [to-do] Simplify setup commands, maybe make default settings for easier running

# 2026.07.22 - AO
- [bug-fix] Running main script without `--setup-only` argument wrongly assumes running only one sample
	Fixed. User can now run a list of bam files via config from initial command and bypass setup
- [bug-fix] Found and fixed issue when chromosome name may not include 'chr' prefix
- [bug-fix] Fixed 'bulk' mode summary functionality

- [update] Added spacing in setup output on commands for next steps
- [update] Removed loom stat output checking from verbose, was only temporary to debug
- [update] read_loom duplicate variable names warning is now hidden and reformatted to annotate the issue has been address in the code

- [idea] activate 'debug' mode

# 2026.09.17 - AO
- [bug] single-cell mode summary running with bulk data, not affecting output, but appearing as warning

# 2026.10.01 - AO
- [bug-fix] Regtools version checking was not extracting the correct string to get system version
- [bug-fix] When target junction is not in sample, or junction region does not have any reads, the sample workflow was breaking. Regtools step moved earlier and will be merged in with target junction data if present. If not, regtools will still write to separate outfile if enabled

- [feature] `count_barcode_read_totals` function added to count barcode read totals for QC
- [feature] `isoform_prop` function added to derive isoform proportions based on a user provided gene and junction names for each isoform

