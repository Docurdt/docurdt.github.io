---
title: Some ideas about gene essentiality prediction and graph neural network
date: 2021-11-11 18:38:09 +1000
categories: [Research, Sequence analysis]
tags: [gene essentiality]     # TAG names should always be lowercase
---

# What is the definition of gene essentiality (GE)?
Gene essentiality is a core concept of genetics, and has important relevance in relation to fundamental areas such as evolutionary, and systems and synthetic biology, and applicability in drug development. Essential genes (EGs) are often responsible for important biological processes and cellular fitness in an organism, and are critical for its survival. The essentiality of a gene is highly dependent on various factors including the genetic context, genetic background of the host and environment (15). Hence, gene essentiality is not a static, but rather a context-dependent property of a gene.

# How to annotate it?
All ‘lethal’ terms and their descendants were extracted from the phenotype_ontology. WS270.obo file and all ‘not lethal’ terms from the association file (phenotype_association.WS270.wb; column 4). We used the latter file to identify individual genes reported (in the peer-reviewed literature) to be linked to ‘lethal’ or ‘not lethal’ phenotypes upon RNAi. For each gene, we then calculated an essentiality score (ES), defined as the total number of RNAi experiments reporting essential/lethal (E) terms squared divided by the total number of experiments reporting essential/lethal and non- essential/viable terms (T) squared (E2/T2). A gene was provisionally assigned as ‘‘essential” (ES > 0.9) or ‘‘non-essential” (ES < 0.1); any other genes with an ES between !0.1 and 0.9 were assigned as ‘‘conditionally-essential”.

# Related publication resources.

# Previous studies of predicting GE.

# The feasibility of predicting GE using graph neural networks.
