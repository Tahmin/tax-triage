CLI Parameters Possible and Explained
Parameter	Description
--input <samplesheet.csv_path>	CSV file containing samplesheet information for each sample. See Samplesheet section
--outdir <path_to_output_to_be_made>	Output folder.
--fastq_1 <path/to/fastq_1>	Path to the first read file (FASTQ format) for single-end or paired-end sequencing. If --input is not provided, this is required to dynamically generate a samplesheet.
--fastq_2 <path/to/fastq_2> (optional)	Path to the second read file for paired-end sequencing. Optional — if not supplied, data is treated as single-end.
--platform [ILLUMINA,OXFORD,PACBIO]	Sequencing platform used for the data. Defaults to ILLUMINA if not specified. This helps determine appropriate preprocessing steps.
--trim	Flag for Whether the reads should be trimmed prior to downstream processing. Accepts "true" or "false". Defaults to false.
--type <str>	Sample type or classification (e.g., blood, stool) Optional — can be used for filtering or labeling during analysis.
--sample <sample_name>	Sample identifier used in the dynamically generated samplesheet. Defaults to "sample" if not specified. Useful for single-sample runs without an input CSV.
--sequencing_summary <path/to/summary.txt>	Optional path to a sequencing summary file (e.g., from Nanopore runs). This is only used for specific preprocessing or reporting steps if applicable.
--use_denovo	Performing the de-novo assembly process. Currently this is recommmended as MEGAHIT for short reads and FLYE for long reads. Disabled by default
--reference_assembly	Perform the reference-based assembly on reads against top hit assemblies or assemblies provided as a local file. Performes variant analysis by default. Disabled by default
--skip_fastp	TRUE/FALSE, do not filter with fastp
--skip_plots	TRUE/FALSE, do not make any plots
--remove_taxids  <numbers[]>	"taxidA taxidB..." a list of one or more taxids to remove from the kraken report prior to downstream analysis. Use "9606" for human reads
--compress_species	TRUE/FALSE, (default: FALSE) Compress all taxonomies in the ODR to the species level. By default, all organisms mapped to the pathogen sheet and NCBI's assembly file will be present per row if present in the sample.
--show_commensals	TRUE/FALSE, Do/Don't (default: Don't) show commensals in the final report
--show_potentials	TRUE/FALSE, Do/Don't (default: Don't) show potential pathogens in the final report
--show_unidentified	TRUE/FALSE, Do/Don't (default: Don't) show unknown or unannotated pathogens in the final report
--k2_confidence  <numbers[]>	Minimum confidence to classify a read using KRAKEN2 only. See here for more information.
--organisms  <numbers[] or strings[]>	Organisms list (names or taxids) you want to pull from to get a reference. Used if you are skipping kraken2 only. Separate by a list of spaces like "1254 573"
--fuzzy	TRUE/FALSE, Match names of organisms by their names (enabled) rather than taxids
--get_pathogens	TRUE/FALSE, Use the pathogens sheet FASTA file instead of k2's top hits. Default is FALSE
--skip_realignment	TRUE/FALSE, Skip realignment step. You will not get a metrics report as a result
--skip_kraken2	TRUE/FALSE, Skip kraken2. If you do not provide a --reference_fasta value and you enable this skip then your pipeline will fail.
--pathogens	OPTIONAL. Enable pathogen discovery mode. See assets/pathogen_sheet.txt for the default sheet. You can ue your own designation so long as it is in the same format as the provided example. This is an ongoing list of annotated known human-pathogens that are mapped to your alignments. Requires alignment to be performed. The "test" config profile automatically uses this.
--distributions	This is set, by default to use this file. However, if you have your own set of distributions for any number of species and their abundances, please specify it here. For example, run --distributions assets/taxid_abundance_stats.hmp.tsv.gz for the default. The file can be either in the .tsv.gz format or a decompressed .tsv
--add_irregular_top_hits	Adds irregular distributions (outside percentile zscore) to top hits. Default is fale and only pathogens and top abu hits are considered
--skip_multiqc	TRUE/FALSE, Skip multiqc final report
--minq <number>	What minimum quality would you want in your samples. Disabled if you run --skip_fastp. Default is 7 for Oxford Nanopore, 20 for Illumina
--minmapq <number>	What minimum mapping quality would you want in your sample alignments. Default is 5
--mmap2_window <number>	What window size to use for alignment with minimap2. Default is 10 for minimap2 if disabled.
--mmap2_fraction_filter <number>	filter out top FLOAT fraction of repetitive minimizers. Default is 0.0009 if disabled.
--organisms_file <file>	A single file that contains what organisms (name or taxid) you want to pull. You can enable this if you are skipping kraken2 as well
--subsample <number>	Take a subsample of n reads from each sample. Useful if your data size is very large and you want a quick triage analysis
--downsample	Uses the BBNorm submodule within the bbmap suite (JGI) to reduce redundant reads to downstream analysis. Useful for deep sequencing samples (e.g. 40 GB of reads per sample)
--reference_fasta <filepath>	Location of a single reference fasta, multiple files (separate by space and within quotations ""), or a directory of fasta files to run alignment on RATHER than (or in addition to) downloading references from NCBI from post K2 or manual organism taxids/names. Useful if you know what you're looking for or have no internet connection to pull said references. Header format must be in the "all" format from NCBI's ftp assembly site and should be ">accession description" where there is a space following the accession with the organism chr/contig description of the sequence. Technically, the accession does not matter as the pipeline only needs to match the organism space that follows the first space in the header. Example: >NC_003663.2 Cowpox virus, complete genome
--recursive_reference	TRUE/FALSE (default). Search recursively through a directory provided in the --reference_fasta parameter
--db <path_to_kraken2_database>	Database to be used. IF --low_memory is called it will read the database from the fileystem. If not called, it will load it all into memory first so ensure that the memory available (limited as well by --max_memory is enough to hold the database). If using with --download-db, choose from download options {minikraken2, flukraken2} instead of using a path. See here for a full list
--download_db	Download the preset database indicated in --db to --outdir
--download_taxdump	Download the nodes and names.dmp from ncbi taxonomy. Adds the genus to the report pdf taxonomic id column
--taxdump	DIRECTORY. Use a local nodes and names.dmp from ncbi taxonomy. Adds the genus to the report pdf taxonomic id column
--sensitive	Sensitive mode for confidence metrics. Uses all BAM query alignments rather than the reference from the alignment. Considered I/O intensive and much slower. Useful if there are a lot of variants present in the alignments, otherwise keep disabled
--metaphlan	Use Metaphlan. Must specify a database path that contains .pkl and .btl2 (bowtie2 index) files
--max_memory <number>GB	Max RAM you want to dedicate to the pipeline. Most of it will be used during Kraken2 steps so ensure you have more memory than the size of the --db called
-latest	Use the latest revision (-r). If you want to autopull the latest commit for a branch from https://github.com/jhuapl-bio/taxtriage, specify this. Used in Basestack and the Cloud (default toggle)
--low_memory <number>	If you don't have enough memory to load the kraken2 db, call this to read it from the filesystem for each read. THIS IS MUCH SLOWER THAN THE DEFAULT METHOD
--max_cpus <number>	Max CPUs you want to dedicate to the pipeline
--gini_weight <number>	Gini Weight to the TASS Score. This is the measure of how spread out the depths/coverages are in an alignment to an organism. The more spread out or evenly distributed the regions, the higher the score.
--breadth_weight <number>	Minimum Log-based breadth weight for TASS Score calculation
--minhash_weight <number>	Weight for minhash filtering. It is the combination of % of reads removed + % of breadth new / 2
--mapq_weight <number>	MapQ Weight to the TASS Score. If filtering on 20+, this will likely all be 1 or close to 1. Disabled by default
--hmp_weight <number>	TASS Score weight for HMP percentile, recommend disabling if sample is unknown
--disparity_score_weight <number>	The weight for giving more of a bonus for more prevalent organisms. Unused by default
--dispersion_factor <number>	TASS Score Dispersion factor. This is the measure of how spread out the depths/coverages are in an alignment to an organism. The more spread out or evenly distributed the regions, the higher the score.
--reward_factor <number>	TASS Score Reward factor. This is the measure of how spread out the depths/coverages are in an alignment to an organism. The more spread out or evenly distributed the regions, the higher the score.
--top_per_taxa "<taxid:amount:rank>"]	One or more 3 element values for the minimum taxa at a rank. Example "10239:20:S 2:20:S" is minimum 20 virus species (10239 is Virus) AND (separated by space for a new definition) 20 Bacteria (2) species. Possible Rank codes to use are the single alphabet letter: G(enus),S(pecies),P(hylum),F(amily),O(rder),C(lass)
--genome	Pull one of the pre-made igenomes databases for host removal. Available list at here or here (aws cli or curl command) to download them locally
--remove_reference_file	Remove all reads that align to a set of accessions in a single fasta file
--demux	If your Samplesheet contains a folder (rather than 1-2 fastq files), you MUST call this flag
--use_megahit_longreads	If running denovo assembly, use MEGAHIT for longreads. Default is disabled = FLYE
--decompress_pre_megahit	Some HPC envs cant use megahit with gz files, enable if this is the case or you experience INPUT/OUTPUT errors at this step.
--top_hits_count	Minimum taxa to filter out per rank level. If top_per_taxa specified, whatever is the larger of the 2 values for the results takes priority.
--get_features	Pull Features (CDS) for each assembly present. Performs Coverage on each feature
--min_conf <number>	Minimum confidence to appear within the pdf report (ODR)
--use_bt2	Use Bowtie2 instead of minimap2 for Illumina reads
--get_variants	Perform mpileup on your assemblies against your reads. Disabled by default. Auto-called if you are doing a reference-based assembly
-resume	Resume the run from where it left off. IF not called the pipeline will restart from the Samplesheet check each time
-r [main, stable, etc.]	Specify the branch/revision name to use if pulling from github (not local main.nf file)
-profile [local,test,test_viral,docker,singularity]	Default profile, 2 tests, Docker, or Singularity for execution reasons
⚠️ Please note that for the --reference_fasta parameter, you MUST use the designated header format from the FTP site that NCBI hosts for assemblies at here. This format should looke like:

