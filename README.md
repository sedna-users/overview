Overview of SEDNA users’ scripts and workflows
================

Who is doing what?

## Bionformatic Topics

### Whole Genome Sequencing:

- Eric Anderson’s whole genome sequencing workflow for non-model
  organisms: <https://github.com/eriqande/mega-non-model-wgs-snakeflow>

### Microhaplotype genotyping

- The SWFSC MEGA Microhaplotype workflow:
  <https://github.com/eriqande/mega-simple-microhap-snakeflow>

### Processing BCF files to ANGSD and other programs

- Eric’s workflows for post-BCF processing (PCA and association at the
  moment):
  <https://github.com/eriqande/mega-post-bcf-exploratory-snakeflows>

### Phase chromosomes of WGS data

- Eric threw <https://github.com/eriqande/phase-chromosomes-snakeflow>
  together at one point when he was contemplating preparing some high
  coverage data for use with Leo Speidel’s RELATE program, that takes
  phased variant data to infer genealogies and then do inference from
  them.

### Annotating with SnpEff from a GFF file

- Eric put something together related to a guest lecture in a class at
  CSU. It shows a small Snakemake solution for it:
  <https://github.com/eriqande/annotate-millet-variants-snakeflow>

### Download sequences from NCBI using fasterq-dump

- <https://github.com/eriqande/fasterq-dump-snakemake-example>

### Making a FASTA file of ancestral bases

Such a FASTA file is something that ANGSD requires when you want to
polarize allele frequency spectra as derived and ancestral. One way to
do it is to use the sequence of a closely related species (like using
chimpanzee bases as the ancestral ones for human—as done in the ANGSD
examples). The probably is that the ancestral sequence has to be
perfectly concordant (in terms of number of bases, etc) with your focal
species reference genome. This involves a fair bit of aligning and
post-processing. There must be an easier way to do this, but here is one
solution: <https://github.com/eriqande/make-ancestral-fasta-snakeflow>

## Using SEDNA topics

### Work interactively from your local RStudio on SEDNA’s R

- A little R package Eric wrote to make this easier to do:
  <https://github.com/eriqande/rView> Don’t know if it still works, or
  if some of the packages it depends on have changed enough to break it!
