# TS_Predictor V1.0

# TS_Predictor: A Deep Learning Toolbox for GNSS Time Series Prediction with Signal Decomposition and Nonlinear Modelling**

# For software usage issues
Please contact：6720230184@mail.jxust.edu.cn (Yu Zhou) and 2452481248@qq.com (Jun Li).

## How to cite

If you find the TS_Predictor program is useful, please cite it in your work as:

[1] TS_Predictor: A Deep Learning Toolbox for GNSS Time Series Prediction with Signal Decomposition and Nonlinear Modelling. (Appear soon, see https://authors.elsevier.com/tracking/article/details.do?aid=19477&jid=JASR&surname=He)

[2]Zhang, S., Li, J., Zhao, L., Zeng, A., Ming, F., Liu, N., Chen, X., Feng, Z. and Wang, H., 2025. gCMEbox: A MATLAB toolbox for extracting and analyzing common-mode errors from GNSS time series. Advances in Space Research, 75(1), pp.497-514.  

[3] Zhou, Y., He, X., Montillet, J.P., Wang, S., Hu, S., Sun, X., Huang, J. and Ma, X., 2025. An improved ICEEMDAN-MPA-GRU model for GNSS height time series prediction with weighted quality evaluation index. Gps Solutions, 29(3), p.113.  

## Overview

TS_Predictor is an open-source MATLAB toolbox for predicting Global Navigation Satellite System (GNSS) coordinate time series. It integrates signal decomposition methods with machine learning and deep learning models, providing a complete workflow from raw data preprocessing to prediction accuracy assessment.


## Key Features

- **Data Import**: Supports multiple formats from NGL, PBO, and CEA data centers
- **Preprocessing**: Missing data interpolation, outlier detection, offset correction, CME removal
- **Signal Decomposition**: EMD, EEMD, CEEMD, CEEMDAN, ICEEMDAN, VMD
- **Prediction Models**: SVM, RBF, ELM, BP, LSTM, GRU
- **Accuracy Evaluation**: RMSE, MAE, sMAPE, R², and unified WQE index
- **Visualization**: Interactive plots and exportable results

## Installation

### Requirements

- MATLAB 2024b or later
- Deep Learning Toolbox
- Signal Processing Toolbox
- Statistics and Machine Learning Toolbox

### Steps

1. Download or clone this repository:
   ```bash
   git clone https://github.com/SpaceGeodesyLab/TS_Predictor.git
   ```

2. Open MATLAB and navigate to the TS_Predictor directory

3. Right-click on `TS_predictor.mlappinstall` and select **Install**

4. After installation, TS_Predictor will appear in the **Apps** toolbar

5. Click the TS_Predictor icon to launch the program

## Quick Start

### 1. Load Data

TS_Predictor accepts GNSS time series from:
- Nevada Geodetic Laboratory (NGL): `.txt` format
- Plate Boundary Observatory (PBO): `.csv` and `.pos` formats  
- China Earthquake Administration (CEA): `.txt` format

Use the **Data Conversion** module to convert your data to the unified CSV format.

### 2. Preprocess

The preprocessing module (based on gCMEbox) provides:
- **Interpolation**: Kriging-Kalman filtering for missing data
- **Outlier detection**: IQR and MAD methods
- **Offset correction**: Weighted least-squares fitting
- **CME removal**: PCA, ICA, FastICA, vbICA

### 3. Decompose

Select a decomposition method to separate your time series into components:

| Method | Description | Best for |
|--------|-------------|----------|
| EMD | Empirical Mode Decomposition | Basic separation |
| EEMD | Ensemble EMD | Reducing mode mixing |
| CEEMDAN | Complete Ensemble EMD with Adaptive Noise | Cleaner separation |
| ICEEMDAN | Improved CEEMDAN | Best overall performance |
| VMD | Variational Mode Decomposition | Known number of modes |

### 4. Predict

Choose a prediction model:

| Model | Type | Characteristics |
|-------|------|-----------------|
| SVM | Machine Learning | Good for small datasets |
| RBF | Machine Learning | Fast training |
| ELM | Machine Learning | Very fast, less accurate |
| BP | Neural Network | Classic approach |
| LSTM | Deep Learning | Best for long sequences |
| GRU | Deep Learning | Good balance of speed/accuracy |

**Recommended**: ICEEMDAN + GRU for most GNSS applications.

### 5. Evaluate

Compare models using multiple metrics:
- **RMSE**: Root Mean Square Error
- **MAE**: Mean Absolute Error
- **sMAPE**: Symmetric Mean Absolute Percentage Error
- **R²**: Coefficient of determination
- **WQE**: Weighted Quality Evaluation (unified metric)

Results are exported to Excel for further analysis.

## Example

Test data from 10 GNSS stations in Yunnan, China (2010-2025) is provided in the `Test data` folder.

```matlab
% Example workflow
% 1. Launch TS_Predictor from Apps toolbar
% 2. Load test data from 'Test data/YNTC.csv'
% 3. Apply preprocessing (interpolation, outlier removal)
% 4. Decompose using ICEEMDAN (default parameters)
% 5. Predict using GRU model
% 6. Evaluate and export results
```

## Project Structure

```
TS_Predictor/
├── main/                    # Core application files
├── gCMEbox_v5/             # Preprocessing toolbox
├── Test data/              # Example GNSS time series
├── TS_predictor.mlappinstall   # Installation package
├── LICENSE                 # MIT License
└── README.md              # This file
```


## Related Software

- [gCMEbox](https://github.com/SpaceGeodesyLab/gCMEbox) - GNSS Common Mode Error extraction toolbox
- [Hector](http://segal.ubi.pt/hector/) - GNSS time series noise analysis
- [TSAnalyzer](https://github.com/yxw027/TSAnalyzer) - GNSS time series analysis

## Authors

- **Xiaoxing He** - Jiangxi University of Science and Technology - xxh@jxust.edu.cn
- **Yu Zhou** - Jiangxi University of Science and Technology
- **Jun Li** - Chang'an University
- **Gaël Kermarrec** - Leibniz University Hannover
- **Rui Fernandes** - University of Beira Interior
- **Jean-Philippe Montillet** - University of Beira Interior

## Acknowledgments

This work was supported by:
- National Natural Science Foundation China (42364002, 42474028)
- Natural Science Foundation of Jiangxi (20252BAC220015, 20252BAC200264)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## Support

- **Issues**: [GitHub Issues](https://github.com/SpaceGeodesyLab/TS_Predictor/issues)
- **Email**: xxh@jxust.edu.cn

---

**SpaceGeodesyLab** | Jiangxi University of Science and Technology
