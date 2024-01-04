
3 Arten von Mapping Algorithmen für Single Cell/ nuclei Data
- [[Spliced Alignment]]
- [[Continues Alignment]]
- [[lighweight mapping]] 



![[Pasted image 20240104143848.png]]

First, let us draw a distinction here between alignment-based approaches and lightweight mapping-based approaches.

==**Allignment =/= lighweight Mapping**==

## **Allignment**:

Alignment approaches apply a range of **different heuristics** to determine the potential loci from which reads may arise and then subsequently score, at each putative locus, the best nucleotide-level alignment between the read and reference, typically using **dynamic programming-based approaches**.
> Heuristisch + nutzt DP

==Alignments sind heuristisch und nutzen alle DP.==

 [Global alignment](https://en.wikipedia.org/wiki/Needleman%E2%80%93Wunsch_algorithm) is applicable for the case where the entirety of the query and reference sequence are to be aligned. On the other hand, [local alignment](https://en.wikipedia.org/wiki/Smith%E2%80%93Waterman_algorithm) is applicable when, possibly, only a subsequence of the query is expected to match a subsequence of the reference.
Short Reads nutzen weder Global noch local. Sie nutzen semi-global (the majority of the query is expected to align to some substring of the reference (this is often called “fitting” alignment)).

Oft Soft Clipping an Enden -> Geringere Penalties an Enden. Nutzt [“extension” alignment](https://github.com/smarco/WFA2-lib#-33-alignment-span).

Andere Allignment Tools:
- banded Alignment: Ignoriert Alignments mit einem geringen Threshold. Bessere rechenzeiten dadurch.
- x-drop und z-drop: Schmeißen schlechte Alignments früh raus.
- waterfron Alignments

### Output eines Alignments:

- Score
- backtrace des Alignments in ***CIGAR-Format*** (Concise Idiosyncratic Gapped Alignment Report) in der ***SAM/ BAM***-Datei. 

An example of a `CIGAR` string is `3M2D4M`, which represents that the alignment has three matches or mismatches, followed by a deletion of length two from the read (bases present in the reference but not the read), followed by four more matches or mismatches.

### Vor und Nachteile des Alignments

***At the cost of computing such scores***, alignment-based approaches ***know the quality of each potential mapping*** of a read, which they can then use to filter reads that align well to the reference from mappings that arise as the result of low complexity or “spurious” matches between the read and reference.

## **Lightweight Mapping**


Such approaches generally achieve superior speed by avoiding nucleotide-level alignment between the read and reference sequences.
> Kein Alignment auf Nucleilevel anders als Alignment Methoden
> Schneller als Alignment

Instead, they base the determination of the reported mapping loci of a read on a separate set of rules and heuristics that may look only at the set of matching k-mers or other types of exact matches (e.g., via a consensus rule) and, potentially, their orientations and relative positions with respect to each other on both the read and reference (e.g., chaining).

Nachteil:
Keine gut interpretierbaren Scores wie bei Alignments.

