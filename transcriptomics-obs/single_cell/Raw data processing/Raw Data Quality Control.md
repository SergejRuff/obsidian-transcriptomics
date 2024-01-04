

Man sollte die FastQ Files, die die Raw Data enthalten, und die man aus BCL-Files über Base Calling erhält, auf ihre Qualität hin kontrollieren.

## FastQC

Once raw FASTQ files have been obtained, the quality of the reads themselves can be quickly diagnosed by running a quality control (QC) tool, such as **FastQC**

assess read quality, sequence content, etc.
`FastQC` generates a QC report for each input FASTQ file.

Overall, this report summarizes the quality score, base content, and certain relevant statistics to **spot potential problems originating from library preparation or sequencing**.


Although nowadays, single-cell raw data processing tools internally evaluate some quality checks that are important for single-cell data, such as the N content of sequences and the fraction of mapped reads, it is still a good habit to run a quick quality check before processing the data, as it evaluates other useful QC metrics.

# Achtung: FastQC funktioniert nicht immer. 

Finally, most of the metrics reported in such quality control reports make sense only for the “biological” reads of a single-cell dataset (i.e. the read being drawn from gene transcripts). For example, for 10x Chromium v2 and v3 datasets, this would be read 2 (the files containing `R2` in their filename). This is because the technical reads are comprised primarily of barcode and UMI sequences which are not drawn from the underlying transcriptome and which we do not expect to have typical biologically plausible sequence or GC content, though certain metrics like the fraction of `N` base calls are still relevant.
Siehe [[FastQC Beispiel]]


# Siehe Beispiel einer FASTQC- Datei:

siehe: [[FastQC Beispiel]]
