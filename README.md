# fastp

Fastp is all-in-one preprocesser tool does quality profiling, adapterm trimming, read filtering and base correction. Fastp supports the single-end and paired-end reads

# Installation with Bioconda

conda install -c bioconda fastp

# Usuage

https://github.com/OpenGene/fastp

 > example
 
 fastp --detect_adapter_for_pe --adapter_fasta <adapter-file.fasta> -I 75 -q 20 -u 25 -n 0 thread 8 -i fastq_R1.gz -l fastq_R2.gz -o fastq-trim_R1.fastq -O fastq-trim_R2.fastq --json fastq-fastp.json --html fastq-fastp.html

 --detect_adapter_for_pe          by default, the adapter sequence auto-detection is enabled for SE data only, turn on this option to enable it for PE data.
 
 --adapter_fasta                  specify a FASTA file to trim both read1 and read2 (if PE) by all the sequences in this FASTA file (string [=])
 
 -i, --in1                          read1 input file name (string)
 
  -o, --out1                         read1 output file name (string [=])
  
  -I, --in2                          read2 input file name (string [=])
  
  -O, --out2                           read2 output file name (string [=])
  
  -q, --qualified_quality_phred      the quality value that a base is qualified. Default 15 means phred quality >=Q15 is qualified. (int [=15])
  
  -u, --unqualified_percent_limit    how many percents of bases are allowed to be unqualified (0~100). Default 40 means 40% (int [=40])
  
  -n, --n_base_limit                 if one read's number of N base is >n_base_limit, then this read/pair is discarded. Default is 5 (int [=5])
