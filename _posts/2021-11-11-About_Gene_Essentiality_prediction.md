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
1. Campos, T. L., Korhonen, P. K., Gasser, R. B., & Young, N. D. (2019). An Evaluation of Machine Learning Approaches for the Prediction of Essential Genes in Eukaryotes Using Protein Sequence-Derived Features. Computational and Structural Biotechnology Journal, 17, 785–796. https://doi.org/10/gm9pc3
2. Campos, T. L., Korhonen, P. K., Hofmann, A., Gasser, R. B., & Young, N. D. (2020). Combined use of feature engineering and machine-learning to predict essential genes in Drosophila melanogaster. NAR Genomics and Bioinformatics, 2 (3), lqaa051. https://doi.org/10/gm9pc7
3. Campos, T. L., Korhonen, P. K., Sternberg, P. W., Gasser, R. B., & Young, N. D. (2020). Predicting gene essentiality in Caenorhabditis elegans by feature engineering and machine-learning. Computational and Structural Biotechnology Journal, 18, 1093–1102. https://doi.org/10/gh33dp
4. Gurumayum, S., Jiang, P., Hao, X., Campos, T. L., Young, N. D., Korhonen, P. K., Gasser, R. B., Bork, P., Zhao, X.-M., He, L., & Chen, W.-H. (2021). OGEE v3: Online GEne Essentiality database with increased coverage of organisms and human cell lines. Nucleic Acids Research, 49 (D1), D998–D1003. https://doi.org/10/gm9pc6

# The feasibility of predicting GE using graph neural networks.
