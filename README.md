# :seedling: :dna:  __Project: _De novo_ Genome Assembly and Annotation of an _Arabidopsis thaliana_ genome__

This repository contains the workflow and scripts used for the assembly and annotation of an Arabidopsis thaliana genome.\
Datasets used: PacBio HiFi reads (WGS) and Illumina reads (RNA-seq). Accession number: Had-6b, genetic group from Africa. \
Raw data are from: [Qichao Lian et al. A pan-genome of 69 Arabidopsis thaliana accessions reveals a conserved genome structure throughout the global species range. Nature Genetics. 2024;56:982-991](https://www.nature.com/articles/s41588-024-01715-9) and [Jiao WB, Schneeberger K. Chromosome-level assemblies of multiple Arabidopsis genomes reveal hotspots of rearrangements with altered evolutionary dynamics. Nature Communications. 2020;11:1–10](http://dx.doi.org/10.1038/s41467-020-14779-y)

## Project workflow:

### __1st step:__ pre-assembly quality control 
- Raw reads quality check (fastQC and fastp, but trimmomatic could also be an option)
- Kmer counting for genome size estimation using Jellyfish tool
- Visualization of the histo file (output of Jellyfish) to determine the coverage

### __2nd step:__ assembly
- Whole genome assemblies using Flye, HifiASM, LJA. 
- Whole transcriptome assembly using Trinity (applied on Illumina data).
Note: LJA assembler was run within Apptainer container
Note: assemblies could take a few hours to complete and require quite some memory

### __3rd step:__ evaluation
- Assessing the quality of genomes using BUSCO, QUAST and merqury
- Comparison between assemblies based on the outputs of BUSCO and QUAST
- Visualization of copy-number spectra (output of merqury)
Note: BUSCO was applied to all the genome and transcriptome assemblies; QUAST and merqury were applied only to genome assemblies
Note: QUAST and merqury were run within Apptainer containers
Note: the Flye genome assembly evalutation has its own script called [12_flye_assembly_evaluation](https://github.com/mathilde733/Assembly_Annotation_Course/blob/main/scripts/12_flye_assembly_evaluation)

### __4th step:__ comparing genomes
- Comparison of genome assemblies using nucmer and MUMmer
- Visualization of dotplots to compare assemblies (see script [13_comparison_assemblies](https://github.com/mathilde733/Assembly_Annotation_Course/blob/main/scripts/13_comparison_assemblies))or to compare assembly with the reference genome (reference genome is provided; see script [11_comparing_genomes](https://github.com/mathilde733/Assembly_Annotation_Course/blob/main/scripts/11_comparing_genomes))

## ⚙️ Requirements:
- FastQC v.0.11.9 
- [Fastp v.0.23.4](https://github.com/OpenGene/fastp)
- [Jellyfish v.2.3.0](http://genomescope.org/genomescope2.0/)
- [Flye v.2.9](https://github.com/mikolmogorov/Flye/blob/flye/docs/USAGE.md) 
- [HifiASM v.0.16.1](https://github.com/chhylp123/hifiasm)
- [LJA v.0.2](https://github.com/AntonBankevich/LJA/blob/main/docs/lja_manual.md)
- [Trinity v.2.15.1](https://github.com/trinityrnaseq/trinityrnaseq/wiki)
- [BUSCO v.5.4.2](https://busco.ezlab.org)
- [QUAST v.5.2](https://quast.sourceforge.net/)
- [merqury v.1.3](https://github.com/marbl/merqury)
- [nucmer and mummer v.4](https://mummer4.github.io/manual/manual.html)
  
Some of the tools used in this workflow were run within Apptainer containers to ensure reproducibility and consistent environments. The other softwares were installed via modules. \
`apptainer exec --bind /data:/data /containers/apptainer/` 
or 
`module avail/load name`





