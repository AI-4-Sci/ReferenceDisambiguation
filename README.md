# ReferenceDisambiguation

<!-- Short Introduction what this repo is about -->
This repository contains the dataset, annotation framework and supplementary results for the work *"Disambiguation of Implicit Scientific References on X"*, currently under review at the **ACM Web Conference (WWW 2025)**.

__Table of contents:__
- [Directory Structure](#directory-structure)
- [Data and Samples for Reviewers](#data-and-samples-for-reviewers) (WWW short-paper submission)
- [Publication](#publication)
- [Reproducibility](#reproducibility)
  - [Data Analysis](#analysis)
  - [Annotation](#annotation)
- [Licensing](#licensing)
- [Contact](#contact)
- [Acknowledgment](#acknowledgment)
- [References](#references)


## Directory Structure
=======================<br/>
This repository contains the following directories and files:

1. **data**
   1. **samples_for_reviewers.tsv**: <u>samples for reviewers for the WWW short-paper submission</u>
   3. **full_explicit_references.tsv**: the explicit references *(TO BE ADDED)*
   4. **full_implicit_references.tsv**: the manually annotated implicit references *(TO BE ADDED)*
3. **data_analysis**: supplementary material for the preliminary data analysis (see Section 3 of the research paper)
   1. **topic_clusters.png**: HDBSCAN clusters of SPECTER embeddings of study titles, used to determine the top20 topics from the CORD-19 corpus
   2. **top20_topic_plots**: temporal distribution plots for the top20 topics, each plot compares the distribution of explicit and implicit references 
   3. **topic_keywords_top50_studies.tsv** keywords used to sample candidate implicit references before annotation *(TO BE ADDED)*
   4. **topic_stats.tsv**: statistics computed for each reference-type for all topics. Metrics include number of tweets and Pearson correlation
4. **annotation_protocol_examples.pdf**: the annotation framework provided to the annotators, along with definitions and examples provided to annotators
9. **README.md**: this file

## Data & Samples for Reviewers
Our TweetCite corpus consists of tweet-study pairs, where tweets reference papers from CORD-19. Tweets contain two distinct reference-types: explicit references (where the URLs are deleted to approximate implicit references), and manually annotated implicit references. Here are examples of both reference-types for a common scientific publication:
- **Scientific publication:** "Effectiveness of Covid-19 Vaccines against the B.1.617.2 (Delta) Variant"
    - **Explicit references**:
        - *"only modest differences in vaccine effectiveness were noted with the delta variant as compared with the alpha variant after the receipt of two vaccine doses . ' https://pubmed.ncbi.nlm.nih.gov/34289274/"*
        - *"great article - synopsis : 2 doses of pfizer vaccine effective against delta variant at 88 % compared to 94 % against original covid - 19 strain ! can't stop at 1 dose #covidvaccine effectiveness of covid - 19 vaccines against the b . 1.617 . 2 ( delta ) variant | nejm https://pubmed.ncbi.nlm.nih.gov/34289274/"*
    - **Implicit references**:
        - *"peer-reviewed in the new england journal of medicine regarding delta ( b . 1.617 . 2 ): • pfizer is ~ 90 % effective • astrazeneca is ~ 70 % effective this falls in line with vaccine efficacy of other variants . yes , the vaccines are indeed effective against delta."*

The full data is not immediately publicly available, as it is being used for an upcoming CheckThat! Lab which we organize at CLEF2025. However, samples are already available for reviewers at:
- data/samples_for_reviewers.tsv

**The full data will be made publicly available before the WWW camera-ready deadline.**

## Reproducibility
### Data analysis (Section 3 in the paper): 
- To extract top-keywords for each topic, we follow the methodology from BERTopic [1], where we use a c-TF-IDF algorithm [2] to extract the top-keyword for each of the top-20 topics in our clusters.
### Annotation (Section 4.3 in the paper): 
- Prior to the annotation, individual training sessions were held with the annotators to examine examples and counterexamples and ensure that the labeling task was understood correctly.
- During annotation, annotators answered two questions: Q1 (*"Does the tweet mention a SINGLE scientific study? If not, move on to the next tweet"*), and Q2 (*"Does the tweet text mention the candidate study?"*). Q2 was answered only if Q1 = "Yes". In Round 1, annotators directly answered Q2 on samples where Q1 was answered 'Yes' by a majority vote (at least 2 out of 3). In Round 2, to try to sample more data, we conducted two iterations.  In the first iteration, all annotators labeled tweets by themselves. Then we checked the agreement on Q1 = "Yes" samples and collected the cases where at least two annotators answered "Yes" and at least one annotator answered "No". For those cases, the Q1 answer was consolidated as "Yes". Those tweets were then redistributed for a second iteration, this time only to annotators who had previously answered 'No' to Q1.


## Publication
<!-- TODO: Update with correct information once we uploaded the paper somewhere -->
Please cite the following paper if you are using the dataset or annotation framework, or citing empirical results from the paper:

1. *(TO BE ADDED)*

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
