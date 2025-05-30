# Automated main concept generation for narrative discourse assessment in aphasia
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-red.svg)](#python)
[![paper](https://img.shields.io/badge/Link%20to-paper-you_like?logoColor=blue&color=green)](https://github.com/slanglab/aphasia/blob/main/ACL2025/Aphasia_ACL.pdf)
[![poster](https://img.shields.io/badge/Link%20to-poster-you_like?logoColor=blue&color=orange)](https://docs.google.com/presentation/d/1cyZt2GJBX3EBr_F2UbjBdgs0R4rTCLonFFYPHG-GUyE/edit?usp=sharing)
[![lightning-talk](https://img.shields.io/badge/lightning-talk-you_like?logoColor=blue&color=green)](https://docs.google.com/presentation/d/1cFGv6r3njzEUmd8bukarrUry8J8O2Bb8fzEgW7z5hvA/edit?usp=sharing)


This is the official repository for our paper: Automated main concept generation for
narrative discourse assessment in aphasia. This repository contains code to reproduce the modeling experiments discussed in our paper.

An earlier version of this work was presented at the Clinical Aphasiology Conference 2025. The abstract is available in the ```CAC2025``` directory.


### Set up

Follow these instructions to set up the repository.

```
git clone https://github.com/gnkitaa/aphasia-narrative.git
cd aphasia-narrative

conda create -y --name aphasia python=3.9
conda activate aphasia
pip install -r requirements.txt

git clone https://github.com/openai/openai-cookbook.git
```

### Datasets
- We release a novel BATS dataset, containing narratives with human-annotated main concepts, which are empirically
derived through extensive analysis of hundreds of story retellings from healthy participants (Kurland et al.,
2021; Richardson and Dalton, 2016, 2020) and have been used to assess patients with aphasia (Kurland et al., 2024b). The dataset is provided under ```data/BATS``` directory.


- We also evaluate our method on an existing narrative summarization dataset (Zhao et al., 2022). Please refer to [NarraSum](https://aclanthology.org/2022.findings-emnlp.14/) for more details.

### MC generation 
To generate main concepts run ```MCGenerator/generate_mcs_bats.ipynb``` for BATS dataset and ```MCGenerator/generate_mcs_narrasum.ipynb``` for narrasum dataset. 

Different prompts used for MC generation are provided in ```MCGenerator/Prompts``` directory.

### Semantic deduplication
To cluster main concepts that are similar in meaning, run ```MCGenerator/clustering_bats.ipynb``` for BATS dataset and ```MCGenerator/clustering_narrasum.ipynb``` for narrasum dataset.

### MC evaluation
To evaluate the generated main concepts, run ```MCEvaluator/evaluate_bats.ipynb``` for BATS dataset and ```MCEvaluator/evaluate_narrasum.ipynb``` for narrasum dataset. The notebooks also plot the recall versus yield tradeoff curves discussed in the paper.
