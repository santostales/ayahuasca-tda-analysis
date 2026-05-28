# Expected private data structure

No private data are distributed with this repository.

## Connectivity matrices

Place paired before/after connectivity matrices in:

```text
data_private/connectivity_matrices/
```

Expected naming pattern:

```text
suj1_before_mat_corr_wcoef_corP05.txt
suj1_after_mat_corr_wcoef_corP05.txt
...
suj9_before_mat_corr_wcoef_corP05.txt
suj9_after_mat_corr_wcoef_corP05.txt
```

Each matrix used in the article workspace had shape `104 x 104`.

## MAT time-series files

Place paired ROI time-series `.mat` files in:

```text
data_private/Aya_temporal_series/
  before/
    s_1_serie_temporal_filtrada/
    ...
  after/
    s_1_serie_temporal_filtrada/
    ...
```

The article workspace contained 9 paired subjects and 104 ROI files per condition after exclusions.

## Control data

The control-group notebook expects a local HCP/control folder with this Windows-style organization:

```text
D:\temp_doc\HCPYoungAdult\
  <subject_id>\
    rfMRI_REST1\
      Schaefer2018_100Parcels_7Networks_Tian_Subcortex_S1_3T\
        *.txt
    rfMRI_REST2\
      Schaefer2018_100Parcels_7Networks_Tian_Subcortex_S1_3T\
        *.txt
```

Edit `HCP_ROOT_DIR` in `04_control_group_persistent_entropy.ipynb` if the private control data are stored elsewhere.
