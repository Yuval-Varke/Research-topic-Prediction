# Research Topic Prediction

This project predicts multiple research topic labels from paper metadata and abstract text. The core work lives in [Research-topic-Prediction.ipynb](Research-topic-Prediction.ipynb), which builds a text classification pipeline over the provided training and test CSV files.

## Project Files

- [Research-topic-Prediction.ipynb](Research-topic-Prediction.ipynb) - notebook with data preparation, feature extraction, model training, and submission generation
- [train.csv](train.csv) - labeled training data with `TITLE`, `ABSTRACT`, and topic columns
- [test.csv](test.csv) - unlabeled test data with `TITLE` and `ABSTRACT`
- [submission6.csv](submission6.csv) - sample submission format
- `final_result.csv` - model predictions written by the notebook

## Approach

The notebook uses a text-processing and multi-label classification pipeline:

1. Clean and combine title and abstract text.
2. Build bag-of-words features with `CountVectorizer` using unigrams and bigrams.
3. Apply TF-IDF transformation.
4. Train a `LinearSVC` model wrapped in `MultiOutputClassifier` to predict the topic columns.

## Data Schema

The training set includes these topic labels:

- `Computer Science`
- `Physics`
- `Mathematics`
- `Statistics`
- `Quantitative Biology`
- `Quantitative Finance`

The test set contains `ID`, `TITLE`, and `ABSTRACT`. Predictions are written in the same label columns as the sample submission.

## Requirements

The notebook relies on common Python data-science packages, including:

- `numpy`
- `pandas`
- `matplotlib`
- `scikit-learn`

## How To Run

1. Open [Research-topic-Prediction.ipynb](Research-topic-Prediction.ipynb).
2. Update the CSV paths in the first cell if needed. The notebook currently uses Colab-style `/content/...` paths, so local runs in this workspace should point to the files in the project folder.
3. Run the notebook from top to bottom.
4. The final prediction file will be saved as `final_result.csv`.

## Output

The generated submission contains one row per test example and binary predictions for all six topic labels.