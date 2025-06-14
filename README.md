Heart Failure RNA-seq Analysis Pipeline (GSE71613)
Overview
This repository contains a reproducible bioinformatics pipeline for analyzing RNA-seq data from human heart failure samples, based on GEO dataset GSE71613. The workflow performs data download, quality control, read alignment, gene counting, and differential expression analysis using DESeq2.

Project Structure
perl
Copy
Edit
HeartFailure_RNASeq/
├── data/                 # Raw and trimmed FASTQ files (local only, ignored)
├── qc/                   # Quality control reports
├── ref/                  # Reference genome and GTF (local only, ignored)
├── results/              # STAR alignments, featureCounts output, DESeq2 results, plots
├── scripts/              # Shell and R scripts for each step
├── HeartFailure_RNASeq.Rproj  # RStudio project file
└── README.md             # Project description and instructions
Requirements
Bash shell

FastQC

fastp

SRA Toolkit

STAR aligner

Subread/featureCounts

R with DESeq2, pheatmap, ggplot2

How to Run
Download and QC raw FASTQ files:

bash
Copy
Edit
./scripts/download_qc.sh
Align reads and count genes:

bash
Copy
Edit
./scripts/align_count.sh
Run differential expression analysis in R:

bash
Copy
Edit
Rscript scripts/deseq2_analysis.R
Outputs will appear in the results/ folder:

featurecounts/counts.txt

deseq2_results.csv

PCA plot, volcano plot, and heatmap

Reference Files
Note: The human reference genome FASTA and GTF files (hg38.fa and hg38.gtf) are required locally but are ignored in this repository due to size. Download them directly from GENCODE before running the pipeline.

Tools and Methods
fasterq-dump — retrieve FASTQ files from SRA

fastp and FastQC — read trimming and quality checks

STAR — genome alignment

featureCounts — gene-level read counting

DESeq2 — differential expression analysis in R

pheatmap and ggplot2 — visualization

Citation
If you use this pipeline or adapt it, please cite the source dataset GSE71613 and acknowledge this workflow in your work.

License
This project is provided for educational and research purposes. Feel free to fork and adapt.


