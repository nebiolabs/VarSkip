# VarSkip multiplex PCR designs for SARS-CoV-2 sequencing

This repository contains reference files that describe the VarSkip primers used to amplify overlapping fragments of the SARS-CoV-2 virus.

In an attempt to reduce the impact of variants on amplification efficiency, these primers were designed using [PrimalSeq][1] after masking the [SARS-CoV-2 reference sequence][2] for SNVs observed more than 4000 times in [GISAID][3].
More details can be found in scientific presentations:
 -  [slides](https://slides.com/bwlang/varskip-sequencing-sfaf-2021-09-28) from a presentation at the [Sequencing to Function: Analysis and Application for the Future 2021 conference](http://sfafmeeting.org/index.html) (September 2021) 
 -  [screen recording](https://www.youtube.com/watch?v=4T6BF6F3-9w&t=2339s) of a presentation at a CDC SPHERES meeting (June 2021).

VarSkip 1a primers are commerically available at [NEB.com](https://www.neb.com/applications/ngs-sample-prep-and-target-enrichment/nebnext-artic-products-for-sars-cov-2-sequencing) as part of the ARTIC sequencing kits.
VarSkip Long primers are only available as a [custom product](https://www.neb.com/customized-solutions/contact-us) for larger volume sequencing. 

The files in this repository can be used with analyis methods designed for other multiplex designs (e.g. [ARTIC](https://artic.network/ncov-2019)). To avoid miscalling or masking variants in priming regions, it's important to use primer coordinates that match the primers used during amplification (e.g. do not use ARTICv3 primer files with VarSkip libraries).

The same information is presented in multiple formats for convenience. Most workflows should use [neb_vss1a.primer.bed](https://github.com/nebiolabs/VarSkip/blob/main/neb_vss1a.primer.bed).  

Analysis methods known to work:
 - [galaxy ARTIC](https://usegalaxy.eu/u/sars-cov2-bot/w/covid-19-variation-analysis-on-artic-pe-data-3)
   - example [data](https://usegalaxy.eu/u/brad_langhorst/h/varskip-short-test-data) and [results](https://usegalaxy.eu/u/brad_langhorst/h/varskip-example-data---ivar-workflow-results) are available via galaxy
 - [viralrecon](https://nf-co.re/viralrecon) (tested with illumina data)
 - [ARTIC field bioinformatics](https://github.com/artic-network/fieldbioinformatics) [docs](https://artic.readthedocs.io/en/latest/?badge=latest)

   The ARTIC field bioinformatics pipeline is commonly used to analyize results produced on the Oxford Nanopore instruments. It requires a specific directory structure and primer naming to operate correctly. The schemes directory contains a reformatted primer annotation and reference genome that meet those constraints.

   Example command (tune this to your instrument-specific model and directories):

   `artic minion --threads 4 --read-file example.fastq --scheme-directory schemes --scheme-version 1a NEB_VarSkip Example --skip-nanopolish --medaka --medaka-model r941_min_fast_g303`

Many libraries produced using VarSkip primers are available via the NCBI SRA. e.g. [SRR16375192](https://trace.ncbi.nlm.nih.gov/Traces/sra/?run=SRR16375192)

[1]: <https://dx.doi.org/10.1186/s13059-018-1618-7> "PrimalSeq"
[2]: <https://www.ncbi.nlm.nih.gov/nuccore/MN908947> "MN908947.3"
[3]: <http://doi.org/10.17616/R3Q59F> "GISAID"
