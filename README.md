# Heart Failure RNA-seq Analysis Pipeline (GSE71613)

## Overview
This repository provides a reproducible RNA-seq analysis pipeline for investigating gene expression differences between failing and non-failing human heart tissues, using publicly available data from [GSE71613](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE71613).

The workflow includes:
- Downloading raw reads from GEO/SRA
- Quality control with FastQC and fastp
- Read alignment using STAR
- Gene-level counting with featureCounts
- Differential expression analysis with DESeq2
- Visualization of results (PCA, volcano plot, heatmap)

---

## Project Structure

```HeartFailure_RNASeq/
├── data/ # Raw and trimmed FASTQ files (local only, ignored)
├── qc/ # Quality control reports
├── ref/ # Reference genome and GTF (local only, ignored)
├── results/ # STAR alignments, featureCounts output, DESeq2 results, plots
├── scripts/ # Shell and R scripts for each step
├── HeartFailure_RNASeq.Rproj # RStudio project file
└── README.md # Project description and instructs```


---

## Requirements

- Bash shell
- [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)
- [fastp](https://github.com/OpenGene/fastp)
- [SRA Toolkit](https://github.com/ncbi/sra-tools)
- [STAR aligner](https://github.com/alexdobin/STAR)
- [Subread (featureCounts)](http://subread.sourceforge.net/)
- R with packages: `DESeq2`, `pheatmap`, `ggplot2`

---

## How to Run the Pipeline

**1. Download and QC raw FASTQ files:**

```bash
./scripts/download_qc.sh
./scripts/align_count.sh
Rscript scripts/deseq2_analysis.R


## Outputs
results/featurecounts/counts.txt: Gene count matrix

results/deseq2_results.csv: DESeq2 differential expression results

results/pca_plot.png: PCA plot of samples

results/volcano_plot.png: Volcano plot of significant genes

results/heatmap_top20.png: Heatmap of top differentially expressed genes

##Reference Files
This pipeline requires the human reference genome (FASTA) and gene annotation (GTF). These files are not included in this repository due to size constraints. Please download them from GENCODE and place them in the ref/ folder.

Recommended files:

GRCh38.primary_assembly.genome.fa

gencode.v44.annotation.gtf

## Citation
If you use or adapt this pipeline, please cite the original dataset GSE71613 and acknowledge all tools and packages according to their respective licenses.

## License
This project is provided for academic and educational purposes. Feel free to fork and adapt as needed.

---

##  **How to use it**

⃣ Open your `README.md`:
```bash
nano README.md
