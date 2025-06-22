---
title: Hierarchical Datasets for Feature Selection in Genomics
date: '2025-06-22'
categories:
  - Dataset
tags:
  - Hierarchical
---

```bash
mkdir -p static/datasets
cd static/datasets
for f in CellCycle Church Derisi Eisen Expr Gasch1 Gasch2 Sequence SPO; do
  wget https://oliveira-sh.github.io/datasets/${f}.arff
done
cd -
````

---

These `.arff` files are sourced from functional genomics research (Amanda Clare), annotated using FunCat and Gene Ontology (GO), ideal for hierarchical multi-label classification with tools like `Clus` or `GMNB` ([ebi.ac.uk][1], [dtai.cs.kuleuven.be][2]). In the table below i summarized the main characteristics of the ten freely-available datasets used.

## Datasets

* **[CellCycle](/datasets/CellCycle.arff)**
  Tracks gene expression during yeast cell-cycle phases. Useful for modeling time-series or cell-state dependent features.

* **[Church](/datasets/Church.arff)**
  Focuses on gene expression under stress conditions with categorical functional labels.

* **[Derisi](/datasets/Derisi.arff)**
  Early yeast expression dataset (cDNA arrays), frequently used in clustering and hierarchical classification.

* **[Eisen](/datasets/Eisen.arff)**
  From Eisen et al.’s foundational work on clustering yeast gene expression profiles.

* **[Expr](/datasets/Expr.arff)**
  A general gene-expression collection, potentially combining various experiments for broader analysis.

* **[Gasch1](/datasets/Gasch1.arff)** & **[Gasch2](/datasets/Gasch2.arff)**
  Stress response datasets from Gasch et al., capturing diverse conditions like heat shock and osmotic stress.

* **[Sequence](/datasets/Sequence.arff)**
  Annotation based on gene sequence features—includes functional categories useful for integrative modeling.

* **[SPO](/datasets/SPO.arff)**
  Likely relates to sporulation gene expression in yeast, useful for classification of developmental states.

| Dataset   | Num of attributes | Num of classes | Number of classes per level  |
| --------- | ----- | ----- | ---------------------------- |
| Cellcycle | 77    | 499   | 18 - 80 - 178 - 142 - 77 - 4 |
| Church    | 27    | 499   | 18 - 80 - 178 - 142 - 77 - 4 |
| Derisi    | 63    | 499   | 18 - 80 - 178 - 142 - 77 - 4 |
| Eisen     | 79    | 461   | 18 - 76 - 165 - 131 - 67 - 4 |
| Expr      | 551   | 499   | 18 - 80 - 178 - 142 - 77 - 4 |
| Gasch1    | 173   | 499   | 18 - 80 - 178 - 142 - 77 - 4 |
| Gasch2    | 52    | 499   | 18 - 80 - 178 - 142 - 77 - 4 |
| Pheno     | 69    | 455   | 18 - 74 - 165 - 129 - 65 - 4 |
| Seq       | 478   | 499   | 18 - 80 - 178 - 142 - 77 - 4 |
| Spo       | 80    | 499   | 18 - 80 - 178 - 142 - 77 - 4 |


---

## Further reading & resources

* Clus tool examples and settings (incl. `run_sc.pl`, `run_hsc.pl`, eval classes) are available via the HMC dataset page ([dtai.cs.kuleuven.be][2], [pmc.ncbi.nlm.nih.gov][4]).
* For sequence-based functional prediction: see datasets like **Sequence.arff**, ideal for integrating sequence-derived features with expression data.
* Consider reading Pliakos et al. (2015) on representational power in gene features—addresses challenges like non-unique feature mappings ([dtai.cs.kuleuven.be][2]).

---

[1]: https://www.ebi.ac.uk/training/online/courses/machine-learning-drug-discovery/identifying-targets-for-cancer-using-gene-expression-profiles/?utm_source=chatgpt.com "Identifying targets for cancer using gene expression profiles"
[2]: https://dtai.cs.kuleuven.be/clus/hmcdatasets/?utm_source=chatgpt.com "HMC Software and Datasets - DTAI"
[3]: https://webthesis.biblio.polito.it/16763/1/tesi.pdf?utm_source=chatgpt.com "[PDF] Politecnico di Torino"
[4]: https://pmc.ncbi.nlm.nih.gov/articles/PMC11847294/?utm_source=chatgpt.com "Protocol to denoise spatially resolved transcriptomics data utilizing ..."
