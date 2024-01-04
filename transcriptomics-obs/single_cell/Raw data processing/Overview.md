In this section, we discuss some of the fundamental issues surrounding what is commonly called “preprocessing” of single-cell and single-nucleus RNA-sequencing (sc/snRNA-seq) data.

Though this is common terminology, it seems a bit of a misnomer, as this process involves several steps that make important decisions about how to deal with and represent the data.


![[Pasted image 20240104141257.png]]

 focus will be on the phase of data analysis that begins with lane-demultiplexed FASTQ files, and ends with a count matrix representing the estimated number of distinct molecules arising from each gene within each quantified cell.

count Matrix dient als Input für weitere Analysen.
> methods for normalization, integration, and filtering through methods for inferring cell types, developmental trajectories, and expression dynamics.
> - Sie alle brauchen die Count Matrix.

	Eine gute Count Matrix ist kritisch. Deshalb ist auch eine gute Data Raw Processing nötig.

Fundamental misestimation in raw data processing can contribute to invalid inferences in higher-level analyses and can preclude discoveries based on the signal present in the raw data, which has been missed, diminished, or distorted by raw data processing.
> Schlechtes Raw processing führt zu schlechten Ergebnissen später.


we will cover the fundamental steps in raw data processing, including read alignment/mapping, cell barcode (CB) identification and correction, and the estimation of molecule counts through the resolution of unique molecular identifiers (UMIs).


Ablauf:

1. [[Raw Data Quality Control]] -> FastQ Files kontrollieren.
2. [[Alignment und Mapping]] 