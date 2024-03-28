# fastaconvtr v0.1beta (20200613) Sebastian E. Ramos-Onsins.

### Conversion of fasta and ms files into transposed fasta (tfasta, compressed and indexed) files and viceversa.

## Flags:
	-F [input format file: f (fasta), t (tfasta)]
	-i [path and name of the input file (text or gz indexed)]
	-f [output format file: t (tfasta), f (fasta), m (ms), 0(nothing)]
	-o [path and name of the output sequence file]
	-n [name of the file containing the name(s) of scaffold(s) and their length (separated by a tab), one per line (ex. fai file)]

##### OPTIONAL PARAMETERS:
	-h [help and exit]
	-P [define window lengths in 'physical' positions (1) or in 'effective' positions (0)]. DEFAULT: 1
	-O [#_nsam] [Reorder samples: number order of first sample, number 0 is the first sample] [second sample] ...etc.
	-W [for ms and fasta outputs, file with the coordinates of each window: (one header plus nlines with init end]
	-N [#_pops] [#samples_pop1] ... [#samples_popN] (necessary in case to indicate the outgroup population)
	-G [outgroup included (1) or not (0), last population (1/0)]. DEFAULT: 0
	-u [Missing counted (1) or not (0) in weights given GFF annotation]. DEFAULT: 0
	-m [masking regions: file indicating the start and the end of regions to be masked by Ns]
	-E [input file with weights for masking positions: include three columns with a header, first the physical positions (1...end), second the weight for positions and third a boolean weight for the variant (eg. syn variant but nsyn position)]

##### Outputing ms format:
	-k [path and name of the output mask file for ms].
	-w [window size]. DEFAULT: Total_length
	-s [slide size]. DEFAULT: Total_length
	Inputing fasta format:
	-p [if fasta input, haplotype:1 (single sequence) genotype:2 (two mixed sequences in IUPAC). DEFAULT: 1
	Annotation file and weight options:
	-g [GFF_file]
	[add also: coding,noncoding,synonymous,nonsynonymous,silent, others (whatever annotated)]
	[if 'synonymous', 'nonsynonymous', 'silent' add: Genetic_Code: Nuclear_Universal,mtDNA_Drosophila,mtDNA_Mammals,Other]
	[if 'Other', introduce the single letter code for the 64 triplets in the order UUU UUC UUA UUG ... etc.]
	-c [in case use coding regions, criteria to consider transcripts (max/min/first/long)]. DEFAULT: long
	-e [path and name of the output weights file (mandatory if included GFF)]

