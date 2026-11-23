# Student Performance — Train-Test Split with Scikit-learn

## Overview

This project is a practical machine learning exercise focused on preparing a student performance dataset and splitting it into training and testing sets using **Pandas** and **Scikit-learn**.

The dataset contains student information, academic habits, career aspirations, and subject scores. The objective is to understand how to separate input features from a target variable and prepare data for supervised machine learning.

## Learning Objectives

- Understand features (`X`) and target (`y`).
- Load and explore a dataset using Pandas.
- Identify relevant input features.
- Separate features from the target variable.
- Understand training and testing datasets.
- Use Scikit-learn's `train_test_split()`.
- Understand `test_size` and `random_state`.
- Inspect dataset dimensions using `.shape`.

## Dataset

The dataset contains the following columns:

| Column | Description |
|---|---|
| `id` | Unique student identifier |
| `first_name` | Student's first name |
| `last_name` | Student's last name |
| `email` | Student's email address |
| `gender` | Student's gender |
| `part_time_job` | Whether the student has a part-time job |
| `absence_days` | Number of days absent |
| `extracurricular_activities` | Whether the student participates in extracurricular activities |
| `weekly_self_study_hours` | Weekly independent study hours |
| `career_aspiration` | Student's career aspiration |
| `math_score` | Mathematics score |
| `history_score` | History score |
| `physics_score` | Physics score |
| `chemistry_score` | Chemistry score |
| `biology_score` | Biology score |
| `english_score` | English score |
| `geography_score` | Geography score |

## Feature Selection

For this exercise, the target variable is:

**Target (`y`):** `math_score`

The input features (`X`) include:

- `gender`
- `part_time_job`
- `absence_days`
- `extracurricular_activities`
- `weekly_self_study_hours`
- `career_aspiration`
- `history_score`
- `physics_score`
- `chemistry_score`
- `biology_score`
- `english_score`
- `geography_score`

The following columns are excluded:

- `id`: Identifier, not a meaningful predictive feature.
- `first_name`: Personal information.
- `last_name`: Personal information.
- `email`: Personal information.

Categorical features such as `gender`, `part_time_job`, `extracurricular_activities`, and `career_aspiration` will require preprocessing before they can be used by most Scikit-learn estimators.

## Train-Test Split

The dataset is divided into two subsets:

| Dataset | Percentage | Purpose |
|---|---:|---|
| Training set | 80% | Used to train the machine learning model |
| Testing set | 20% | Used to evaluate the model on unseen examples |

Scikit-learn's `train_test_split()` is used with:

- `test_size=0.2`
- `random_state=42`

## Expected Workflow

1. Load the student performance dataset.
2. Explore the dataset.
3. Select the input features (`X`).
4. Select the target variable (`y`).
5. Split the dataset into training and testing sets.
6. Print and inspect the shapes of the resulting datasets.

## Expected Output

The dataset contains 17 input features and one target variable.

Assuming the dataset contains 2,000 records:

| Variable | Expected Shape |
|---|---|
| `X_train` | `(1600, 12)` |
| `X_test` | `(400, 12)` |
| `y_train` | `(1600,)` |
| `y_test` | `(400,)` |

*Note: The actual shapes depend on the dataset's total number of records and the selected features. The feature list above contains 12 input columns.*

## Technologies

- Python
- Pandas
- Scikit-learn

## Installation

Install the required libraries:

```bash
pip install pandas scikit-learn
```

## How to Run

```bash
python main.py
```

## Key Concepts

**Features (`X`):** Input variables used by a machine learning model to make predictions.

**Target (`y`):** The variable the model is trained to predict.

**Training data:** The subset used by the model to learn patterns.

**Testing data:** The subset used to evaluate how well the model performs on unseen examples.

**Data splitting:** Dividing a dataset into separate subsets for training and evaluation.

**Reproducibility:** Using `random_state` to obtain the same random split when running the code again with the same data and settings.

