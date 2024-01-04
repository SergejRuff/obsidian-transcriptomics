The summary panel on the left-hand side of the HTML report shows the module names included in the report, together with a sign used for quick evaluation of the module results. However, because `FastQC` uses uniform thresholds for files generated from all kinds of sequencing platforms and underlying biological material, we sometimes see warnings (orange exclamation) and failures(red crosses) for good data and passes (green ticks) for questionable data. So, all modules should be carefully evaluated before concluding about the data quality.

[![Summary](https://www.sc-best-practices.org/_images/summary.jpg)](https://www.sc-best-practices.org/_images/summary.jpg)

Fig. 3.2 The summary panel of a bad example.[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-summary "Permalink to this image")

**1. Basic Statistics**

The basic statistics module contains the overview information and statistics of the reads in the input FASTQ file, such as the filename, total number of sequences, number of poor quality sequences, sequence length, and the overall %GC of all bases in all sequences. Good single-cell data usually have a very little number of poor quality sequences and most often have uniform sequence length. The GC content should match the overall GC content of the genome or transcriptome of the sequenced species.

[![Basic Statistics](https://www.sc-best-practices.org/_images/basic_statistics.jpg)](https://www.sc-best-practices.org/_images/basic_statistics.jpg)

Fig. 3.3 A good basic statistics report example.[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-basic-statistics "Permalink to this image")

**2. Per Base Sequence Quality**

The per base sequence quality view contains a BoxWhisker type plot for each position in the read, which shows the range of quality scores across all bases at each position along all reads in the file. The x-axis represents the positions in the read, and the y-axis shows the quality scores. For single-cell data of good quality, all yellow boxes in the view, which represent the inter-quantile range of the quality scores of positions, should fall into the green (calls of good quality) area. So do all the whiskers, which represent the 10% and 90% of the distribution. It is not unexpected to see that the quality scores drop along the body of the reads, and some base calls of the last positions fall into the orange (calls of reasonable quality) area because of the decrease in the signal-to-noise ratio that is common in most sequencing-by-synthesis methods. Still, boxes should fall outside of the red (calls of poor quality) area. If poor quality calls are observed, one may consider performing quality trimming of their reads. [A detailed explanation](https://hbctraining.github.io/Intro-to-rnaseq-hpc-salmon/lessons/qc_fastqc_assessment.html) of the sequencing error profiles is provided by the [HBC training program](https://hbctraining.github.io/main/).

[![per read sequence quality](https://www.sc-best-practices.org/_images/per_read_sequence_quality.jpg)](https://www.sc-best-practices.org/_images/per_read_sequence_quality.jpg)

Fig. 3.4 A good (left) and a bad (right) per-read sequence quality graph.[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-per-read-sequence-quality "Permalink to this image")

**3. Per Tile Sequence Quality**

Using an Illumina library, the per tile sequence quality plot shows the deviation from the average quality for the reads in each flowcell tile that was sequenced. The “hotter” the color, the larger the deviation. For high-quality data, we should see blue over the entire plot, meaning that the flowcell has consistent quality in all tiles. If only part of a flowcell has poor quality, some hot colors will appear in the plot. In that case, the sequencing step might have encountered transient problems, such as bubbles going through the flowcell or smudges and debris inside the flowcell lane. For further diagnoses, please refer to [QC Fail](https://sequencing.qcfail.com/articles/position-specific-failures-of-flowcells/) and [common reasons for warnings](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/Help/3%20Analysis%20Modules/12%20Per%20Tile%20Sequence%20Quality.html) from `FastQC`.

[![per tile sequence quality](https://www.sc-best-practices.org/_images/per_tile_sequence_quality.jpg)](https://www.sc-best-practices.org/_images/per_tile_sequence_quality.jpg)

Fig. 3.5 A good (left) and a bad (right) per tile sequence quality view.[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-per-tile-sequence-quality "Permalink to this image")

**4. Per Sequence Quality Scores**

The per sequence quality score plot shows the distribution of the average quality score of each read in the file. The x-axis shows the average quality scores, and the y-axis represents the frequency of each quality score. For good data, this plot should have only one peak at the tail. If some other peaks show up, a subset of reads might have some quality issue.

[![per sequence quality scores](https://www.sc-best-practices.org/_images/per_sequence_quality_scores.jpg)](https://www.sc-best-practices.org/_images/per_sequence_quality_scores.jpg)

Fig. 3.6 A good (left) and a bad (right) per sequence quality score plot.[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-per-sequence-quality-scores "Permalink to this image")

**5. Per Base Sequence Content**

The per base sequence content plot reports the percent of each base position of all reads in the file for which each of the four nucleotides has been called. For single-cell data, it is not uncommon to see fluctuations at the start of the lines because the first bases of reads represent the sequence of the priming sites, which may not be perfectly random, as explained on the [QC Fail website](https://sequencing.qcfail.com/articles/positional-sequence-bias-in-random-primed-libraries/). This happens frequently in RNA-seq libraries, even though `FastQC` will call a warning or failure.

[![per base sequence content](https://www.sc-best-practices.org/_images/per_base_sequence_content.jpg)](https://www.sc-best-practices.org/_images/per_base_sequence_content.jpg)

Fig. 3.7 A good (left) and bad (right) per base sequence content plot.[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-per-base-sequence-content "Permalink to this image")

**6. Per Sequence GC Content**

The per sequence GC content plot shows the distribution of GC content over all of the reads in red and a theoretical (expected) distribution in blue. The central peak of the observed distribution should correspond to the overall GC content of the underlying transcriptome. Sometimes we see a wider or narrower distribution than the theoretical distribution because the GC content of the transcriptome might differ from the genome, which, in theory, should follow the distribution shown in blue. Such differences in the spread of the distributions are not uncommon, even though it may trigger a warning or failure. However, a complex distribution usually indicates a contaminated library. It is worth noting, however, that a GC content plot can be somewhat complicated to interpret in transcriptomics experiments, as the expected GC content distribution depends not only on the sequence content of the underlying transcriptome, but also on the expression of the genes in the sample, which are unknown.

[![Per Sequence GC Content](https://www.sc-best-practices.org/_images/per_sequence_gc_content.jpg)](https://www.sc-best-practices.org/_images/per_sequence_gc_content.jpg)

Fig. 3.8 A good (left) and a bad (right) per sequence GC content plot. The plot on the left is from [the RTSF at MSU](https://rtsf.natsci.msu.edu/genomics/tech-notes/fastqc-tutorial-and-faq/). The plot on the right is taken from [the HBC training program](https://hbctraining.github.io/Intro-to-rnaseq-hpc-salmon/lessons/qc_fastqc_assessment.html).[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-per-sequence-gc-content "Permalink to this image")

**7. Per Base N Content**

The per base N content plot shows the percent of bases at each position for which an `N` was called, which will occur when the sequencer has insufficient confidence to make a base call. In a high-quality library, we should not expect any noticeable non-zero `N` content throughout the line.

[![Per Base N Content](https://www.sc-best-practices.org/_images/per_base_n_content.jpg)](https://www.sc-best-practices.org/_images/per_base_n_content.jpg)

Fig. 3.9 A good (left) and a bad (right) per base N content plot.[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-per-base-n-content "Permalink to this image")

**8. Sequence Length Distribution**

The Sequence length distribution graph shows the distribution of the read lengths. In most single-cell chemistries, all reads will be of the same length. If trimming was performed before quality assessment, there may be some small variation in read lengths.

[![Sequence Length Distribution](https://www.sc-best-practices.org/_images/sequence_length_distribution.jpg)](https://www.sc-best-practices.org/_images/sequence_length_distribution.jpg)

Fig. 3.10 A good (left) and a bad (right) sequence length distribution plot.[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-sequence-length-distribution "Permalink to this image")

**9. Sequence Duplication Levels**

The sequence duplication level plot shows the distribution of the degree of duplication for read sequences (the blue line) and those after deduplication. As most single-cell platform requires multiple rounds of PCR, highly expressed genes usually express a large number of transcripts, and FastQC itself is not UMI aware, it is common that a small subset of sequences may have a large number of duplications. This may trigger a warning or failure for this module, but it does not necessarily represent a quality problem with the data. Still, the majority of sequences should have a low duplication level.

[![Sequence Duplication Levels](https://www.sc-best-practices.org/_images/sequence_duplication_levels.jpg)](https://www.sc-best-practices.org/_images/sequence_duplication_levels.jpg)

Fig. 3.11 A good (left) and a bad (right) per sequence duplication levels plot.[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-sequence-duplication-levels "Permalink to this image")

**10. Overrepresented Sequences**

The overrepresented sequences module lists all read sequences that make up more than 0.1% of the total number of sequences. We might see some overrepresented sequences from the highly expressed genes after PCR amplification, but most sequences should not be overrepresented. Note that if the possible source of the overrepresented sequences is not “No Hit”, it might indicate that the library is contaminated by the corresponding type of source.

[![Overrepresented Sequences](https://www.sc-best-practices.org/_images/overrepresented_sequences.jpg)](https://www.sc-best-practices.org/_images/overrepresented_sequences.jpg)

Fig. 3.12 An overrepresented sequence table.[](https://www.sc-best-practices.org/introduction/raw_data_processing.html#raw-proc-fig-fastqc-overrepresented-sequences "Permalink to this image")

**11. Adapter Content**

The adapter content module shows the cumulative percentage of the fraction of reads in which each of the adapter sequences has been observed at each base position. Ideally, we should not see any abundant adapter sequences in the data.

[![Adapter Content](https://www.sc-best-practices.org/_images/adapter_content.jpg)](https://www.sc-best-practices.org/_images/adapter_content.jpg)

Fig. 3.13 A good (left) and a bad (right) per sequence quality score plot. The plot on the right is from [the QC Fail website](https://sequencing.qcfail.com/articles/read-through-adapters-can-appear-at-the-ends-of-sequencing-reads/).