# VarSkip multiplex PCR designs for SARS-CoV-2 sequencing

This repository contains reference files that describe the VarSkip primers used to amplify overlapping fragments of the SARS-CoV-2.

In an attempt to reduce the impact of variants on amplification efficiency, these primers were designed using [PrimalSeq][1] after masking the [SARS-CoV-2 reference sequence][2] for SNVs observed more than 4000 times in [GISAID][3].

They are commerically available at [NEB.com](https://www.neb.com/applications/ngs-sample-prep-and-target-enrichment/nebnext-artic-products-for-sars-cov-2-sequencing) as part of the ARTIC sequencing kits.

The files can be used with analyis methods designed for other multiplex designs (e.g. [ARTIC](https://artic.network/ncov-2019)).

Analysis methods known to work:
 - [galaxy ARTIC](https://usegalaxy.eu/u/sars-cov2-bot/w/covid-19-variation-analysis-on-artic-pe-data-3)
 - [viralrecon](https://nf-co.re/viralrecon)

[1]: <https://dx.doi.org/10.1186/s13059-018-1618-7> "PrimalSeq"
[2]: <https://www.ncbi.nlm.nih.gov/nuccore/MN908947> "MN908947.3"
[3]: <http://doi.org/10.17616/R3Q59F> "GISAID"

