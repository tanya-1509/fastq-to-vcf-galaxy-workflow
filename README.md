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
| 2 | **Trimmomatic** | Removes low-quality bases and adapters |
| 3 | **BWA-MEM2** | Aligns reads to a reference genome (e.g., hg38 which is an in built reference or reference fasta provided) |
| 4 | **Picard MarkDuplicates** | Identifies and marks duplicate reads |
| 5 | **FreeBayes** | Performs variant calling to generate raw VCF |






