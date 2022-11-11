# VDss

This repo presents a large benchmark dataset of the volume of distribution at steady state (VDss)
for 2440 drug and drug-likeness molecules, which were curated from 13 published sources and the
DrugBank database (https://go.drugbank.com/). The full raw data is
[raw_data_all.xlsx](data_cleaning/raw_data_all.xlsx) and the clean dataset
is [VDss_dataset.xlsx](VDss_dataset/VDss_dataset.xlsx).

## Features of VDss

- Largest dataset with volume of distribution at steady state values
  (to our knowledge, as of February 20, 2022);
- Stereochemistry information is incorporated with isomeric SMILES if possible and the
  canonical SMILES is used otherwise;
- An extended dataset with precomputed molecular descriptors is provided;

## Details of VDss Dataset

- [VDss_dataset.xlsx](VDss_dataset/VDss_dataset.xlsx) consists of 2440 molecules with *logVDss*
  values.
- [VDss_3d.sdf](VDss_dataset/VDss_3d.sdf) contains 2420 molecules with explicit hydrogen atoms
  in 3D coordinates. It should be noted that there are 2420 molecules
  [VDss_dataset.xlsx](VDss_dataset/VDss_dataset.xlsx), but `RDKit` cannot set up the MMFF94s
  or UFF force field for 20 molecules.
- [VDss_mordred_descriptors.xlsx](VDss_dataset/VDss_mordred_descriptors.xlsx) contains precomputed
  molecular descriptors with [`mordred`](https://github.com/mordred-descriptor/mordred).

## Computational Models of VDss

We have constructed 5 independent machine learning models for VDss predictions,

- random forests (RF)
- light gradient boosting machine (LightGBM)
- support vector machine (SVM)
- XGBoost
- gaussian process regression (GPR)

## Dependencies

All computations were performed in a Python 3.7 virtual environment created with `Conda` in `CentOS`
version 7.9.2009. The `Conda` environment includes the following packages:

- LightGBM==3.2.1, https://lightgbm.readthedocs.io/
- mordred==1.2.0, https://github.com/mordred-descriptor/mordred/
- numpy==1.19.5, https://numpy.org/
- pandas==1.3.3, https://pandas.pydata.org/
- PubChemPy==1.0.4, https://github.com/mcs07/PubChemPy/
- RDKit==2020.09.1, https://www.rdkit.org/
- scikit-learn==0.24.2, https://scikit-learn.org/
- xgboost==1.4.2, https://xgboost.readthedocs.io/

## Citation

Please use the following citation in any publication using VDss library:

```
@misc{liu2022benchmarking,
    title={A Benchmarking Dataset with 2440 Organic Molecules for Volume Distribution at Steady State},
    author={Wenwen Liu and Cheng Luo and Hecheng Wang and Fanwang Meng},
    year={2022},
    eprint={2211.05661},
    archivePrefix={arXiv},
    primaryClass={q-bio.QM}
```

*VDss © 2022 by Luo Lab is licensed under CC BY-NC 4.0*
