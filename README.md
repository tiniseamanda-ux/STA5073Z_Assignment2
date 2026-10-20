# Handwriting Analysis Using CNNs and Siamese Neural Networks

## STA5073Z — Neural Network 

This project explores simulated handwritten digit images to investigate writer identification and writer verification using deep learning. The project combines exploratory data analysis, convolutional neural networks (CNNs), Siamese neural networks, model evaluation, and limited hyperparameter optimization.

The project was completed in R using Quarto and neural network tools. The repository contains the project brief, simulated dataset, source code, rendered reports, and supporting project files.

## Project Overview

The dataset contains **25,000 simulated handwritten digit images** from 20 people. Each person contributed 1,250 images across five independent recording sessions.

The images represent digits 0–4, with 50 samples of each digit collected per person per session.

**Important:** The images are simulated for educational purposes and do not represent real handwriting or real individuals. Findings should therefore be interpreted within the limitations of the simulated dataset.

## Objectives

The project addresses the six assignment tasks:

1. **Exploratory data analysis:** Explore the images and metadata, display examples across writers, digits, and sessions, and discuss visible variation and limitations.
2. **CNN writer identification:** Build a CNN to predict writer ID, evaluate overall performance, and compare identification accuracy across digits.
3. **Siamese network writer verification:** Build a Siamese network to estimate whether two images were written by the same person, using a pair-based learning approach and contrastive loss.
4. **Data partitioning and generalization:** Justify the training, validation, and test strategy and discuss generalization, potential data leakage, and optimistic evaluation.
5. **Hyperparameter optimization:** Conduct a limited hyperparameter search and assess how model performance changes with the selected settings.
6. **Model comparison:** Compare CNN and Siamese results, investigate which digits provide more information about writer identity, and discuss the effect of recording-session variation.

All six tasks and their analyses are included in the main project report.

## Dataset

**File:** `handwriting.rds`

The dataset contains 25,000 simulated grayscale images, each measuring 28 × 28 pixels, and associated metadata.

| Dataset characteristic | Description |
|---|---|
| Number of images | 25,000 |
| Number of writers | 20 |
| Digits | 0, 1, 2, 3, 4 |
| Recording sessions per writer | 5 |
| Samples per digit per session | 50 |
| Samples per writer | 1,250 |
| Image dimensions | 28 × 28 pixels |
| Data type | Simulated, not real handwriting |

The metadata identifies the image, writer, digit, session, and replicate. These variables support exploratory analysis, data partitioning, writer classification, and pair construction for verification.

## Models and Analysis

### 1. Exploratory Data Analysis

The exploratory analysis examines handwriting-image examples and variation across writers, digits, and recording sessions. It also considers within-session variation and the limitations of using simulated images.

### 2. Convolutional Neural Network

The CNN treats writer identification as a multiclass classification problem. Given a digit image, the model predicts which of the 20 simulated writers produced it.

Evaluation includes overall identification performance and comparisons by digit. The report discusses what the metrics mean for writer identification and how performance may change when the model encounters a different recording session.

### 3. Siamese Neural Network

The Siamese network learns to compare two images and estimate whether they belong to the same writer. Training examples are constructed as pairs of images with same-writer or different-writer labels.

The model uses contrastive learning to learn an embedding space in which images from the same writer can be brought closer together and images from different writers can be separated.

Evaluation considers matching performance and the effect of the chosen decision threshold.

### 4. Hyperparameter Optimization

A limited hyperparameter search investigates how selected model settings affect validation performance. The report presents the results and explains the trade-offs involved in selecting model configurations.

### 5. Generalization and Model Comparison

The report discusses the rationale for the data splits, including the role of recording sessions and writer-level separation where applicable. It compares CNN classification with Siamese verification and considers possible sources of optimistic performance and data leakage.

## Repository Structure

The repository includes the following files and materials. Exact filenames may vary as the project develops.

| File or folder | Purpose |
|---|---|
| `STA5073Z_Assignment2_Report.qmd` | Quarto source for the main project report |
| `STA5073Z_Assignment2_Report.html` | Rendered HTML version of the main report |
| `handwriting.rds` | Simulated handwriting images and metadata |
| `STA5073Z_Assignment2.Rproj` | RStudio project file |
| `index.html` | Website entry page |
| Assignment brief PDF | Original assignment instructions |
| Additional `.qmd` files | Source documents for exploratory analysis and model development |
| Additional `.R` files | R scripts used for analysis and model development, where applicable |
| Rendered HTML reports | HTML outputs generated from Quarto source documents |
| Supporting figures and files | Visualizations, intermediate outputs, and other project materials |

The repository has four main branches:

- **`main`** — the consolidated project containing the main report and assignment materials.
- **`data-exploration`** — work related to exploratory data analysis and dataset inspection.
- **`cnn-analysis`** — work related to CNN development, evaluation, and tuning.
- **`siamese-analysis`** — work related to Siamese network development, pair construction, evaluation, and tuning.

The `main` branch serves as the primary location for the consolidated project and final report. The other branches preserve the separate areas of development.

## Reproducibility

The `.qmd` source files contain the report narrative, analysis, and code chunks used to produce the rendered reports. The `.Rproj` file supports opening the project in RStudio.

To reproduce the analysis:

1. Clone or download the repository.
2. Open the `.Rproj` file in RStudio.
3. Install the required R packages and configure the required neural network backend.
4. Confirm that `handwriting.rds` and any referenced supporting files are available at the expected paths.
5. Open the relevant `.qmd` file.
6. Render the document using Quarto in RStudio or the Quarto command-line interface.

Exact package versions, Python dependencies, and system requirements may affect reproducibility. Consult the source files and any package setup instructions before running the models.


## Limitations

- The dataset is simulated and may not capture the full complexity of real handwriting.
- Only five digits are represented.
- The number of writers is limited to 20.
- Performance depends on the data-partitioning strategy, training procedure, hyperparameters, and evaluation threshold.
- Results from simulated images cannot be assumed to generalize directly to real-world writer identification or verification.
- Model performance should be interpreted alongside the risk of data leakage and the type of generalization assessed by the chosen evaluation strategy.

## Conclusion

This project investigates two complementary approaches to handwriting analysis: CNN-based writer identification and Siamese-network-based writer verification. By combining exploratory analysis, model development, evaluation, hyperparameter optimization, and critical discussion, the project demonstrates how neural networks can learn writer-related patterns from images while highlighting the importance of careful data partitioning and appropriate interpretation of results.

The findings apply to the simulated assignment dataset and should not be treated as evidence of real-world biometric performance.

