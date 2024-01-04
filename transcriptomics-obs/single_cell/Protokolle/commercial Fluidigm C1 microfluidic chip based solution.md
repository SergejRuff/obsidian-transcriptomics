the commercial Fluidigm C1 microfluidic chip based solution which loads and separates cells into small reaction chambers.

![[Pasted image 20240104133328.png]]

The commercial Fluidigm C1 system is a microfluidic chip, which loads and separates cells into small reaction chambers in an automated manner.


The CEL-seq2 and SMART-seq (version 1) protocols are using the Fluidigm C1 chips in their workflow, allowing the RNA extraction and library preparation steps to be conducted together, thereby decreasing the required manual labor.

# Vor und Nachteile

Vorteile:

Since the amplification step is carried out in individual wells, [[full-length Quantification]] and sequencing is possible, effectively reducing the 3’ bias of many other single-cell RNA-seq sequencing protocols.

Nachteile:

- Benötigt homogene Zellmixturen ->  since the cells will reach different locations on the microfluidic chip based on their size, which could introduce potential location bias.
- Teuer

Strengths:

- Allows for full-length transcript coverage.
    
- Splicing variants and T/B cell receptor repertoire diversity can be recovered.
    

Limitations:

- Only allows for the sequencing of up to 800 cells[[Fluidigm, 2022](https://www.sc-best-practices.org/introduction/scrna_seq.html#id116 "Fluidigm. Single-cell analysis with microfluidics. https://www.fluidigm.com/area-of-interest/single-cell-analysis/single-cell-analysis-with-microfluidics, 2022. Accessed: 2022-05-07.")].
    
- More expensive per cell than other protocols.
    
- Only about 10% of the extracted cells are captured, which makes this protocol unsuitable for rare cell types or low input.
    
- The used arrays only capture specific cell sizes, which may bias the captured transcripts.