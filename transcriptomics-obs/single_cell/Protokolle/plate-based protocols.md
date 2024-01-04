
well plate based protocols where cells are physically separated into wells



Plate based protocols typically separate the cells physically into microwell plates

## Die generellen Schritte:

![[Pasted image 20240104133410.png]]

1. Zellsortierung durch z.B. orescent-activated cell sorting (FACS) -> Zellen werden basierend auf bestimmten Zellmarkern sortiert. Oder Sie werden mikropipetiert.
2. Selektierte Zellen werden dann einzeln auf Wells mit Zell Lysis Puffer plaziert.
3. Reverse Transkription und Amplifikation erfolgt in Wells.
4. pooling von Zellen mit z.B. Beads.


## Performance

 This allows for several hundreds of cells to be analyzed in a single experiment with 5000 to 10000 captured genes each.

# Beispiele für Technologien

 Plate based sequencing protocols include, but are not limited to, SMART-seq2, MARS-seq, QUARTZ-seq and SRCB-seq.

 Generally speaking, the protocols differ in their [[multiplexing]] ability. For example, MARS-seq allows for three barcode levels, namely molecular, cellular and plate-level tags, for robust multiplexing capabilities. SMART-seq2 on the contrary, does not allow for early multiplexing limiting cell numbers.

A systematic comparison of protocols by Mereu et al in 2020 revealed that QUARTZ-seq2 is able to capture more genes than SMART-seq2, MARS-seq or SRCB-seq per cell, which means QUARTZ-seq2 is able to capture cell-type specific marker genes well, allowing for confident cell type annotation.

# Stärken und Schwächen:

Strengths:

- Recovers many genes per cell, allowing for a deep characterization.
    
- Possible to gather information before the library preparation e.g. through FACS sorting to associate information such as cell size and the intensity of any used labels with well coordinates.
    
- Allows for full-length transcript recovery.
    

Limitations:

- The scale of plate-based experiments is limited by the lower throughput of their individual processing units.
    
- Fragmentation step eliminates strand-specific information 
    
- Depending on the protocol, plate based protocols might be labor-intensive with many required pipetting steps, leading to potential technical noise and batch effects