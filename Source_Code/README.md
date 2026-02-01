# European FX Option Pricing - Streamlit App

A minimal, high-contrast Streamlit application demonstrating the **Garman-Kohlhagen European FX Option Pricing Model**.

## Overview

This app provides an interactive demonstration of:
- Analytical solutions for European currency options
- Numerical methods (FTCS, BTCS, Crank-Nicolson)
- Stability and convergence analysis
- The Greeks and delta-hedging applications
- Comprehensive visualizations

## Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager

### Setup

1. **Navigate to the project directory:**
   ```bash
   cd European_Option_Currency_Pricing
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## Running the App

Start the Streamlit app with:

```bash
streamlit run app.py
```

The app will open in your default web browser at `http://localhost:8501`

## App Features

### 📚 Introduction
- Overview of the Garman-Kohlhagen model
- Mathematical framework and PDE derivation
- Analytical formulas for calls and puts

### 📊 Analytical Solution
- Real-time option pricing (calls and puts)
- Put-Call Parity validation
- The Greeks (Delta, Gamma, Vega, Theta)
- Interactive Greeks visualization

### 🔢 Numerical Methods
- Three finite difference schemes:
  - **FTCS**: Forward-Time Central-Space (Explicit)
  - **BTCS**: Backward-Time Central-Space (Implicit)
  - **Crank-Nicolson**: Second-order implicit scheme
- Comparison with analytical solutions
- Performance benchmarking

### 📈 Stability & Convergence
- Von Neumann stability analysis
- Experimental stability verification
- Convergence rate studies (log-log plots)
- Empirical order of accuracy

### 🎯 Results & Visualization
- 3D option price surfaces
- Contour plots
- Delta-hedging demonstration
- Computational performance summary

## Parameters

Adjust the following parameters in the sidebar:

| Parameter | Symbol | Description | Default |
|-----------|--------|-------------|---------|
| Spot Price | S₀ | Current exchange rate | 100 |
| Strike | K | Option strike price | 100 |
| Domestic Rate | rₐ | Domestic risk-free rate | 0.05 |
| Foreign Rate | rₑ | Foreign risk-free rate | 0.03 |
| Volatility | σ | Exchange rate volatility | 0.20 |
| Time to Maturity | T | Years until expiration | 1.0 |

## Design

The app features a **minimal dark theme** with high-contrast colors:
- Dark background (#0a0a0a)
- Bright accent color (#00ff88)
- Clean, modern interface
- Interactive Plotly visualizations

## Validation

All results have been validated against the original Quarto project:
- Analytical prices match to machine precision
- Numerical methods achieve < 0.1% error
- Greeks accurate to < 1%
- Put-Call Parity holds to 1e-6

## Project Structure

```
European_Option_Currency_Pricing/
├── app.py              # Main Streamlit application
├── requirements.txt    # Python dependencies
└── README.md          # This file
```

## Key Results

- ✓ Crank-Nicolson recommended for production (best accuracy/cost)
- ✓ Convergence rates confirmed: O(Δt²) for CN, O(Δt) for FTCS/BTCS
- ✓ Delta-hedging reduces risk by ~90%
- ✓ All stability properties verified experimentally

## Author

**LENG DEVID**

Based on the comprehensive Garman-Kohlhagen European FX Option Pricing analysis.

## License

Educational and demonstration purposes.
