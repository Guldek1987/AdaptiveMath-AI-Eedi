# Data access and execution prerequisites

## What is included

The six notebooks retain their executed source and outputs exactly. This directory provides the official source information, input checksums and a publication snapshot manifest. It does **not** contain raw responses, transformed learner-level tables, row-level predictions or fitted models.

Eedi's [official dataset page](https://www.eedischool.com/projects/neurips-education-challenge) specifies [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/). The provider restricts commercial use and redistribution of modified material, and places additional restrictions on question images. Obtain the source directly from the provider; no question images are needed by these notebooks.

## Five original input files

The working experiment uses these unchanged CSVs from the [official data archive](https://dqanonymousdata.blob.core.windows.net/neurips-public/data.zip):

| Relative path inside the official archive | Role |
|---|---|
| `data/train_data/train_task_1_2.csv` | Answer, learner, question and correctness identifiers |
| `data/metadata/answer_metadata_task_1_2.csv` | Completion timestamps and answer metadata |
| `data/metadata/question_metadata_task_1_2.csv` | Question-to-subject metadata |
| `data/metadata/student_metadata_task_1_2.csv` | Subgroup descriptors |
| `data/metadata/subject_metadata.csv` | Subject hierarchy |

[required_inputs.json](required_inputs.json) records the source-relative paths, bytes and SHA-256 hashes observed in the working experiment. These are checksums, not redistributed records.

Data acquisition occurs **before** Notebook 01, which analyzes already-local inputs. For POSIX systems, after checking the provider's terms:

```bash
mkdir -p dataset/Raw/Extracted
curl --fail --location --retry 3 \
  https://dqanonymousdata.blob.core.windows.net/neurips-public/data.zip \
  --output dataset/official-data.zip
unzip -n dataset/official-data.zip \
  data/train_data/train_task_1_2.csv \
  data/metadata/answer_metadata_task_1_2.csv \
  data/metadata/question_metadata_task_1_2.csv \
  data/metadata/student_metadata_task_1_2.csv \
  data/metadata/subject_metadata.csv \
  -d dataset/Raw/Extracted
```

This prepares only the raw inputs; it is **not** a claim that the complete saved-artifact workflow will then run without further provisioning.

## Runtime dependency boundary

| Stage | Required material | Publication status |
|---|---|---|
| Notebook source and scientific displays | All six `notebooks/*.ipynb` | Included unchanged |
| Dataset analysis and feature generation | Five official CSVs above | Download from provider |
| Primary temporal experiment | Event/features/splits, exact protocol and fitting contracts | Protocol included; row-level caches not redistributed |
| Frozen primary reconstruction | 60 seed/window prediction files and 540 fitted variant objects | Not redistributed |
| Component tuning display | Per-seed/window reconstruction CSVs and tuning Parquets | Saved notebook displays included; full fitting ledger not bundled |
| Supporting GRU/SAKT displays | `Data/matched_information_predictions.parquet`, `Tables/learning_curves.parquet`, candidate registry | Aggregate registry/results included; prediction and curve caches not bundled |
| Paired uncertainty | Saved draws/contracts or a new complete B=5000 calculation | Aggregate intervals and contract included; draws not bundled |
| Historical numerical reproduction check | `Data/Round2/clean_execution/` control outputs and contracts | Local archive only |
| One-time source-layout compatibility check | `Data/Round2/pre_presentation_notebooks/` | Local archive only |
| Current figures | 12 PNG/PDF pairs | Included unchanged |

The source defines actual preprocessing, fitting and evaluation functions inside notebook cells; aggregate CSVs do not replace the implementation. Nevertheless, some **sequential notebook entry cells expect previously generated downstream artifacts**, and the final cell compares against a separate local raw-only control run. Therefore, this release is an **executed-source/results snapshot, not a verified standalone clean-clone training distribution**.

No raw-only reproduction or model retraining was run during this repository update. Reconstructing omitted dependencies is additional work, not a hidden property of the download command. Missing inputs must not be replaced by synthetic data or silently reduced budgets.

## Paths and environment

The original source uses `Notebooks`, `Data`, `Tables`, `Figures` and `Models`.

- `Data → dataset` and `Tables → artifacts` are tracked aliases.
- On a case-sensitive POSIX filesystem, create the three additional aliases shown in the root README.
- Keep the six canonical notebook filenames: the notebook-source loader uses them directly.
- Python 3.11 and the pinned [reference dependencies](../requirements.txt) describe the current working environment.
- Times New Roman must be installed separately for plotting. There is no silent font substitution and the font itself is not distributed.
- GPU availability is not asserted. The supporting neural experiment records its own configuration and stopping conditions.

[notebook_snapshot.json](notebook_snapshot.json) verifies identity of the published scientific files. It is not evidence that omitted runtime objects exist in a fresh clone.
