# Cleaning and Structuring the Label Space of the iMet Collection 2020 (CVPR 2021 FGVC)

### [Full paper (9 pages)](https://arxiv.org/abs/2106.00815) | [Extended abstract (4 pages)](https://drive.google.com/file/d/1pE1vyvym6WC-M5_unL9X7EwKlP5NKPC6/view?usp=sharing)

This repo provides the code and cleaned labels for our CVPR 2021 FGVC workshop paper.

___

"Cleaning and Structuring the Label Space of the iMet Collection 2020." [Vivien Nguyen*](https://viviehn.github.io/) and [Sunnie S. Y. Kim*](https://sunniesuhyoung.github.io/). CVPR 2021 [The Eight Workshop on Fine-Grained Visual Categorization](https://sites.google.com/view/fgvc8/).

**Abstract**: The iMet 2020 dataset is a valuable resource in the space of fine-grained art attribution recognition, but we believe it has yet to reach its true potential. In this work, we document the unique properties of the dataset and observe that many of the attribute labels are noisy, more than is implied by the dataset's description. Oftentimes, there are also semantic relationships between the labels (e.g., identical, mutual exclusion, subsumption, overlap with uncertainty), which we believe are underutilized. We propose an approach to cleaning and structuring the iMet 2020 labels, and discuss the implications and value of doing so. Further, we demonstrate the benefits of our proposed approach through several proof-of-concept experiments.

___

## The iMet Collection dataset

The iMet Collection is a dataset for fine-grained art attribute recognition, introduced in the 6th FGVC Workshop at CVPR 2019. It is the first high-quality artwork image dataset with professional photographs of artworks from The Metropolitan Museum of Art and attribute labels curated or verified by experts. 

**Dataset paper**: "The iMet Collection 2019 Challenge Dataset." Chenyang Zhang, Christine Kaeser-Chen, Grace Vesom, Jennie Choi, Maria Kessler, Serge Belongie. [arXiv:1906.00901](https://arxiv.org/abs/1906.00901).

**iMet 2020 dataset**: https://www.kaggle.com/c/imet-2020-fgvc7

## Our proposed changes

In ``label_cleaning.ipynb``, we demonstrate our proposed changes and clean/structure the iMet 2020 (training) labels. For compatibility, we don't change the size of the label space (3,474 attributes) and only make modifications that involve adding attribute label(s) to certain samples.

`/edgelists` contains a series of text files listing various attribute pair relationships. ``graph_pm.ipynb`` demonstrates how to create [NetworkX](https://networkx.org/) graphs from the existing iMet attributes, load edgelists, and use the resulting graph to compute graph-based performance measures (e.g. the proposed metric in our workshop paper). Again, for compatibility, no labels (i.e. nodes) are added or removed, only relationships (i.e. edges). `train_example.csv` contains a sample CSV for the format expected by `graph_pm.ipynb`.

These changes, edgelists, etc. are by no means complete; any number of hierarchical relationships could be created depending on the use case/application. 


## Citation

```
@misc{nguyen2021imet,
  author = {Vivien Nguyen and Sunnie S. Y. Kim},
  title = {Cleaning and Structuring the Label Space of the iMet Collection 2020},
  booktitle = {CVPR 2021 The Eight Workshop on Fine-Grained Visual Categorization},
}
```
