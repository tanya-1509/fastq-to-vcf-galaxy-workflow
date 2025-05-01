# fastq-to-vcf-galaxy-workflow
DESCRIPTION: FASTQ to VCF Generation: Workflow and its Explanation using UseGalaxy.

OVERVIEW: This guide provides a comprehensive workflow for converting raw FASTQ sequencing data into annotated VCF files using the UseGalaxy platform.

**FASTQ files** : Raw outputs from high-throughput sequencing, containing nucleotide sequences and corresponding quality scores. These files are the starting point of many genomic data analyses.

**VCF files** : Used to store gene sequence variations (e.g., SNPs, INDELs) identified from comparing the FASTQ sequences to a reference genome.
FASTQ → (alignment + processing) → variant calling → VCF

UseGalaxy is a web-based platform that allows users to perform bioinformatics analysis through a graphical interface. It is open-source, community-driven, and supports a wide range of genomics tools without needing any coding skills.

Creating an UseGalaxy account:

-> Visit https://usegalaxy.org

-> Click on the User icon at the top-right corner.

-> Choose Register.

-> Fill in your details and verify your email.

-> Log in and start building your workflow.

What is a workflow?
A workflow is a step-by-step sequence of tools or processes that you follow to analyze biological data — often automated and repeatable. It defines what tools are used, in what order, and how data flows from one step to the next.

Creating a workflow:

-> Clicking on Workflow -> Create New Workflow

-> Add each tool in sequence.

-> Connecting and checking the outputs of one tool to the inputs via the drag-and-drop interface.

-> Saving and running the workflow on the given data files.

Below we are going to look at the step by step approach on how to convert FASTQ files to VCF:

**Table 1** : Tools used in the workflow and the descripton

| Step | Tool Name | Description |
|------|-----------|-------------|
| 1 | **FastQC** | Performs quality checks on raw FASTQ files |
| 2 | **Trim Galore** | Automatically trims Illumina adapters and low-quality bases using Cutadapt; includes optional FastQC reporting |
| 3 | **BWA-MEM2** | Aligns reads to a reference genome (e.g., hg38 which is an in built reference or reference fasta provided) |
| 4 | **Picard MarkDuplicates** | Identifies and marks duplicate reads |
| 5 | **SortSam** | Sorts SAM/BAM files by coordinate or name using Picard; prepares files for downstream analysis |
| 6 | **GATK4 Mutect2** | Calls somatic variants in tumor or tumor-normal pairs using a Bayesian model; optimized for cancer mutation detection |

**Detailed explanation of each of the tools/steps used:**

1. Quality Control - FastQC

    Input: Raw FASTQ files

    Output: Quality reports

    Purpose: Identifies issues like low-quality reads or adapter contamination.

2. Trimming - Trim Galore

    Input: Raw FASTQ

    Output: Cleaned FASTQ

    Purpose: Removes adapters and low-quality bases, improving downstream analysis.

3. Alignment - BWA-MEM2

    Input: Clean FASTQ + Reference Genome

    Output: SAM file (sequence alignment)

    Purpose: Maps reads to a known reference genome.

4. Tool Name: SortSam

    Input: SAM or BAM file (unsorted)

    Output: Sorted BAM file (by coordinate or read name)

    Purpose: Organizes sequencing reads for downstream tools (e.g., MarkDuplicates, variant calling)

5. Mark Duplicates - Picard

    Input: BAM

    Output: Deduplicated BAM

    Purpose: Identifies and flags PCR duplicates to avoid false variants.

6. Variant Calling - GATK4 Mutect2

    Input: BAM + Reference Genome

    Output: VCF

    Purpose: Detects SNPs and INDELs from aligned reads.
