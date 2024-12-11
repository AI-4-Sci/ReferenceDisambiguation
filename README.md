# ReferenceDisambiguation

<!-- Short Introduction what this repo is about -->
This repository contains the dataset, annotation framework and supplementary results for the work *"Disambiguation of Implicit Scientific References on X"*, currently under review at the **ACM Web Conference (WWW 2025)**.

__Table of contents:__
- [Directory Structure](#directory-structure)
- [Data](#data)
- [Publication](#publication)
- [Reproducibility](#reproducibility)
  - [Annotation](#annotation)
- [Licensing](#licensing)
- [Contact](#credits)
- [Acknowledgment](#acknowledgment)
- [References](#references)


## Directory Structure
=======================<br/>
This repository contains the following directories and files:

1. **data**
   1. **sample_explicit_references.tsv** samples from the explicit references
   2. **sample_implicit_references.tsv** samples from the manually annotated implicit references
   3. **full_explicit_references.tsv** the explicit references *TO BE ADDED*
   4. **full_implicit_references.tsv** the manually annotated implicit references *TO BE ADDED*
3. **data_analysis** supplementary material for the preliminary data analysis (see Section 3 of the research paper)
   1. **topic_clusters.png** HDBSCAN clusters of SPECTER embeddings of study titles, used to determine the top20 topics from the CORD-19 corpus
   2. **top20_topic_plots** temporal distribution plots for the top20 topics, each plot compares the distribution of explicit and implicit references 
   3. **topic_keywords_top50_studies.tsv** keywords used to sample candidate implicit references before annotation
   4. **topic_stats.tsv** statistics computed for each reference-type for all topics. Metrics include number of tweets and Pearson correlation
4. **annotation_protocol_examples.pdf** the annotation framework provided to the annotators, along with definitions and examples provided to annotators
9. **README.md** this file

## Data
The full data is not immediately publicly available, as it is being used for an upcoming CheckThat! Lab which we organize at CLEF2025. However, samples are already available for reviewers (see data/sample_explicit_references.tsv and data/sample_implicit_references.tsv). The full data will be made publicly available before the WWW camera-ready deadline.

## Reproducibility
### Preliminary data analysis (Section 3 in the paper): 
- To extract top-keywords for each topic, we follow the methodology from BERTopic [1], where we use a c-TF-IDF algorithm [2] to extract the top-keyword for each of the top-20 topics in our clusters.
### Annotation (Section 4.3 in the paper): 
- Prior to the annotation, individual training sessions were held with the annotators to examine examples and counterexamples and ensure that the labeling task was understood correctly.


## Publication
<!-- TODO: Update with correct information once we uploaded the paper somewhere -->
Please cite the following paper if you are using the dataset or annotation framework, or citing empirical results from the paper:

1. *TO BE ADDED*

## Licensing
This dataset is published under CC BY 4.0 license. It allows reusers to distribute, remix, adapt, and build upon the material in any medium or format, so long as attribution is given to the creator (https://creativecommons.org/licenses/by/4.0/)

## Contact
Please contact salim.hafid@proton.me

## Acknowledgment
<!-- TODO: Update with french grant number -->
This work is supported by the AI4Sci grant, co-funded by MESRI (France) and BMBF (Germany, grant 01IS21086) and the French National Research Agency (ANR).

## References
- [1] Grootendorst, M. (2022). BERTopic: Neural topic modeling with a class-based TF-IDF procedure. arXiv preprint arXiv:2203.05794.
- [2] c-TF-IDF algorithm: https://github.com/MaartenGr/cTFIDF
