# OASIS-1 MRI Data Preprocessing

## Summary

The OASIS-1 dataset is a cross-sectional collection of MRI scans of young, middle-aged, nondemented, and demented older adults. The dataset consists of 416 subjects, each with 3 or 4 individual T1-weighted MRI scans. This notebook outlines the process of preprocessing the OASIS-1 dataset, including loading images, extracting labels, selecting representative images, converting formats, performing skull stripping, and saving the results.

## Current Workflow

1. **Load .npy Images:** Import .npy images from the OASIS-1 dataset provided by Ninad Aithal on Kaggle. This dataset contains images for 347 subjects.

2. **Extract Labels:** Extract the corresponding CDR (Clinical Dementia Rating) label for each MRI ID.

3. **Select Representative Images:** Select one MRI image for each unique MRI ID to reduce redundancy in the dataset.

4. **Convert Formats:** Convert the selected MRI images from .npy format to .nii.gz format for compatibility with neuroimaging software.

5. **Perform Skull Stripping:** Apply skull stripping to remove non-brain tissue from the converted MRI images using a pre-trained deep learning model based on the Neural Pre-Processing paper ([link](https://doi.org/10.48550/arXiv.2303.12148)).

6. **Save Data:** Save the processed and skull-stripped MRI images in the desired format (e.g., NIfTI).

## Note

- There are 201 rows in the cross-sectional dataset that have missing values for the CDR column. These rows will be excluded from the processing pipeline.

## References

- OASIS-1 dataset: [link](https://www.oasis-brains.org/)
- Ninad Aithal's dataset on Kaggle: [link](https://www.kaggle.com/datasets/ninadaithal/oasis-mri-dataset-npy)
- Neural Pre-Processing paper: [link](https://doi.org/10.48550/arXiv.2303.12148)
