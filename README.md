# RNA-seq NGS Workshop

This repository contains my learning work from the RNA-seq and Next-Generation Sequencing (NGS) workshop. The analysis was performed using the Galaxy platform to understand the basic steps involved in RNA-seq data analysis.

---

## Platform Used
- **Galaxy (web-based bioinformatics platform)**  
Galaxy was used because it provides an easy graphical interface suitable for beginners and students.

---

## Objective
To learn the basic RNA-seq workflow, including quality control, trimming, alignment, gene counting, and an introduction to differential gene expression analysis.

---

## Workflow Overview

### 1. Data Collection
- RNA-seq raw data files (FASTQ format) were downloaded from the SRA database.
- Both single-end and paired-end reads were discussed in the workshop.

---

## 2. Quality Control (QC) Using Galaxy – Step by Step

Quality control helps check whether the sequencing data is good enough for analysis.

### Step 1: Upload Data to Galaxy
- Raw FASTQ files were uploaded using the **Upload Data** button in Galaxy.

### Step 2: Run FastQC
- Tool used: **FastQC**
- This tool checks:
  - Base quality scores
  - GC content
  - Sequence length distribution
  - Presence of adapter sequences

### Step 3: View QC Summary
- FastQC reports were reviewed to understand data quality.
- **MultiQC** was used to combine multiple FastQC reports into one summary report.

---

## 3. Trimming
- Adapter sequences and low-quality bases were removed.
- Reads shorter than 20 bp were discarded.
- This step improves data quality before alignment.

---

## 4. Alignment
- Cleaned reads were aligned to a reference genome.
- Output files generated:
  - SAM
  - BAM
- Only primary alignments were used for further analysis.

---

## 5. Gene Feature Counting
- Tool used: **FeatureCounts**
- Input: BAM files
- Annotation file:
  - Built-in **MM10 (Mouse genome)** GTF file
- This step counts how many reads map to each gene.

---

## 6. Differential Expression Analysis (Introduction)
- Differential expression analysis helps compare gene expression between two conditions.
- Tools introduced:
  - edgeR
  - limma
  - voom
- Raw gene count data is required for this step.

---

## Normalization (Basic Understanding)
- Gene expression values were normalized using:
  - RPKM / FPKM
- Normalization helps compare gene expression levels between samples.

---

## Visualization
- Tool used: **IGV (Integrative Genomics Viewer)**
- Used to visually inspect read alignment and gene structure.

---

## Results & Learning Outcomes
- Learned how to perform quality control using Galaxy
- Understood the importance of trimming and alignment
- Learned how gene counts are generated using FeatureCounts
- Gained basic understanding of differential expression analysis

---

## Tools Used
- Galaxy
- FastQC
- MultiQC
- FeatureCounts
- edgeR
- limma
- voom
- IGV
- GitHub

---

## Conclusion
This workshop helped build a basic understanding of RNA-seq analysis using Galaxy. The step-by-step approach made it easier to learn bioinformatics concepts as a beginner and document the workflow using GitHub.

