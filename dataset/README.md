# Data and runtime prerequisites

The published notebooks preserve the current executed source and outputs exactly. Viewing their saved results requires no dataset download. Executing their code requires the original runtime inputs; this package is not a standalone data-and-model archive.

## Official source

- [Eedi / NeurIPS Education Challenge project](https://www.eedischool.com/projects/neurips-education-challenge)
- [Official data archive](https://dqanonymousdata.blob.core.windows.net/neurips-public/data.zip)

Consult the original provider for the applicable access and reuse terms. This publication update does not newly redistribute learner-level records.

## Runtime dependencies of the unchanged source

| Input or artifact | Original path | Included here? |
|---|---|---|
| Official extracted CSVs | `Data/Raw/Extracted/data/` | No |
| Historical modeling cohort | `Data/Unified/modeling_dataset.parquet` | No |
| Event, feature, split and prediction Parquets | `Data/` | No |
| Fitted model objects | `Models/` | No |
| Historical source notebooks and helper provenance | `Data/legacy/` | No |
| Complete runtime provenance | `Tables/manifests/` | Six selected descriptive manifests only |
| Original technical protocol plan | External local path retained in Notebook 02 | No |
| Selected aggregate results and figures | `artifacts/`, `figures/` | Yes |
| Current notebook source and saved outputs | `notebooks/` | Yes, unchanged |

The word “download” in the first notebook's filename is historical: it must not be interpreted as a verified automatic fresh-clone download workflow. Merely downloading the official archive does not reconstruct every missing frozen object, historical file or cross-stage artifact.

The supplied `Data → dataset` and `Tables → artifacts` aliases preserve original path conventions. Case-sensitive systems also require `Notebooks → notebooks`, `Figures → figures` and `Models → models` aliases. Dependencies must still be provisioned and verified before any execution.

[notebook_snapshot.json](notebook_snapshot.json) records SHA-256 checksums and source-relative paths of the 44 copied scientific files. It verifies snapshot identity, not complete runtime reproducibility. No experiments were rerun during synchronization.
