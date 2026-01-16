# RNA-seq NGS Workshop

This repository documents my learning from an RNA-seq and Next-Generation Sequencing (NGS) workshop. The analysis was performed using the Galaxy platform to understand basic RNA-seq data analysis steps.

---

## Platform Used
- **Galaxy Europe**
Galaxy was used because it provides an easy web-based interface suitable for beginners.

---

## Objective
To learn the basic RNA-seq workflow including quality control, trimming, alignment, gene feature counting, and an introduction to differential expression analysis.

---

## Workflow Overview

### 1. Data Collection
- Dataset obtained from NCBI SRA for practice purposes.
- RNA-seq FASTQ files were downloaded from the SRA database.
- Example dataset:
  - SRR1552445

---

## 2. Quality Control (QC) Using Galaxy

### Step 1: Upload Data
- Raw FASTQ files were uploaded to Galaxy using the **Upload Data** option.

### Step 2: Run FastQC
- Tool used: **FastQC**
- Parameters checked:
  - Per base sequence quality
  - GC content
  - Sequence length distribution
  - Adapter content

### Step 3: MultiQC
- MultiQC was used to summarize all FastQC reports.

### QC Result
<img width="1904" height="1064" alt="Screenshot 2026-01-16 082800" src="https://github.com/user-attachments/assets/b472ccc7-6178-45cd-a46d-ee3cf546c533" />


**Observation:**
- Most quality parameters passed.
- Base quality scores were high.
- GC content was around 50%, which is acceptable.
- Minor warnings were observed, which is common in RNA-seq data.

---

## 3. Trimming

- Tool used: **Trim Galore**
- Adapter sequences and low-quality bases were removed.
- Reads shorter than 20 bp were discarded.

<img width="1895" height="1044" alt="Screenshot 2026-01-16 082603" src="https://github.com/user-attachments/assets/e0c4472c-4d3c-4643-b590-201af15f6891" />


**Observation:**
- Trimmed reads showed improved quality.
- Clean reads were suitable for alignment.

---

## 4. Alignment

- Tool used: **Bowtie2**
- Reference genome: **MM10 (Mouse genome)**
- Output format:
  - BAM file

<img width="1888" height="1041" alt="Screenshot 2026-01-16 082701" src="https://github.com/user-attachments/assets/209a083a-fb92-49e8-b8fa-aaa1c5e46593" />


**Observation:**
- Reads were successfully aligned to the reference genome.
- Alignment files were generated without errors.

---

## 5. Gene Feature Counting

- Tool used: **FeatureCounts**
- Input: BAM alignment file
- Annotation file:
  - Built-in MM10 GTF file

<img width="1912" height="1057" alt="Screenshot 2026-01-16 082456" src="https://github.com/user-attachments/assets/c3a728b1-4379-4ec4-8506-cba98c907654" />


**FeatureCounts Summary:**
- Assigned reads: 573  
- Unassigned (No features): 237  
- Unassigned (Ambiguity): 26  

**Observation:**
- A significant number of reads were successfully assigned to genes.
- Some reads were unassigned due to lack of annotation or ambiguity, which is expected.

---

## 6. Differential Expression Analysis (Introduction)

- Differential expression analysis compares gene expression between conditions.
- Tools introduced:
  - edgeR
  - limma
  - voom
- Raw gene count data from FeatureCounts is required.

---

## Visualization

- Tool used: **IGV (Integrative Genomics Viewer)**
- Used to visualize:
  - Read alignment
  - Gene structure
  - Coverage across chromosomes

---

## Results Summary

- Quality control confirmed good sequencing quality.
- Trimming improved overall read quality.
- Successful alignment to the MM10 genome.
- FeatureCounts generated reliable gene-level count data.
- The dataset was suitable for downstream differential expression analysis.

---

## Learning Outcomes

- Learned RNA-seq analysis using Galaxy
- Understood QC reports and trimming importance
- Learned how alignment and gene counting work
- Gained experience documenting analysis using GitHub

---

## Tools Used
- Galaxy Europe
- FastQC
- MultiQC
- Trim Galore
- Bowtie2
- FeatureCounts
- IGV
- GitHub

---

## Conclusion
This workshop provided hands-on experience with RNA-seq analysis using Galaxy. The step-by-step workflow helped in understanding bioinformatics concepts at a beginner level and maintaining reproducible documentation.
