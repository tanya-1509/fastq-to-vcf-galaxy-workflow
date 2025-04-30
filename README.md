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

-> Clicking on Workflow > Create New Workflow

-> Add each tool listed above in sequence.

-> Connecting outputs to inputs via the drag-and-drop interface.

-> Saving and running the workflow on your dataset.




