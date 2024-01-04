![[Pasted image 20240104142925.png]]

## Wie kann Single Cell Mapping unterteilt werden?

While the specific algorithms, data structures, and time and space trade-offs made by different alignment and mapping approaches can vary greatly, we can roughly categorize existing approaches along two axes:

- The [[type of mapping]] they perform and
    
- The [[type of reference sequence]] against which they map reads.

## Definition

It refers to the process of determining the potential loci of origin of each sequenced fragment (e.g., the set of genomic or transcriptomic loci that are similar to the read).

Bei der Transkriptomik bezieht sich "Alignment" auf den Prozess, bei dem RNA-Sequenzen (z. B. aus RNA-Seq-Experimenten) mit einem Referenzgenom oder einer Referenztranskriptomsequenz verglichen werden. Das Ziel ist es, herauszufinden, wo genau die Sequenzen im Genom oder Transkriptom auftreten.

Depending on the sequencing protocol, the resulting raw sequence file contains the cell-level information, commonly known as cell barcodes (CB), the unique molecule identifier (UMI), and the raw cDNA sequence (read sequence) generated from the molecule.
incorrect read-to-transcript/gene mapping can lead to wrong or inaccurate matrices.


## Tools für ScRNA-Seq Allignment

	 Wozu braucht man eigene Allignment Tools und nutzt nicht einfach Bulk-Allignment Ansätze?

Additionally, using pre-existing RNA-seq aligners that are agnostic to any specific scRNA-seq protocol – like the length and position of cell barcodes, UMI, etc. – requires making use of separate tools for performing other steps such as demultiplexing and UMI resolutions.current and quickly growing scale of scRNA-seq samples (typically hundreds of millions to billions of reads) makes this stage particularly computationally intensive.
> Beide Gründe, wieso Allignment bei ScRNAseq eigene Protokolle braucht und nicht die Bulk-Ansätze nutzen kann.

Tools für ScRNA-Seq

- Cell Ranger -> 10 X Genomics
- ZUMIs
- alevin
- RainDrop
- Kalliso
- STARsolo
- alevin-fry

provide dedicated treatment for aligning scRNA-seq reads along with parsing of technical read content (CBs and UMIs), as well as methods for demultiplexing and UMI resolution.

