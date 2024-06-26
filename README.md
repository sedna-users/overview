Overview of SEDNA users’ scripts and workflows
================

## Who is doing what?

### Phil Morin:

- reference-based genome assembly, genome-wide heterozygosity,
  historical demography (PSMC), genome characterization (BUSCO, QUAST),
  mitogenome assembly (reference based, de novo).

### Eric Anderson

- lcWGS workflows for trimming, mapping, variant calling with GATK, and also using
  the indels discovered therein to do indel realignment on overlap-clipped BAM files
  to make BAMs ready for ANGSD processing.
- microhaplotype genotyping.
- Association with ANGSD.
- Population assignment/GSI with genotype likelihoods.



## Bionformatic Topics

### Whole Genome Sequencing:

- Eric Anderson’s Snakemake-based whole genome sequencing workflow for non-model
  organisms. (FastQC, Trimmomatic, bwa mem, MarkDuplicates, HaplotypeCaller, GenotypeGVCFs to get a BCF file,
  then bamutils clipOveraps and GATK 3.8 Indel Realignment to produce ANGSD-ready
  BAMs a al Nicolas Lou, Nina Therkildsen, et al. <https://github.com/eriqande/mega-non-model-wgs-snakeflow>

- Phil Morin’s genome-wide heterozygosity, 1MB non-overlapping windows
  (ANGSD, R):
  <https://github.com/PAMorin/Genome_wide_heterozygosity_ANGSD>

### SNP discovery from single and multiplex genome assemblies

- Scripts from Morin et al. 2018, SNP discovery from single and multiplex genome assemblies of non-model organisms. In: Head, S.R., Ordoukhanian, P., Salomon, D. (Eds.), Next-Generation Sequencing. Methods in Molecular Biology. Humana Press, pp. 113-144.: https://github.com/PAMorin/SNPdiscovery

### Microhaplotype genotyping

- The SWFSC MEGA Microhaplotype workflow:
  <https://github.com/eriqande/mega-simple-microhap-snakeflow>

### Processing BCF files to ANGSD and other programs

- Eric’s workflows for post-BCF processing (PCA and association at the
  moment):
  <https://github.com/eriqande/mega-post-bcf-exploratory-snakeflows>

### Computing Pairwise Fst from lcWGS data using ANGSD and winsfs

- Eric put this together and the folks in the MEGA have used it for a number
  of species/projects.:
  <https://github.com/eriqande/mega-lcwgs-pw-fst-snakeflow>
  
### Phase chromosomes of WGS data

- Eric threw <https://github.com/eriqande/phase-chromosomes-snakeflow>
  together at one point when he was contemplating preparing some high
  coverage data for use with Leo Speidel’s RELATE program, that takes
  phased variant data to infer genealogies and then do inference from
  them.

### Population assignment from lcWGS data

- Eric collaborated with Matt DeSaix at Colorado State University to put
  this together.
  - repo: <https://github.com/mgdesaix/WGSassign>
  - methods paper: <https://besjournals.onlinelibrary.wiley.com/doi/full/10.1111/2041-210X.14286>
  - application in redstarts: <https://onlinelibrary.wiley.com/doi/full/10.1111/mec.17137>

### Annotating with SnpEff from a GFF file

- Eric put something together related to a guest lecture in a class at
  CSU. It shows a small Snakemake solution for it:
  <https://github.com/eriqande/annotate-millet-variants-snakeflow>

### Download sequences from NCBI using fasterq-dump

- <https://github.com/eriqande/fasterq-dump-snakemake-example>

### Making a FASTA file of ancestral bases

- Such a FASTA file is something that ANGSD requires when you want to
  polarize allele frequency spectra as derived and ancestral. One way to
  do it is to use the sequence of a closely related species (like using
  chimpanzee bases as the ancestral ones for human—as done in the ANGSD
  examples). The probably is that the ancestral sequence has to be
  perfectly concordant (in terms of number of bases, etc) with your
  focal species reference genome. This involves a fair bit of aligning
  and post-processing. There must be an easier way to do this, but here
  is one solution:
  <https://github.com/eriqande/make-ancestral-fasta-snakeflow>

### Visualizing Missing data in RAD seq data, etc

- A simple R package that uses 012 files and some compiled code to
  quickly generate some summaries of missing data in individuals and at
  different loci. It also provides an interface to SNPRelate for PCAs
  and calculating Fst. <https://github.com/eriqande/genoscapeRtools>.

### Historical demography from a single genome (PSMC)

- bash script to generate a consensus diploid genome from a bam file, and run PSMC (plus bootstrap) for historical demography. https://github.com/PAMorin/PSMC_boostrap_231122

### Bioinformatically useful R packages

- ecaRbioinf: A few useful functions in a package:
  - Repo: <https://github.com/eriqande/ecaRbioinf>
  - Online function reference:
    <https://eriqande.github.io/ecaRbioinf/reference/index.html>

## Using SEDNA topics

### Work interactively from your local RStudio on SEDNA’s R

- A little R package Eric wrote to make this easier to do:
  <https://github.com/eriqande/rView> Don’t know if it still works, or
  if some of the packages it depends on have changed enough to break it!
