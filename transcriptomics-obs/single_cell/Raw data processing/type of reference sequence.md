

We consider three main categories of reference sequence against which a method might map:

- The full (likely annotated) reference genome
    
- The annotated transcriptome
    
- An augmented transcriptome


It is also worth noting that, currently, not all combinations of mapping algorithms and reference sequences are possible. For example, [[lighweight mapping]]-based algorithms do not currently exist that can perform spliced mapping of reads against a reference genome.


## Full Genome


The first type of reference, against which a method may map, consists of the entire genome of the target organism, usually with the annotated transcripts considered during mapping. Tools

Tools like `zUMIs`, Cell Ranger and `STARsolo` 


Since many of the reads arise from spliced transcripts, such an approach also ***requires the use of a splice-aware alignment algorithm*** (siehe: [[Spliced Alignment]]) where the alignment for a read can be split across one or more splicing junctions.
> Tools basieren hier oft auf STAR.

The main benefits of this approach are that reads arising from any location in the genome, not just from annotated transcripts, can be accounted for.
A final benefit is that even reads residing outside of the annotated transcripts, exons, and introns can be accounted for by such methods.

Nachteil
> Tradeoff zwischen Datengröße und Alignment Speed: Ich kann große Datenmengen nutzen und schnell sein oder Datenmengen reduzieren und dafür Speed aufgeben. Zb. 32 gb Humangenom oder sparse suffix array nutzen, um Datenmenge und Speed zu reduzieren.
> 
> Second, the increased difficulty of spliced alignment compared to contiguous alignment and the fact that current spliced-alignment tools must explicitly compute a score for each read alignment, means that this approach comes at an increased computational cost compared to the alternatives.
> 
> Brauche ein annotiertes Genom. Kein Problem bei bekannten Spezies wie Mensch. Schlecht bei unbekannten Spezies ohne vollstängiges Modelgenom


## Spliced Transcript