>NC_003663.2 Cowpox virus, complete genome
In this case, the accession (can be any value, default is NCBI's nt or refseq acc) is followed by a space and then the organism name. The pipeline must "fuzzy" match the organism name from this header from the assembly summary file (see NCBI's assembly file here) to understand how the parsing happens in regards to an organism.

Important output locations
report: Organism Discovery Report PDF, MultiQC, Krona Plot (from Kraken2), Microbial Detection Txt File
Combined ODR - all.organisms.report.pdf
Sample ODR - <samplename>.organisms.report.pdf
MultiQC - multiqc_report.html
Microbial Sheet - <samplename|all>.report.txt
Krona - combined_krona_kreports.html
alignments: Post minimap2 alignment to top hits or local reference fasta file(s). Also contains histograms of coverages
Histogram (v1.3.0 or later) - <samplename>.histo.txt
BAM - <samplename>.bam
samtools: Raw Alignment Coverage and Depth Files
Coverage - <samplename>.txt
Depth - <samplename>.tsv
Each contig/chromosome is present in this file, 3rd column is depth at position (col 2).
bcftools: Variant And Consensus – Optional Module (--reference_assembly called)
Variants - <samplename>.<taxid>.vcf.gz
Consensus - <samplename>.consensus.fa
nanoplot/fastqc – QC plots and stats
mergedkrakenreport – krakenreport.merged_mqc.tsv - Top Hits for each sample – kraken2 only
General Procedure
There are a lot of moving parts in the pipeline (see Figure 1) for a detailed railway map of modules

