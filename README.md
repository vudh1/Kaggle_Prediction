# Kaggle Binary Classification Experiments

A machine-learning experimentation project comparing multiple classifiers on a Kaggle-style binary prediction task.

The repository captures the full workflow: **loading tabular data, splitting training/validation sets, training different model families, comparing validation behavior, producing probabilities, and exporting submission files**.

> **Portfolio note:** this project was built with an older scikit-learn environment. The notebook is preserved as an experiment record, so some APIs may need small updates in a modern Python environment.

## Models explored

The primary notebook experiments with:

- Gradient Boosting
- AdaBoost
- Random Forests
- Multi-Layer Perceptron / neural networks
- Support Vector Machines

Additional legacy experiments in `example.py` include K-Nearest Neighbors, dimensionality reduction, SVMs, and bagged tree classifiers.

## Workflow

```text
training data
     |
     v
train / validation split
     |
     +-----------------------------+
     |        |        |           |
     v        v        v           v
 boosting   forest    MLP         SVM
     |        |        |           |
     +--------+--------+-----------+
              |
              v
      validation comparison
              |
              v
     test-set probabilities
              |
              v
       Kaggle CSV output
```

## Repository guide

| Path | Purpose |
| --- | --- |
| `Project.ipynb` | Main experiment notebook |
| `data/` | Training labels/features and test features |
| `mltools/` | Course-provided/helper ML utilities |
| `submission_*.csv` | Historical prediction outputs from different models |
| `example.py` / `example_1.py` | Earlier/alternate experiments |

## Running the notebook

Create a Python environment and install the scientific stack:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install jupyter numpy pandas matplotlib seaborn scikit-learn
jupyter notebook Project.ipynb
```

On Windows:

```powershell
.venv\Scripts\activate
```

The original notebook uses APIs from an older scikit-learn release. In a current release, some constructor arguments or deprecated modules may need to be updated before every cell runs unchanged.

## What this project demonstrates

- practical model comparison rather than relying on a single algorithm;
- train/validation evaluation;
- probability-based predictions for competition submissions;
- ensemble methods and nonlinear classifiers;
- use of notebooks to record both experiments and outputs.

The value of the project is the experimentation process: testing several model families on the same data and examining how model complexity changes training and validation performance.
