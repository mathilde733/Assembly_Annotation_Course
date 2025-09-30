# :seedling: :dna:  __Project: _De novo_ Genome Assembly and Annotation of an _Arabidopsis thaliana_ genome__

This repository contains the workflow and scripts used for the assembly and annotation of an Arabidopsis thaliana genome.\
Datasets used: PacBio HiFi reads (WGS) and Illumina reads (RNA-seq). \
Raw data are from: [Qichao Lian et al. A pan-genome of 69 Arabidopsis thaliana accessions reveals a conserved genome structure throughout the global species range. Nature Genetics. 2024;56:982-991](https://www.nature.com/articles/s41588-024-01715-9) and [Jiao WB, Schneeberger K. Chromosome-level assemblies of multiple Arabidopsis genomes reveal hotspots of rearrangements with altered evolutionary dynamics. Nature Communications. 2020;11:1–10](http://dx.doi.org/10.1038/s41467-020-14779-y)

## Project workflow:

### __1st step:__ pre-assembly quality control 
- Raw reads quality check 
- Kmer counting for genome size estimation using Jellyfish tool

### __2nd step:__ assembly
- Whole genome assemblies using Flye, HifiASM, LJA
- Whole transcriptome assembly using Trinity

### __3rd step:__ evaluation
- Assessing the quality of genome using BUSCO, QUAST and merqury

### __4th step:__ comparing genomes
- Comparison of genome using nucmer and mummer

## ⚙️ Requirements:
- FastQC v.0.11.9 
- Fastp v.0.23.4
- [Jellyfish v.2.3.0](http://genomescope.org/genomescope2.0/)
- [Flye v.2.9](https://github.com/mikolmogorov/Flye/blob/flye/docs/USAGE.md) 
- [HifiASM v.0.16.1](https://github.com/chhylp123/hifiasm)
- [LJA v.0.2](https://github.com/AntonBankevich/LJA/blob/main/docs/lja_manual.md)
- [Trinity v.2.15.1](https://github.com/trinityrnaseq/trinityrnaseq/wiki)
- [BUSCO v.](https://busco.ezlab.org)
- [QUAST v.](https://quast.sourceforge.net/)
- [merqury v.](https://github.com/marbl/merqury)
- nucmer and mummer





