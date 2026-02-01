# Garman-Kohlhagen European Currency Option Pricing

[![Quarto](https://img.shields.io/badge/Made%20with-Quarto-blue.svg)](https://quarto.org/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A comprehensive analysis of the Garman-Kohlhagen model for pricing European currency options, featuring complete mathematical derivations, analytical solutions, and numerical implementations with rigorous validation.

## 🌐 Live Website

Visit the live website: [https://LENGDEVID.github.io/PDE_Garman_Kohlhagen_Currency_Option_Pricing/](https://LENGDEVID.github.io/PDE_Garman_Kohlhagen_Currency_Option_Pricing/)

## 📋 Project Overview

This project bridges theoretical finance with computational methods by:

- **Deriving** the Garman-Kohlhagen PDE from stochastic differential equations
- **Implementing** analytical closed-form solutions
- **Developing** three finite difference numerical schemes (FTCS, BTCS, Crank-Nicolson)
- **Validating** numerical methods through stability and convergence analysis
- **Computing** option Greeks for risk management applications

## 🎯 Key Features

- ✅ Complete mathematical framework from SDE to PDE
- ✅ Analytical Garman-Kohlhagen pricing formulas
- ✅ Three numerical methods with stability analysis
- ✅ Comprehensive convergence studies
- ✅ Greeks computation and delta hedging demonstrations
- ✅ Interactive presentation slides
- ✅ Full Python source code documentation

## 🚀 Quick Start

### Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) (version 1.3+)
- Python 3.8+
- Required Python packages: `numpy`, `scipy`, `matplotlib`, `pandas`

### Installation

1. **Clone the repository**
   ```bash
   git clone git@github.com:LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing.git
   cd PDE_Garman_Kohlhagen_Currency_Option_Pricing
   ```

2. **Install Python dependencies**
   ```bash
   pip install -r Source_Code/requirements.txt
   ```

### Local Development

**Preview the website locally:**
```bash
quarto preview
```

This will start a local server (typically at `http://localhost:4200`) and automatically open your browser.

**Render the entire website:**
```bash
quarto render
```

The rendered website will be in the `_site` directory.

## 📁 Project Structure

```
PDE_Garman_Kohlhagen_Currency_Option_Pricing/
├── _quarto.yml                          # Website configuration
├── index.qmd                            # Homepage
├── styles.css                           # Custom styling
├── Presentation_Slide/
│   ├── presentation.qmd                 # RevealJS slides
│   └── custom.scss                      # Slide styling
├── Source_Code/
│   ├── European_Option_Currency_Pricing.qmd  # Main documentation
│   └── requirements.txt                 # Python dependencies
└── README.md                            # This file
```

## 🌐 GitHub Pages Deployment

### Initial Setup

1. **Render the website:**
   ```bash
   quarto render
   ```

2. **Commit and push to GitHub:**
   ```bash
   git add .
   git commit -m "Initial website build"
   git push origin main
   ```

3. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Navigate to **Settings** → **Pages**
   - Under **Source**, select **Deploy from a branch**
   - Select branch: `main` and folder: `/ (root)`
   - Click **Save**

4. **Wait for deployment** (usually 1-2 minutes)
   - Your site will be available at: `https://LENGDEVID.github.io/PDE_Garman_Kohlhagen_Currency_Option_Pricing/`

### Updating the Website

After making changes:

```bash
quarto render
git add .
git commit -m "Update website content"
git push origin main
```

GitHub Pages will automatically rebuild and deploy your changes.

## 📚 Content Overview

### [Presentation Slides](Presentation_Slide/presentation.qmd)

Interactive RevealJS presentation covering:
- Theoretical framework and PDE derivation
- Analytical solutions
- Numerical methods (FTCS, BTCS, Crank-Nicolson)
- Stability and convergence analysis
- The Greeks and practical applications

### [Source Code Documentation](Source_Code/European_Option_Currency_Pricing.qmd)

Complete Python implementation with:
- Step-by-step mathematical derivations
- Analytical pricing formulas
- Three finite difference solvers
- Comprehensive validation studies
- Rich visualizations and plots

## 👥 Team

- **Leng Devid**
- **Hem Bellyday**
- **Phal Menghak**
- **Lot Soklang**

**Supervisor:** Professor Dr. LUEY Sokea

## 📖 Academic Context

This project was developed as part of advanced coursework in Partial Differential Equations (PDE) and Computational Finance, demonstrating the application of numerical methods to real-world financial derivatives pricing.

## 🛠️ Technical Details

### Numerical Methods Implemented

1. **FTCS (Forward-Time Central-Space)**: Explicit scheme, conditionally stable
2. **BTCS (Backward-Time Central-Space)**: Implicit scheme, unconditionally stable
3. **Crank-Nicolson**: Implicit scheme, second-order accuracy, unconditionally stable

### Validation Techniques

- Von Neumann stability analysis
- Convergence rate studies (spatial and temporal)
- Comparison with analytical solutions
- Greeks computation verification

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Professor Dr. LUEY Sokea for guidance and supervision
- The Quarto team for the excellent documentation framework
- The scientific Python community for robust numerical libraries

## 📧 Contact

For questions or feedback, please open an issue on GitHub or contact the team members.

---

**Made with ❤️ using [Quarto](https://quarto.org/)**
