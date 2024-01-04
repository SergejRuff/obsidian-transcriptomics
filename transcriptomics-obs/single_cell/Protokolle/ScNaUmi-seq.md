Eine angepasste Form von Oxford Nanopore, die UMIs nutzen kann, trotz der höheren Errorrate von Long Read Sequenziergeräten, die normalerweise UMIs nicht nutzen können.

combines Nanopore sequencing with cell barcode and UMI assignment.

Wieso können Sie keine [[UMI]]s nutzen?
> Weil UMIs nicht verändert werden dürfen, um auch wieder erkannt zu werden. Wenn man aber eine hohe Fehlerrate hat, dann werden die UMIs mutieren und man kann das Transkript nicht dem Original-Molekül zuweisen.



The barcode assignment is guided with Illumina data by comparing the cell bar code sequences found in the Nanopore reads with those recovered from the Illumina reads for the same region or gene


However, this effectively requires two single-cell libraries. scCOLOR-seq computationally identifies barcodes without errors using nucleotide pair complementary across the full length of the barcode. These barcodes are then used as guides to correct the remaining erroneous barcodes

A modified UMI-tools directional network based method corrects for UMI sequence duplication.


Strengths:

- Recovers splicing and sequence heterogeneity information
    

Weaknesses:

- Nanopore reagents are expensive.
    
- High cell barcode recovery error rates.
    
- Depending on the protocol, barcode assignment is guided with Illumina data requiring two sequencing assays.