Unique Molecular Identifier

Teil von [[tag-based Quantification]]

# anderer Name

random barcodes

# Wozu UMI?

The usage of UMIs is a common solution to quantify the original, non-duplicated molecules.

he ability to accurately identify PCR duplicates is important for downstream analysis to rule out - or be aware of [[amplification biases]]

 The usage of UMIs further allows for [[normalization]] of gene counts to be performed without a loss of accuracy

Benutzt in [[Microfluidic device-based protocols]]

# Woraus bestehen sie?

These ‘barcodes’ consist of short random nucleotide sequences that are added to every molecule in the sample as a unique tag.

# Wann angebracht?

UMIs must be added during library generation before the amplification step.

## Wieso kann man UMIs nicht bei Long Reads Sequenziergeräten wie PacBio oder Nanopore nutzen?


Long Reader haben eine hohe Errorrate. Führen also Mutationen ein.

Weil UMIs nicht verändert werden dürfen, um auch wieder erkannt zu werden. Wenn man aber eine hohe Fehlerrate hat, dann werden die UMIs mutieren und man kann das Transkript nicht dem Original-Molekül zuweisen.

Siehe [[ScNaUmi-seq]] als eine Möglichkeit, wo es nach vielen Anpassungen doch ging.


