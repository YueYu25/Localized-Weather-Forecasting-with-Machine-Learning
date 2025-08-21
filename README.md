# Localized Weather Forecasting with Machine Learning

## Overview

This repository contains the implementation and experimental code for the research project **"Localized Weather Forecasting with Machine Learning"**, conducted as part of the Computational and Applied Mathematics (CAM) MSc program at the University of Edinburgh.

### Project Information
- **Author**: Yue Yu
- **Supervisors**: Francesco Tudisco, Harris Abdul Majid
- **Institution**: University of Edinburgh
- **Program**: MSc Computational and Applied Mathematics (CAM)
- **Year**: 2025

## Abstract

This project explores the application of deep learning techniques to localized weather forecasting, investigating how spatial patch-based approaches can improve prediction accuracy and reduce memory requirements compared to global weather models. The research focuses on optimizing patch sizes for local weather prediction and comparing the performance of models with and without pooling layers.

## Repository Structure

The codebase consists of four main Jupyter notebooks, each addressing different aspects of the localized weather forecasting problem:

### `Patch_Extraction.ipynb`
**Purpose**: Optimal patch size determination and validation
- Tests various patch sizes to identify the optimal dimensions for local weather prediction
- Validates the rationality of selected patch sizes using saliency map analysis
- Provides visualization tools for understanding spatial feature importance

### `GPU_Memory_Test.ipynb`
**Purpose**: Computational resource analysis
- Benchmarks peak GPU memory requirements for both local and global weather prediction models
- Measures forward-backward training time requirements
- Provides performance comparisons between different model architectures

### `Local_Weather_Forecasting_with_Pooling_Layer.ipynb`
**Purpose**: Local forecasting with pooling layers
- Implements and evaluates local weather forecasting models incorporating pooling layers
- Presents experimental results and performance metrics
- Analyzes the impact of pooling operations on prediction accuracy

### `Local_Weather_Forecasting_without_Pooling_Layer.ipynb`
**Purpose**: Local forecasting without pooling layers
- Implements local weather forecasting models without pooling layers
- Provides comparative analysis against pooling-based approaches
- Evaluates trade-offs between model complexity and prediction accuracy


## Usage

### Quick Start

1. **Patch Size Optimization**:
   ```bash
   jupyter notebook Patch_Extraction.ipynb
   ```
   Run this notebook first to determine optimal patch sizes for the dataset.

2. **Model Training and Evaluation**:
   - For models with pooling: `Local_Weather_Forecasting_with_Pooling_Layer.ipynb`
   - For models without pooling: `Local_Weather_Forecasting_without_Pooling_Layer.ipynb`

3. **Resource Assessment**:
   ```bash
   jupyter notebook GPU_Memory_Test.ipynb
   ```
   Use this to understand computational requirements before training.

### Data Requirements

The models expect weather data in the following format:
- **Spatial Resolution**: `256 × 512` (latitude × longitude) global regular grid. :contentReference[oaicite:0]{index=0}  
- **Temporal Resolution**: sequences of `1008` time steps sampled every **6 hours**  
  (≈ 252 days per sequence). :contentReference[oaicite:1]{index=1}
- **Variables**: horizontal wind **velocity** with two channels  
  `u` (zonal, x-direction) and `v` (meridional, y-direction). Shape per sequence:
  `(1, 1008, 256, 512, 2)`. :contentReference[oaicite:2]{index=2}
- **Format**: **HDF5**. The commonly used groups/keys are:
  - `boundary_conditions` (e.g., `phi_periodic`, `theta_open`)
  - `dimensions` (`phi`, `theta`, `time`)
  - `t0_fields/height`  *(optional, not required by our models)*
  - `t1_fields/velocity`  *(required; shape `(1, 1008, 256, 512, 2)`)*

## Results

### Key Findings

1. **Optimal Patch Size**: [Summary of optimal patch size findings]
2. **Performance Comparison**: 
   - Models with pooling layers: [Performance metrics]
   - Models without pooling layers: [Performance metrics]
3. **Computational Efficiency**: [Summary of memory and time requirements]

### Performance Metrics

| Model Type | RMSE | MAE | Training Time | Memory Usage |
|------------|------|-----|---------------|--------------|
| With Pooling | [Value] | [Value] | [Value] | [Value] |
| Without Pooling | [Value] | [Value] | [Value] | [Value] |



## Citation

If you use this work in your research, please cite:

```bibtex
@mastersthesis{yu2024localized,
  title={Localized Weather Forecasting with Machine Learning},
  author={Yu, Yue},
  year={2024},
  school={University of Edinburgh},
  type={MSc Thesis},
  program={Computational and Applied Mathematics}
}
```

## License

[Specify license, e.g., MIT, Apache 2.0, etc.]

## Contact

For questions about this research, please contact:
- **Yue Yu**: [email@example.com]
- **Supervisors**: 
  - Francesco Tudisco: [francesco.tudisco@ed.ac.uk]
  - Harris Abdul Majid: [harris.majid@ed.ac.uk]

## Acknowledgments

- University of Edinburgh; School of Mathematics
- CAM MSc Program
- [Any other acknowledgments, funding sources, data providers, etc.]

---

*This project was completed as part of the MSc Computational and Applied Mathematics program at the University of Edinburgh, 2024.*
