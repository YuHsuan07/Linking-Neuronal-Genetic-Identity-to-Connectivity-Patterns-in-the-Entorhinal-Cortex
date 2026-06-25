# Linking-Neuronal-Genetic-Identity-to-Connectivity-Patterns-in-the-Entorhinal-Cortex

## Overview
This study investigates the relationship between gene expression and brain connectivity, focusing on how cell-body position within the entorhinal cortex relates to neuronal identity and projection patterns.

We analysed two datasets. The first consists of neurons from the entorhinal cortex in a multiplexed error-robust fluorescence in situ hybridisation (MERFISH) spatial transcriptomics dataset. The second is a single-neuron reconstruction (SNR) dataset describing projection patterns of neurons in layer 5a of the entorhinal cortex.

First, a random forest classifier was trained to examine the relationship between cell-body position and gene expression–related labels. We then applied k-means clustering to define data-driven neuronal projection types based on projection features. Next, a k-nearest neighbours classifier was used to investigate whether cell-body position can predict these projection-defined types. Finally, a pretrained SNR-based classifier was applied to MERFISH spatial coordinates to infer neuronal supertypes from projection features.

Our results suggest that cell-body position contains limited but measurable information about gene expression and brain connectivity, allowing for modest predictive performance in classification tasks.

## Methods
This project investigates the relationship between neuronal spatial organisation, transcriptomic identity, and projection patterns using MERFISH spatial transcriptomics and single-neuron reconstruction (SNR) data.
- Data cleaning and preprocessing: For MERFISH, singleton supertypes were removed and data were split into training and test sets (80/20). Spatial coordinates (x, y, z) were used as input features. For SNR, projection features (axon terminal counts and total axonal length across 29 regions) were standardised, and data were also split into training and test sets (80/20).
- Projection clustering (SNR): K-means clustering was applied to define broader projection groups based on axonal features. The optimal number of clusters was selected using silhouette analysis.
- Models: Logistic Regression, k-Nearest Neighbours, and Random Forest were used to predict either MERFISH supertypes or SNR projection clusters from spatial coordinates.
- Cross-dataset analysis: A model trained on SNR projection clusters was applied to MERFISH spatial coordinates to infer projection patterns across transcriptomic cell types.
- Evaluation metrics: Balanced Accuracy, Macro F1-score, and Top-5 Accuracy (MERFISH) were used due to class imbalance. Recall was additionally reported for SNR classification.
- SHAP and permutation importance



## Data Availability
The dataset is not included in this repository due to access and reuse restrictions.


## Repository Structure
- `report/`: final report (LaTeX source files and figures)
- `code/`: analysis models
- `data/`: raw data (not included in repo)