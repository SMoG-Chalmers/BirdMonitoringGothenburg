# Background

This repository references the data and code products of an urban bird monitoring study conducted by SMoG in Gothenburg, Sweden, during Spring 2024. The study aimed to monitor avian diversity in dense and compact urban areas using passive audio recordings and machine learning techniques.

## About the Dataset 

The dataste prodcued in this study is a machine learning-generated and expert-validated bird occurrence dataset, based on 10,691 hours of passive audio recordings systematically collected across different types of dense and compact urban areas in Gothenburg, Sweden. The dataset includes **239,570 occurrence records** of **61 species** from April 21 to June 16, 2024, across 30 sites in central Gothenburg.

### Download 

The dataset is available for download at https://zenodo.org/records/15350316.

### Documentation

A detailed documentation of the dataset, including URI identifiers, definitions, and examples for all attributes (column headers), is available at https://smog-chalmers.github.io/BirdMonitoringGothenburg/. 

### Data Filtering

Depending on the use case, users may want to filter the dataset based on the [occurrenceProbability](https://smog-chalmers.github.io/BirdMonitoringGothenburg/#occurrenceProbability) attribute using the following recommended thresholds (see the paper for more details) to:

- **Balance sensitivity and specificity** (an optimal threshold determined based on [Youden's J statistic](https://acsjournals.onlinelibrary.wiley.com/doi/10.1002/1097-0142(1950)3:1%3C32::AID-CNCR2820030106%3E3.0.CO;2-3)):

    ```r
    occurrence %>% filter(occurrenceProbability >= 0.74)
    ```
    
-  **Maximize specificity** (a stricter threshold that minimizes false positives):

    ```r
    occurrence %>% filter(occurrenceProbability >= 0.82)
    ```

### Citation

This dataset is part of the manuscript "A bird species occurrence dataset from passive audio recordings across dense urban areas in Gothenburg, Sweden", which is currently under peer review. If you use this dataset in your work, please cite it as follows:

```bibtex
@misc{eldesoky2025birdspecies,
  author = {Eldesoky, A. H. and Gil, J. and Kindvall, O. and Stavroulaki, I. and Jonasson, L. and Bennet, D. and Yang, W. and Martínez, A. and Lichter, R. and Petrou, F. and Berghauser Pont, M.},
  title = {A bird species occurrence dataset from passive audio recordings across dense urban areas in Gothenburg, Sweden},
  year = {2025},
  note = {Data set},
  publisher = {Zenodo},
  doi = {10.5281/zenodo.15350316},
  url = {https://doi.org/10.5281/zenodo.15350316}
}
```

## Scripts

The R scripts used to produce this dataset are available at https://github.com/ahmaeldesoky/bird-species-detection-gothenburg-2024.

# Funding

This study is part of the project "[Twin2Expand](https://twin2expand.surf.com.cy/): Twinning towards research excellence in evidence-based planning and urban design," which has received funding from the European Union’s Horizon Europe Research and Innovation Programme under Grant Agreement No. 101078890, as well as from UK Research and Innovation (UKRI) under the UK government’s Horizon Europe funding guarantee (grant numbers 10052856 and 10050784).

![Funding](funding.png)

# Partners

The Twin2Expand is in collaboration with the University of Cyprus, University College London (UCL), Chalmers University of Technology and the Polytechnic University of Turin

![Partners](partners.png)

