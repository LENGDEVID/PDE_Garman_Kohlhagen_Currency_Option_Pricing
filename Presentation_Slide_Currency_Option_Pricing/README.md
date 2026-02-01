# Garman-Kohlhagen FX Option Pricing - Presentation

## Overview

This professional Quarto presentation provides a comprehensive overview of the Garman-Kohlhagen European FX Option Pricing project, covering theory, implementation, numerical methods, and validation.

## Features

- **Clean Professional Design**: Minimalist color scheme following professional presentation standards
- **Scrollable Slides**: Extended content areas with smooth scrolling
- **Interactive Elements**: Code folding, tabsets, and incremental reveals
- **Comprehensive Visualizations**: Matplotlib plots with consistent styling
- **Mathematical Typesetting**: Beautiful LaTeX equations
- **Responsive Layout**: Works on different screen sizes

## Structure

### Part I: Theory & Foundations
- Motivation & market context
- Mathematical framework
- SDE to PDE derivation
- Garman-Kohlhagen equation

### Part II: Analytical Solution
- Closed-form formulas
- Implementation & validation
- Option price behavior

### Part III: The Greeks
- Analytical formulas for all Greeks
- Visualizations
- Delta hedging application

### Part IV: Numerical Methods
- Finite difference discretization
- FTCS, BTCS, Crank-Nicolson schemes
- Implementation examples

### Part V: Stability Analysis
- Von Neumann analysis
- Stability demonstrations
- CFL condition

### Part VI: Convergence Analysis
- Theoretical convergence rates
- Empirical verification
- Accuracy vs computational cost

### Part VII: Results & Visualization
- 3D option price surfaces
- Time evolution plots
- Numerical vs analytical comparison

### Part VIII: Performance & Recommendations
- Method comparison
- Practical recommendations
- Computational performance

### Part IX: Conclusions
- Summary of achievements
- Key findings
- Limitations & future work

## How to Render

### Prerequisites
```bash
pip install jupyter numpy scipy matplotlib pandas
```

Install Quarto from: https://quarto.org/docs/get-started/

### Rendering Options

1. **HTML Presentation** (RevealJS):
```bash
quarto render presentation.qmd
```

2. **PDF Export** (via browser):
   - Open the HTML presentation
   - Press 'E' to enter PDF export mode
   - Print to PDF using browser

3. **Preview Mode**:
```bash
quarto preview presentation.qmd
```

## Keyboard Shortcuts

- **Arrow Keys**: Navigate slides
- **F**: Fullscreen mode
- **S**: Speaker notes view
- **O**: Overview mode
- **B**: Blackout screen
- **E**: PDF export mode
- **?**: Help menu

## Color Palette

- **Primary Blue**: `#2c5f8d` - Headers, emphasis
- **Dark Blue**: `#1e3a5f` - Section backgrounds
- **Accent Green**: `#2ecc71` - Success, tips
- **Accent Red**: `#e74c3c` - Warnings, important
- **Accent Orange**: `#f39c12` - Cautions
- **Light Background**: `#f8f9fa` - Slide backgrounds

## Customization

Edit `custom.scss` to modify:
- Colors and fonts
- Spacing and layout
- Animation effects
- Responsive breakpoints

## File Structure

```
Presentation_Slide/
├── presentation.qmd     # Main presentation file
├── custom.scss          # Custom styling
└── README.md           # This file
```

## Tips for Presenting

1. **Navigation**: Use arrow keys or click
2. **Scrolling**: Some slides have scrollable content for detailed information
3. **Code Blocks**: Click to expand/collapse code
4. **Incremental Reveals**: Press space to reveal bullet points one at a time
5. **Speaker Notes**: Press 'S' for presenter view with notes

## Export Formats

- **HTML**: Full interactive experience
- **PDF**: Static export for distribution
- **PowerPoint**: Convert using Pandoc if needed

## Dependencies

- Python 3.8+
- NumPy
- SciPy
- Matplotlib
- Pandas
- Quarto 1.3+

## Author

LENG DEVID

## License

Educational use - Based on the Garman-Kohlhagen European Option Pricing project

## Notes

- All visualizations are generated from actual code execution
- Results are reproducible with consistent random seeds
- Mathematical derivations follow standard financial engineering textbooks
- Numerical methods validated against analytical solutions

---

For questions or issues, refer to the main project documentation.
