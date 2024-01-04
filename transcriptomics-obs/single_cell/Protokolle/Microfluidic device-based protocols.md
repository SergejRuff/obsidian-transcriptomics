Microfluidic device-based strategies where cells are encapsulated into hydrogel droplets

# wie funktioniert es?

![[Pasted image 20240104125827.png]]

Microfluidic device based single-cell strategies trap cells inside hydrogel droplets allowing for compartmentalisation into single-cell reaction chambers.

nanoliter-sized droplets containing encapsulated cells are always designed to capture beads and cells simultaneously.

Upon lysis the cell’s mRNA is instantaneously released and captured by the barcoded oligonucleotides that are attached on the beads. Next, the droplets are collected and broken to release single-cell transcriptomes attached to microparticles (STAMPs).
> Zellen werden lysiert und so mRNA freigesetzt, welches von den Beads eingefangen werden kann über einen Poly-T-Schwanz.

This is followed by PCR and reverse transcription to capture and amplify the transcripts.

Finally, tagmentation takes place where the transcripts are randomly cut and sequencing adaptors get attached.

This process results in sequencing libraries that are ready for sequencing as described above.

![[Pasted image 20240104130311.png]]

The encapsulation process is conducted with specialized microbeads with on-bead primers containing a PCR handle, a cell barcode and a 4-8b bp-long unique molecular identifier ([[UMI]]) and a poly-T tail
# Beispiele für Technologien + Vor und Nachteile - 3

 ==**inDrop**== 

InDrop uses primers which are released with photocleavage. Steigert Capture Effizienz.
 
 ==**Drop-seq** (siehe Bachelorarbeit) ==: 
 
 Drop-seq uses brittle resin for the beads and therefore the beads are encapsulated with a Poisson distribution.
 capture efficiency is likely influenced by the use of surface-tethered primers (fest an Beads befestigt) in Drop-Seq.
  In Drop-seq, reverse transcription occurs after the beads are released from the droplets

 
 commercially available==**10x Genomics Chromium**==

10X genomics dissolves the beads (so Sequenzen leicht freigelassen). Steigert Capture Effizienz.

the InDrop and 10X Genomics beads are deformable resulting in bead occupancies of over 80%.
> Die Wahrscheinlichkeit, dass InDrop und 10X Beads in Droplets kommen, liegt bei 80 %.


==Comparison of the 3 technologies:==

while reverse transcription takes place inside the droplets for the InDrop and 10X genomics protocols

A comparison from Zhang et al. in 2019 uncovered that inDrop and Drop-seq are outperformed by 10X Genomics with respect to bead quality, as the cell barcodes in the former two systems contained obvious mismatches. Moreover, the proportion of reads originating from valid barcodes was 75% for 10X Genomics, compared to only 25% for InDrop and 30% for Drop-seq.

Similar advantages were demonstrated for 10X Genomics regarding sensitivity. During their comparison, 10X Genomics captured about 17000 transcripts from 3000 genes on average, compared to 8000 transcripts from 2500 genes for Drop-seq and 2700 transcripts from 1250 genes for InDrop. Technical noise was the lowest for 10X Genomics, followed by Drop-seq and InDrop

10X Genomics favored the capture and amplification of shorter genes and genes with higher GC content, while Drop-seq in comparison preferred genes with lower GC content.

lthough 10X Genomics was shown to outperform the other protocols in various aspects, it is also about twice as expensive per cell. Moreover, except the beads, Drop-seq is open-source and the protocol can more easily be adapted if required. InDrop is completely open-sourced, where even the beads can be manufactured and modified in labs. Hence, InDrop is the most flexible of the three protocols.
# Wie viele Droplets pro Sekunde

are able to generate such droplets several thousand times per second. This massively parallel process generates very high numbers of droplets for a relatively low cost.

# Wie viele Transkripte werden pro Zelle gewonnen?

In microfluidic based protocols only about 10% of the transcripts of the cell are recovered. Notably, this low sequencing is sufficient for robust identification of cell types.

# Vor und Nachteile

Strengths:

- Allows for the cost-efficient sequencing of cells in large quantities, to identify the overall composition of a tissue and characterize rare cell types.
    
- UMIs can be incorporated.
    

Limitations:

- Low detection rates of transcripts compared to other methods.
    
- Captures 3’ only and not full transcripts, because the cell barcodes and PCR handles are only added to the end of the transcript.