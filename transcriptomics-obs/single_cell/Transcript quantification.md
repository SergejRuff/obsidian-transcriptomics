
![[Pasted image 20240104122218.png]]
Transcript quantification is the process of counting the hits of the sequenced transcripts against the gene sequences.
 After sequencing, these RNA fragments are then bioinformatically aligned to the transcriptome. Each fragment constitute a read which is then assigned to the corresponding transcript / gene.
 > Wie viele Transkripte/ Reads sind pro Gen enthalten.
 > Wieviele Original-Moleküle sind enthalten (Transkripte werden oft amplifiziert).


There are two major approaches to transcript quantification: 
- [[ full-length Quantification]] and 
- [[tag-based Quantification]] .
- Full Length muss für Read length adjustiert werden (FPKM) oder (TPM). Tag Based muss nicht adjustiert werden.
- Full Length kann nur [[plate-based protocols]] nutzen.

 The transcript amplification process is a critical step in any RNA-seq sequencing run, to ensure that the transcripts are abundant enough for [[quality control]] and sequencing.

During this process, which is typically conducted with polymerase chain reaction (PCR), copies are made from identical fragments of the original molecule. Since the copies and the original molecules are indistinguishable, determining the original number of molecules in samples becomes challenging.
> Oft [[UMI]] benutzt, um Original-Moleküle zu bestimmen.