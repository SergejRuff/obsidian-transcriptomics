
What does array data look like in for example array express?

How do I know if data is array data and not rnaseq?

ARRAY: TechnologyArray assay or Study typetranscription profiling by array
![[Pasted image 20231220140723.png]]

When working with Gene expression data, you will usually find processed data on array express.
For example: https://www.ebi.ac.uk/biostudies/arrayexpress/studies/E-GEOD-39259

The processed files are saved usually in a txt file:
https://ftp.ebi.ac.uk/biostudies/fire/E-GEOD-/259/E-GEOD-39259/Files/GSM958898_sample_table.txt

The txt files look like this (Only proccessed.Raw Files look different):

![[Pasted image 20231220135643.png]]

The files names are  for example: 
> GSM958868_sample_table.txt	
> Each GSM entry typically corresponds to a specific biological sample -> cells,tissue

commonly associated with gene expression data and is part of the Gene Expression Omnibus (GEO) database, which is maintained by the National Center for Biotechnology Information (NCBI).
In the GEO database, "GSM" stands for "GEO Sample,"
and the number following it (in this case, "958868") is a unique identifier for a particular sample within the database.

![[Pasted image 20231220141509.png]]
https://www.ebi.ac.uk/biostudies/arrayexpress/studies/E-GEOD-39259/sdrf

The image for example we see that GSM958861 1 corresponds to the spleen of a mouse.
WARNING: the number corresponds to the sample/tissue, not the organism, which you can see in teh image. GSM958861 1 and GSM958862 1 are from the same animal, but one uses the spleen and one uses the liver part of the same mouse.

Sample count 40 -> Meaning there should be 40 sample txt files: one for each sample.
Typically more samples than organisms.

In gene expression studies using microarrays, RNA samples are often labeled and hybridized to microarray chips containing probes. The probes are designed to bind specifically to certain RNA sequences, allowing researchers to measure the abundance of specific RNA molecules.

The identifiers in your dataset, such as "A_51_P616356" or "A_52_P580582," likely refer to specific probes or probe sets on the microarray. 

Each identifier (e.g., A_52_P616356) is associated with a numerical value (e.g., 6.030949379).

**Reporter Identifier (e.g., A_52_P616356):** These are likely identifiers for specific probes or reporters on the microarray chip. Each identifier corresponds to a unique spot on the array that detects the expression of a specific gene or transcript.
**VALUE (e.g., 6.030949379):** This represents the numerical value associated with the expression level of the gene or transcript corresponding to the Reporter Identifier.

those values can be used for analysis to determin DEG.