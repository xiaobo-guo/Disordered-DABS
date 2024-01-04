# DisjointDABS
This repository hosts the paper "Disjoint-DABS: A Benchmark for Dynamic Aspect-Based Summarization in Disorganized Texts."

## Dataset
Access the Disjoint-DABS dataset at [Harvard Dataverse](https://doi.org/10.7910/DVN/OEE1RI).

### Disjoint-DABS
We offer three zip files: **D-CnnDM.zip**, **D-WikiHow.zip**, and **D-WikiHow-sample.zip**. The first two are as per the paper, and the last is a sample for Section 7.1.

The datasets are pre-split into train, validation, and test sets. Each zip file includes:
* `train.csv`
* `validation.csv`
* `test.csv`

Containing columns:
* `id`: Unique identifier.
* `article`: Shuffled source article.
* `highlights`: Groundtruth summary.
* `original article`: Unshuffled source article.
* `sentence id`: The label for showing which summary this source article sentence beloing to.

Sentences are split with `[SENSEP]`, and aspects/topics with `[SEP]`.

### Dataset For Summarization Model
For fine-tuning the summarization model, we provide single-aspect article-summary pairs. These are from **cnn_dailymail** and **WikiHowSep**. Each dataset includes `train.csv`, `validation.csv`, and `test.csv`, with columns:
* `id`: Unique identifier.
* `article`: Source article.
* `highlights`: Groundtruth summary.

Further details in the respective original papers.

## Baseline Generated Summaries
We provide generated summaries for baselines in `result.zip` for research and human evaluation. The file structure is:
``
./{dataset}/{random_seed}/{method}/
``
The `prompting` method summaries are available with `random_seed` of 10. Each method folder contains `prediction_results.json` and `generated_predictions.json`.

`prediction_results.json` includes all automatic metrics from the paper. `generated_predictions.json` contains generated summaries. Each line in `generated_predictions.json` includes:
* `article`: Shuffled source article.
* `ref`: List of ground truth aspect-based summaries.
* `generation`: List of generated aspect-based summaries.
* `score`: Mean score for generated summaries.
* `score_per_aspect`: Aspect-level score for generated summaries.

Generated and groundtruth summaries are aligned, including padding.


