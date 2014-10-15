# BIOMD0000000350: Model_1

## Installation

Download this repository, and install with distutils

`python setup.py install`

Or, install using pip

`pip install git+https://github.com/biomodels/BIOMD0000000350.git`

To install a specific version (in this example, from the 2014-09-16 BioModels release)

`pip install git+https://github.com/biomodels/BIOMD0000000350.git@20140916`


# Model Notes


This model is from the article:  
**Multiple light inputs to a simple clock circuit allow complex biological rhythms**   
Troein C, Corellou F, Dixon LE, van Ooijen G, O'Neill JS, Bouget FY, Millar
AJ. _Plant J._ 2011 Apr;66(2):375-85.
[21219507](http://www.ncbi.nlm.nih.gov/pubmed/21219507) ,  
**Abstract:**   
Circadian clocks are biological timekeepers that allow living cells to time
their activity in anticipation of predictable environmental changes. Detailed
understanding of the circadian network of higher plants, such as Arabidopsis
thaliana, is hampered by the high number of partially redundant genes.
However, the picoeukaryotic alga Ostreococcus tauri, which was recently shown
to possess a small number of non-redundant clock genes, presents an attractive
alternative target for detailed modelling of circadian clocks in the green
lineage. Based on extensive time-series data from in vivo reporter gene
assays, we developed a model of the Ostreococcus clock as a feedback loop
between the genes TOC1 and CCA1. The model reproduces the dynamics of the
transcriptional and translational reporters over a range of photoperiods.
Surprisingly, the model is also able to predict the transient behaviour of the
clock when the light conditions are altered. Despite the apparent simplicity
of the clock circuit, it displays considerable complexity in its response to
changing light conditions. Systematic screening of the effects of altered day
length revealed a complex relationship between phase and photoperiod, which is
also captured by the model. The complex light response is shown to stem from
circadian gating of light-dependent mechanisms. This study provides insights
into the contributions of light inputs to the Ostreococcus clock. The model
suggests that a high number of light-dependent reactions are important for
flexible timing in a circadian clock with only one feedback loop.

**Note: Two-gene model of the Ostreococcus circadian clock**

This is a model of the circadian clock of Ostreococcus tauri, with a negative
feedback loop between TOC1 and CCA1 (a.k.a. LHY) and multiple light inputs. It
was used and described in Troein et al., Plant Journal (2011).

The model incorporates luciferase reporters, and in this SBML model the four
different versions of the model for transcriptional and translational reporter
lines (pTOC1::LUC, pCCA1::LUC, TOC1-LUC and CCA1-LUC) are all accessible by
setting one of the rep_X parameters to 1 and the others to 0. You can also set
all four to 0 to only simulate the non-reporter core of the system.

Input to the system should be provided by modifying the "light" function. An
implementation of LD 12:12 is provided as an example, but the model was also
used with more complicated light regimes that vary between data sets and are
not convenient to express directly in SBML.

The functions "ox_cca1" and "ox_toc1" can be altered to add overexpression of
CCA1 and TOC1. Setting either to x gives additional, constitutive
transcription at x times the maximal (and typically not realizable)
transcription rate of the native gene. The overexpression mutant fits in
Figure 7 of Troein et al. (2011) used ox_cca1 = 0.115 and oc_toc1 = 0.0584,
respectively.

The functions "copies_toc1" and "copies_cca1" are normally 1 but can be
lowered to simulate knockdown experiments. The functions "transcription",
"translation" and "proteasome" can be modified to simulate the effects of
altering the overall rate of transcription, translation and protein
degradation.

The parameters were fitted specifically to data from transgenic reporter lines
TOC8, pTOC3, LHY7 and pLHY7 (Corellou et al., Plant Cell 2009). Parameters
that begin with "effcopies" describe the effective number of copies of CCA1 or
TOC1 in the respective translational fusion lines, with anything above 1 due
to the fusion proteins.

For the model fitting, the initial values were fitted to the data in the
various time courses. The initial values given here correspond to the limit
cycle of the system in LD 12:12. The system converges to the limit cycle in
just a few days under most light conditions, so these initial values are
biologically meaningful.

The species cca1luc_c and cca1luc_n have been merged into cca1luc (which
corresponds to the observable luminescence signal), because Copasi refused to
run the system otherwise. For TOC1-LUC, the predicted output signal is the sum
of toc1luc_1 and toc1luc_2.

This model originates from BioModels Database: A Database of Annotated
Published Models (http://www.ebi.ac.uk/biomodels/). It is copyright (c)
2005-2011 The BioModels.net Team.  
For more information see the [terms of
use](http://www.ebi.ac.uk/biomodels/legal.html) .  
To cite BioModels Database, please use: [Li C, Donizelli M, Rodriguez N,
Dharuri H, Endler L, Chelliah V, Li L, He E, Henry A, Stefan MI, Snoep JL,
Hucka M, Le Novère N, Laibe C (2010) BioModels Database: An enhanced, curated
and annotated resource for published quantitative kinetic models. BMC Syst
Biol., 4:92.](http://www.ncbi.nlm.nih.gov/pubmed/20587024)


