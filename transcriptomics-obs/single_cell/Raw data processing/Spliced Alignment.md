
# Definition

Spliced-alignment approaches are capable of aligning a sequence read over several distinct segments of a reference, allowing potentially large gaps between the regions of the reference that align well with the corresponding parts of the read.

# Wann wird es benutzt?

These alignment approaches are typically applied when aligning RNA-seq reads to the genome, since the alignment procedure must be able to align reads that span across one or more splice junctions of the transcript.
> Wenn ganze Genom gemappt wird.
> Wenn Splicing Varianten gesucht werden.


Spliced alignment is a challenging problem, particularly in cases where only a small region of the read spans a splicing junction, since very little informative sequence may be available to place the segment of the read that overhangs the splice junction by only a small amount.