# Evaluation Results: TCM Herb Composition Extraction via Hungarian Matching

## Overview & Methodology
This repository provides an optimal one-to-one matching evaluation between ground-truth Traditional Chinese Medicine (TCM) formula compositions and Large Language Model (LLM) extraction outputs. To handle potential size mismatches and row misalignment, the evaluation leverages the Hungarian Algorithm (`scipy.optimize.linear_sum_assignment`) applied to a pairwise Jaccard Similarity matrix. The pipeline standardizes raw herb strings into set representations, solves the global assignment problem to maximize set similarities, and records itemized performance metrics.

## Dataset & Metrics Breakdown (`hungarian_matched_evaluations_stats.csv`)
The dataset `hungarian_matched_evaluations_stats.csv` contains the complete itemized alignment and evaluation results. Each entry includes:

* **Identification & Raw Formulations**: Ground-truth index (`標準索引`), matched LLM index (`匹配LLM索引`), and their corresponding raw herb composition strings (`standard_純單方藥組成` and `LLMmodel_純單方藥組成`).
* **Set Overlaps**: Raw herb counts for both reference and prediction (`標準藥材數`, `LLM萃取藥材數`), along with their exact intersection count (`交集數`).
* **Evaluation Metrics**: Pairwise performance scores calculated for each matched sample, including `Jaccard_Similarity`, exact-match `Precision`, `Recall`, and `F1_Score`.

## Usage
The CSV file can be directly loaded using Python (`pandas.read_csv('hungarian_matched_evaluations_stats.csv')`) or any standard spreadsheet tool for custom statistical analysis and downstream benchmarking visualization.
