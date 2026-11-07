# Song Popularity Prediction and Interpretation

**Course:** EAS 5740 / Group Final Project  
**Artifact type:** Course project / coursework

## Overview

A group project combining cleaning, feature engineering, linear regression, decision trees, random forests, and gradient boosting. The notebook includes feature importance, SHAP, and residual analysis. Individual responsibilities remain to be confirmed.

## Guiding question

How well can audio features and metadata predict song popularity?

## Methods and technical scope

Python; pandas; scikit-learn; regression; SHAP.

## Evaluation and analysis

The existing workflow fits supervised SelectKBest before the train/test split. This leaks test-label information. Move feature selection into a training-only pipeline, reserve validation for model selection, and reevaluate before reporting generalization performance.

## Contribution and evidence status

Group project; personal contribution unconfirmed. Existing scores are not validated portfolio benchmarks. Keep solution code private under the course syllabus.

The presence of a local file does not independently establish sole authorship. Course-provided scaffolding, collaborators, third-party resources, and any required AI-assistance disclosures must remain attributed.

## Source artifacts

The following exact filenames identify the local evidence. For browser upload, source files and text-only report transcriptions are stored at the repository root; incomplete templates are identified below. The table below maps each artifact. PDF transcriptions omit figures and may alter table layout; original files remain on the author's computer.

- `574_Group_Final_Project_1_1.ipynb`
- `PresentationFinalProject 1.0.pdf`

## Reproduction status

This portfolio preparation did not rerun training, rebuild the project, call paid model APIs, or verify all dependencies. Exact environment versions, permitted dataset access, and a tested entry point should be added only after the final submission version is identified. This README is not a claim of reproducibility.

## Access and redistribution

Keep assignment solution code and course materials private pending the relevant course rules. Do not redistribute datasets, instructor materials, credentials, student IDs, or collaborator information without an appropriate basis. No third-party licensing rights are implied.


## Packaged artifact map

| Original filename | Repository file |
|---|---|
| `574_Group_Final_Project_1_1.ipynb` | [`574_Group_Final_Project_1_1.ipynb`](<574_Group_Final_Project_1_1.ipynb>) |
| `PresentationFinalProject 1.0.pdf` | [`PresentationFinalProject 1.0.md`](<PresentationFinalProject 1.0.md>) |

Notebook outputs are intentionally cleared. No credentials, datasets, model checkpoints, course syllabi, or exam papers are included. Dependencies and execution instructions remain to be verified against the final submitted versions.
