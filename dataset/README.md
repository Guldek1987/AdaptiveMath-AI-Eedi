# Eedi dataset access

The raw Eedi / NeurIPS 2020 Education Challenge data are intentionally not mirrored in this repository. This keeps access tied to the official source and its licensing conditions and avoids redistributing learner-level or transformed records.

Notebook [`01_dataset_acquisition_and_research_design.ipynb`](../notebooks/01_dataset_acquisition_and_research_design.ipynb) downloads and validates the official archives from:

- Project page: <https://www.eedischool.com/projects/neurips-education-challenge>
- Data archive: <https://dqanonymousdata.blob.core.windows.net/neurips-public/data.zip>
- Starter kit: <https://dqanonymousdata.blob.core.windows.net/neurips-public/starter_kit.zip>

The official project page identifies the dataset license as **CC BY-NC-ND 4.0**. Use the data for non-commercial research only, retain attribution, review the current terms on the official page, and do not redistribute question images.

During execution, the notebooks create the following ignored runtime directories:

```text
dataset/
├── raw/
│   ├── archives/
│   └── extracted/
└── processed/
```

Run Notebooks 01 and 02 before any model notebook. No local data file is required before the first run.

Recommended dataset citation:

> Wang, Z., Lamb, A., Saveliev, E., et al. (2021). Results and Insights from Diagnostic Questions: The NeurIPS 2020 Education Challenge. *Proceedings of Machine Learning Research*, 133, 191–205. <https://proceedings.mlr.press/v133/wang21a.html>
