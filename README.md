# Code repository for topological and entropy analyses

This repository contains the public, notebook-only version of the analyses used in the article. The notebooks were organized for scientific inspection and reproducibility while preserving the computational structure of the original analysis notebooks.

## Important data note

The source data are not included in this repository.

- Connectivity matrices (`.txt`) are restricted/private and must not be committed.
- ROI time-series files (`.mat`) are restricted/private and must not be committed.
- Generated result tables and figures are ignored by default.

The notebooks include configuration cells where local paths can be adjusted. The analyses were performed on Windows 11. Users on other systems may need to adapt local paths and environment setup.

## Notebooks

Run the notebooks in numerical order when reproducing the full analysis locally:

1. `01_petri_scaffold_analysis.ipynb`  
   Petri scaffold and persistent H1 analyses from paired connectivity matrices.

2. `02_persistent_entropy_abs_correlation.ipynb`  
   Persistent entropy using `1 - abs(correlation)` as the distance matrix.

3. `03_persistent_entropy_signed_correlation.ipynb`  
   Persistent entropy using `1 - correlation` as the distance matrix.

4. `04_control_group_persistent_entropy.ipynb`  
   Control-group persistent entropy workflow. The original exploratory notebook did not store the random seed or selected control subjects; this public version fixes `CONTROL_RANDOM_SEED = 42` and prints selected subject IDs.

5. `05_lzc_ben_sample_entropy.ipynb`  
   Lempel-Ziv complexity and BEN/Sample Entropy analysis from paired `.mat` ROI time-series files.

## Private data layout

For local reproduction, create the following ignored folders:

```text
data_private/
  connectivity_matrices/
    suj1_before_mat_corr_wcoef_corP05.txt
    suj1_after_mat_corr_wcoef_corP05.txt
    ...
  Aya_temporal_series/
    before/
      s_1_serie_temporal_filtrada/
        timeCourse_roi_filtered_modwt_d4_1.mat
        ...
    after/
      s_1_serie_temporal_filtrada/
        timeCourse_roi_filtered_modwt_d4_1.mat
        ...
```

The preparation workspace used a local fallback to the parent folder for private data. In a clean public clone, place private data under `data_private` or edit the first configuration cell in each notebook.

## Environment

Install the dependencies listed in `requirements.txt`. The original work was performed in a Windows 11 Python environment.

## Reproducibility notes

The notebooks intentionally preserve methodological choices from the original analyses, including distance definitions, topological libraries, statistical tests, thresholds and bootstrap settings. Only the public-facing organization, path configuration, output cleaning and control-group random seed handling were changed.

Because the raw `.txt` and `.mat` files are not public, third parties can inspect and rerun the code only if they have access to equivalent private data in the expected format.
