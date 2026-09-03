# Interpretable Markovian Models of Animal Communication

This repository contains the data, preprocessing pipeline, analyses, visualizations, and generation tools used to investigate sequence structure in fish behavior and birdsong. Analysis files are numbered in the order that they should be run.

## Abstract 

Animal communication can be represented as sequences of discrete, categorical signals. These signals alone often do not convey information, but instead
are combined to form complex, meaningful behavioral motifs. Therefore, a prerequisite in understanding the meaning behind communication is understanding how these signals are organized. Achieving this requires both exploratory
methods for identifying structure, as well as experimental paradigms for testing
hypotheses about that structure.

This thesis proposes a pipeline for approximating complex historical dependencies in behavioral sequences using fully interpretable analysis methods.
Specifically, it proposes a family of probabilistic Markovian models based on
generalizations of Markov chains. These models can integrate more complex
historical information in sequences, referencing customizable strategies for extracting key historical information in sequences. This thesis presents two such
strategies, both motivated by biological applications and theory, and evaluates their performance in synthetic datasets mimicking features of collected
empirical corpora.

These models are applied to two animal communication datasets, featuring
two different behavioral modalities. The first dataset consists of postural behavioral sequences collected from six species of cichlid during dyadic territory
disputes. The second consists of acoustic recordings of song from six male
Bengalese finches.

The analysis revealed that Bengalese finch song demonstrates a highly deterministic process at the beginnings which violates modeling assumptions. To
address this, this thesis describes a method for detecting and extracting this
process from sequences by adapting tries, a data structure typically used in
computer science applications.

Finally, novel corpora were generated using fitted models, which can be
used for future playback experiments to move from exploratory analysis to hypothesis testing. Possible experimental designs and hypotheses were explored,
as well as strengths and limitations of the proposed methods.

## Repo Structure

```text
fish-and-finches/
├── analyses/
│   ├── 01-preprocessing.Rmd
│   │   Data wrangling, ribbon plots, descriptive statistics,
│   │   prefix extraction, and processed corpora
│   ├── 02-analysis validation.ipynb
│   │   Evaluation of modeling strategies using synthetic datasets
│   ├── 03-fish-analyses.ipynb
│   │   Markovian modeling for fish corpora
│   ├── 04-bird-analyses.ipynb
│   │   Markovian modeling for bird corpora
│   ├── 05-postprocessing.Rmd
│   │   Visualizations of simulation results, modeling results
│   │   from empirical corpora, and empirical vs. generated
│   │   corpora comparisons
│   └── simResults.csv
│       simulation results from Analysis 02
│
├── bird-data/
│   ├── raw/
│   │   Contains .txt files for each bird of full, collapsed,
│   │   cropped full, and cropped collapsed songs, as well as
│   │   .csv files of original raw data
│   ├── birdResultsCropped.csv
│   │   Markovian modeling results of cropped bird corpora
│   │   from Analysis 04
│   └── prefixes.csv
│       Extracted full prefixes
│
├── fish-data/
│   ├── raw/
│   │   Contains .csv files of original raw postural data
│   └── fishResults.csv
│       Markovian modeling results from Analysis 03
│
├── generation-app/
│   ├── 06-app.ipynb
│   │   Notebook for sequence generation and heatmap visuals
│   │   based on modeling results from Analyses 03 and 04
│   └── []_playback.txt
│       200-line generated corpora for each fish species and bird
│
├── plots/
│   └── Plots generated from notebooks
│
└── requirements.txt
    Requirements for the Python environment

```

