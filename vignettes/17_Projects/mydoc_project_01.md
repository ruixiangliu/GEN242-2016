---
title: ChIP-Seq1 - Motif Prediction
last_updated: 29-Apr-16
---

## ChIP-Seq Workflow  

1. Read quality assessment, filtering and trimming 
2. Align reads to reference genome 
3. Compute read coverage across genome
4. Peak calling with different methods and consensus peak identification 
5. Annotate peaks 
6. Differential binding analysis 
7. Gene set enrichment analysis 
8. Motif prediction to identify putative TF binding sites

## Challenge Project: Comparison of motif enrichment and finding methods

+ Run workflow from start to finish (steps 1-8) on ChIP-Seq data set from Kaufman et al. (2010)
+ Challenge project tasks
    + Prioritize/rank peaks with at least two different methods, e.g. p-value from differential binding analysis, coverage, consensus peaks
    + Parse peak sequences from genome
    + Determine which peak prioritization method shows the highest enrichment for any of the motifs available in the Jaspar database (motifDB). 
    + Optional: use different statistical methods to test for motif enrichment. 

## References

+ Kaufmann, K, F Wellmer, J M Muiño, T Ferrier, S E Wuest, V Kumar, A Serrano-Mislata, et al. 2010. "Orchestration of Floral Initiation by APETALA1." Science 328 (5974): 85–89. [PubMed](http://www.ncbi.nlm.nih.gov/pubmed/20360106)
+ McLeay, Robert C, and Timothy L Bailey. 2010. “Motif Enrichment Analysis: A Unified Framework and an Evaluation on ChIP Data.” BMC Bioinformatics 11: 165. [PubMed](http://www.ncbi.nlm.nih.gov/pubmed/20356413)
+ Frith, Martin C., Yutao Fu, Liqun Yu, Jiang‐fan Chen, Ulla Hansen, and Zhiping Weng. 2004. “Detection of Functional DNA Motifs via Statistical Over‐representation.” Nucleic Acids Research 32 (4): 1372–81. [PubMed](http://www.ncbi.nlm.nih.gov/pubmed/14988425)
+ Tompa, M, N Li, T L Bailey, G M Church, B De Moor, E Eskin, A V Favorov, et al. 2005. “Assessing Computational Tools for the Discovery of Transcription Factor Binding Sites.” Nature Biotechnology 23 (1): 137–44. [PubMed](http://www.ncbi.nlm.nih.gov/pubmed/15637633)


