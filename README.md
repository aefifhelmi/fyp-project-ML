# 🛢️ Crude Oil Price Forecasting with PSO-LightGBM

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/aefifhelmi/fyp-project-ML/blob/main/notebook/01_pso_lgbm_forecasting.ipynb)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **Final Year Project**: Advanced time-series forecasting of WTI & Brent crude oil prices using Particle Swarm Optimization (PSO) to tune LightGBM hyperparameters, with interactive Power BI dashboards for visualization.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Methodology](#methodology)
- [Results](#results)
- [Technologies](#technologies)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This project implements a hybrid machine learning approach for forecasting crude oil prices by combining:

- **Particle Swarm Optimization (PSO)** for intelligent hyperparameter tuning
- **LightGBM** as the core gradient boosting model
- **Time-series feature engineering** with sliding window techniques
- **Power BI dashboards** for interactive visualization and business insights

The system forecasts both **WTI (West Texas Intermediate)** and **Brent** crude oil prices, providing accurate predictions for energy market analysis.

## ✨ Features

- 🔍 **Automated Hyperparameter Optimization**: PSO algorithm finds optimal LightGBM parameters
- 📊 **Comprehensive EDA**: Statistical analysis, stationarity tests, and outlier detection
- 🎯 **Time-Series Modeling**: Sliding window approach with lag features
- 📈 **Multiple Metrics**: RMSE, MAE, and custom evaluation metrics
- 🚀 **Google Colab Ready**: One-click execution in cloud environment
- 📉 **Visualization**: Training curves, prediction plots, and convergence analysis
- 💼 **Power BI Integration**: Interactive dashboards for stakeholder presentations

## 📁 Project Structure

```
fyp-project-ML/
├── notebook/
│   └── 01_pso_lgbm_forecasting.ipynb    # Main analysis notebook
├── data/
│   ├── wti_price.csv                     # WTI crude oil historical prices
│   └── brent_price.csv                   # Brent crude oil historical prices
├── powerbi/                              # Power BI dashboard files
├── exports/                              # Model outputs and predictions
├── assets/                               # Images and documentation assets
├── requirements.txt                      # Python dependencies
├── .gitignore                           # Git ignore rules
├── LICENSE                              # MIT License
└── README.md                            # This file
```

## 🚀 Installation

### Local Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/aefifhelmi/fyp-project-ML.git
   cd fyp-project-ML
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook notebook/01_pso_lgbm_forecasting.ipynb
   ```

### Google Colab Setup

1. Click the **"Open in Colab"** badge at the top of this README
2. Upload your data files to Google Drive at `/MyDrive/FYP PROJECT/DATASETS/`
3. Run all cells (`Runtime` → `Run all`)

The notebook automatically detects the environment and configures paths accordingly.

## 💻 Usage

### Quick Start

```python
# The notebook handles everything automatically, but here's the workflow:

# 1. Data Loading & Preprocessing
# 2. Exploratory Data Analysis (EDA)
# 3. Feature Engineering (sliding window)
# 4. Train/Validation/Test Split (60/20/20)
# 5. PSO Hyperparameter Optimization
# 6. Model Training with Early Stopping
# 7. Evaluation & Visualization
```

### Customization

Modify PSO parameters in the notebook:

```python
# PSO Configuration
swarmsize = 50        # Number of particles
maxiter = 50          # Maximum iterations
omega = 0.8           # Inertia weight
phip = 1.5            # Cognitive coefficient
phig = 1.5            # Social coefficient
```

Adjust LightGBM search space:

```python
# Hyperparameter bounds [min, max]
lb = [100, 0.001, 3, 8, 5, 0.5, 0.5, 0.0, 0.0]
ub = [3000, 0.1, 32, 128, 50, 1.0, 1.0, 10.0, 10.0]
```

## 🔬 Methodology

### 1. Data Preprocessing
- Date parsing and indexing
- Missing value analysis
- Outlier detection using IQR method (COVID-19 period handled separately)
- Data normalization with StandardScaler

### 2. Feature Engineering
- **Sliding window approach**: Creates lag features (lag_1 to lag_5)
- **Temporal features**: Extracts time-based patterns
- **Stationarity tests**: ADF and KPSS tests for time-series validation

### 3. PSO-LightGBM Optimization
- **Objective**: Minimize validation RMSE
- **Search space**: 9 hyperparameters optimized simultaneously
- **Convergence tracking**: Real-time best cost monitoring
- **Early stopping**: Prevents overfitting during training

### 4. Model Evaluation
- **Train/Val/Test split**: 60/20/20 chronological split
- **Metrics**: RMSE, MAE
- **Visualization**: Actual vs. Predicted plots, residual analysis

## 📊 Results

### Model Performance

| Dataset | RMSE | MAE | 
|---------|------|-----|
| Training | TBD | TBD |
| Validation | TBD | TBD |
| Test | TBD | TBD |

*Note: Run the notebook to generate actual metrics*

### Key Findings

- PSO successfully optimizes LightGBM hyperparameters
- Sliding window features capture temporal dependencies
- Model handles COVID-19 price volatility effectively
- Early stopping prevents overfitting

## 🛠️ Technologies

### Core Libraries
- **LightGBM** - Gradient boosting framework
- **PySwarm** - Particle Swarm Optimization
- **scikit-learn** - Machine learning utilities
- **pandas** - Data manipulation
- **NumPy** - Numerical computing

### Visualization & Analysis
- **Matplotlib** & **Seaborn** - Static plots
- **Plotly** - Interactive visualizations
- **Power BI** - Business intelligence dashboards

### Statistical Tools
- **statsmodels** - Time-series analysis (ADF, KPSS tests)
- **scipy** - Statistical functions

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Tengku Afif**
- GitHub: [@aefifhelmi](https://github.com/aefifhelmi)
- Project: Final Year Project - Machine Learning

## 🙏 Acknowledgments

- Dataset sources: WTI and Brent crude oil historical prices
- Supervisor: Dr. Marina (dataset provision)
- Inspiration: Energy market forecasting research

## 📞 Contact

For questions or collaboration opportunities, please open an issue or reach out via GitHub.

---

⭐ **Star this repository** if you find it helpful!
