# :seedling: :dna:  __Project: _De novo_ Genome Assembly and Annotation of an _Arabidopsis thaliana_ genome__

This repository contains the workflow and scripts used for the assembly and annotation of an Arabidopsis thaliana genome.\
Datasets used: PacBio HiFi reads (WGS) and Illumina reads (RNA-seq).

## Project workflow:

### __1st step:__ pre-assembly quality control 
- Raw reads quality check 
- Kmer counting for genome size estimation using Jellyfish tool

### __2nd step:__ assembly
- Whole genome assemblies using Flye, HifiASM, LJA
- Whole transcriptome assembly using Trinity

### __3rd step:__ evaluation

### __4th step:__ comparing genomes

## ⚙️ Requirements:
- FastQC v.0.11.9
- Fastp v.0.23.4
- Jellyfish v.2.3.0
- Flye v.2.9
- HifiASM v.0.16.1
- LJA v.0.2
- Trinity v.2.15.1





