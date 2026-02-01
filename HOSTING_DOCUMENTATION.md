# Complete Hosting Documentation
## Garman-Kohlhagen Currency Option Pricing Project

**Author**: Leng Devid  
**Date**: February 1, 2026  
**Project**: PDE Garman-Kohlhagen Currency Option Pricing

---

## Table of Contents

1. [Overview](#overview)
2. [Architecture](#architecture)
3. [GitHub Pages Setup](#github-pages-setup)
4. [Streamlit Cloud Deployment](#streamlit-cloud-deployment)
5. [Website Integration](#website-integration)
6. [Maintenance & Updates](#maintenance--updates)
7. [Troubleshooting](#troubleshooting)

---

## Overview

This project is hosted using **two free platforms**:

| Component | Platform | URL | Cost |
|-----------|----------|-----|------|
| **Quarto Website** | GitHub Pages | https://lengdevid.github.io/PDE_Garman_Kohlhagen_Currency_Option_Pricing/ | FREE |
| **Streamlit App** | Streamlit Community Cloud | https://pdegarmankohlhagencurrencyoptionpricing-aoph8lblbkhpztlgcxacck.streamlit.app | FREE |

**Total Monthly Cost**: $0.00 ✅

---

## Architecture

### Project Structure

```
PDE_Garman_Kohlhagen_Currency_Option_Pricing/
├── docs/                                    # GitHub Pages serves from here
│   ├── index.html                          # Homepage
│   ├── Presentation_Slide_Currency_Option_Pricing/
│   │   └── index.html                      # Presentation slides
│   ├── Source_Code/
│   │   └── European_Option_Currency_Pricing.html
│   └── site_libs/                          # Shared libraries
│
├── Streamlit_python_app/                   # Streamlit Cloud serves from here
│   ├── app.py                              # Main Streamlit application
│   └── requirements.txt                    # Python dependencies
│
├── _quarto.yml                             # Quarto website configuration
├── index.qmd                               # Homepage source
├── .nojekyll                               # Disables Jekyll processing
└── README.md                               # Repository documentation
```

### Hosting Flow

```
User visits website
        ↓
GitHub Pages (lengdevid.github.io)
        ↓
    ┌───────────────────┬───────────────────┬───────────────────┐
    ↓                   ↓                   ↓                   ↓
Homepage          Presentation        Source Code      Interactive App
(index.html)      (RevealJS)         (Quarto Doc)     (External Link)
                                                              ↓
                                                    Streamlit Cloud
                                                    (streamlit.app)
```

---

## GitHub Pages Setup

### Step 1: Repository Configuration

**Repository**: `LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing`  
**Visibility**: Public (required for free GitHub Pages)  
**Branch**: `main`

### Step 2: Quarto Configuration

Created `_quarto.yml` to define website structure:

```yaml
project:
  type: website
  output-dir: docs        # Output to docs/ folder

website:
  title: "Garman-Kohlhagen Currency Option Pricing"
  description: "Complete PDE Analysis: From Theory to Implementation"
  
  navbar:
    background: primary
    search: true
    left:
      - text: "Home"
        href: index.qmd
      - text: "Presentation"
        href: Presentation_Slide_Currency_Option_Pricing/presentation.qmd
      - text: "Source Code"
        href: Source_Code/European_Option_Currency_Pricing.qmd
      - text: "Interactive App"
        href: https://pdegarmankohlhagencurrencyoptionpricing-aoph8lblbkhpztlgcxacck.streamlit.app
    right:
      - icon: github
        href: https://github.com/LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing
        aria-label: GitHub Repository

format:
  html:
    theme: cosmo
    css: styles.css
    toc: true
    code-fold: true
    link-external-newwindow: true
```

**Key Configuration Choices**:
- `output-dir: docs` → GitHub Pages can serve from `/docs` folder
- `link-external-newwindow: true` → External links open in new tabs
- `theme: cosmo` → Professional Bootstrap theme

### Step 3: Build Website

```bash
# Render Quarto website
quarto render

# Output created in docs/ folder
# docs/index.html
# docs/Presentation_Slide_Currency_Option_Pricing/index.html
# docs/Source_Code/European_Option_Currency_Pricing.html
```

### Step 4: Disable Jekyll Processing

Created `.nojekyll` file to prevent GitHub from processing files with Jekyll:

```bash
touch .nojekyll
```

**Why this is needed**: 
- GitHub Pages uses Jekyll by default
- Jekyll ignores folders starting with `_` (like `_site`)
- `.nojekyll` tells GitHub to serve files as-is

### Step 5: Fix Git Submodule Issue

**Problem**: Presentation folder was treated as a git submodule, causing deployment failure.

**Solution**:
```bash
# Remove from git index as submodule
git rm --cached Presentation_Slide_Currency_Option_Pricing

# Re-add as regular directory
git add Presentation_Slide_Currency_Option_Pricing

# Commit and push
git commit -m "Fix submodule issue - add presentation folder as regular directory"
git push origin main
```

**Error message that was fixed**:
```
No url found for submodule path 'Presentation_Slide_Currency_Option_Pricing' in .gitmodules
```

### Step 6: Configure GitHub Pages Settings

1. Go to: `https://github.com/LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing/settings/pages`

2. Configure:
   - **Source**: Deploy from a branch
   - **Branch**: `main`
   - **Folder**: `/docs` ← **Important!**

3. Click **Save**

4. Wait 1-2 minutes for deployment

5. Website live at: `https://lengdevid.github.io/PDE_Garman_Kohlhagen_Currency_Option_Pricing/`

### Step 7: Commit and Deploy

```bash
# Add all files
git add .

# Commit
git commit -m "Add Quarto website configuration"

# Push to GitHub
git push origin main

# GitHub Actions automatically builds and deploys
```

---

## Streamlit Cloud Deployment

### Step 1: Prepare Application

**File**: `Streamlit_python_app/app.py` (849 lines)

**Features**:
- 5 interactive sections
- Real-time parameter adjustments
- Professional dark theme
- Plotly visualizations

### Step 2: Create Requirements File

Created `Streamlit_python_app/requirements.txt`:

```txt
streamlit>=1.30.0
numpy>=1.24.0
pandas>=2.0.0
scipy>=1.11.0
plotly>=5.18.0
```

**Why these versions**:
- `streamlit>=1.30.0` → Latest features and bug fixes
- `numpy>=1.24.0` → Required for scipy compatibility
- `pandas>=2.0.0` → DataFrame performance improvements
- `scipy>=1.11.0` → Statistical functions (norm.cdf, norm.pdf)
- `plotly>=5.18.0` → Interactive 3D plots and surfaces

### Step 3: Push to GitHub

```bash
# Add requirements file
git add Streamlit_python_app/requirements.txt

# Commit
git commit -m "Add requirements.txt for Streamlit Cloud deployment"

# Push
git push origin main
```

### Step 4: Deploy to Streamlit Cloud

1. **Go to**: https://share.streamlit.io/

2. **Sign in** with GitHub account

3. **Click**: "New app" button

4. **Fill in deployment form**:
   - **Repository**: `LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing`
   - **Branch**: `main`
   - **Main file path**: `Streamlit_python_app/app.py`
   - **App URL** (optional): `pdegarmankohlhagencurrencyoptionpricing`

5. **Click**: "Deploy!"

6. **Wait** 2-3 minutes for deployment

7. **App live at**: `https://pdegarmankohlhagencurrencyoptionpricing-aoph8lblbkhpztlgcxacck.streamlit.app`

### Step 5: Verify Deployment

**Check**:
- App loads without errors ✅
- All 5 sections accessible ✅
- Parameters adjust in real-time ✅
- Plots render correctly ✅

---

## Website Integration

### Step 1: Add to Navigation Bar

**File**: `_quarto.yml`

**Added**:
```yaml
navbar:
  left:
    # ... existing links ...
    - text: "Interactive App"
      href: https://pdegarmankohlhagencurrencyoptionpricing-aoph8lblbkhpztlgcxacck.streamlit.app
```

### Step 2: Update Homepage Layout

**File**: `index.qmd`

**Changed from 2-column to 3-column grid**:

```markdown
::: {.grid}

::: {.g-col-4}
### 📊 [Presentation Slides](...)
...
:::

::: {.g-col-4}
### 💻 [Source Code Documentation](...)
...
:::

::: {.g-col-4}
### 🚀 [Interactive Application](https://pdegarmankohlhagencurrencyoptionpricing-aoph8lblbkhpztlgcxacck.streamlit.app)

Live Streamlit app for interactive exploration:

- **Real-time Pricing**: Adjust parameters and see instant results
- **Greeks Visualization**: Interactive plots of all Greeks
- **Method Comparison**: FTCS, BTCS, Crank-Nicolson side-by-side
- **Stability Analysis**: Von Neumann stability verification
- **3D Surfaces**: Explore option price landscapes

[Launch App →](https://pdegarmankohlhagencurrencyoptionpricing-aoph8lblbkhpztlgcxacck.streamlit.app){.btn .btn-primary target="_blank"}
:::

:::
```

### Step 3: Rebuild and Deploy

```bash
# Render website with new changes
quarto render

# Commit changes
git add _quarto.yml index.qmd docs/
git commit -m "Add Interactive Streamlit App to website navigation"

# Push to GitHub
git push origin main

# GitHub Pages auto-deploys in 1-2 minutes
```

### Step 4: Verify Integration

**Checked**:
- Navigation bar shows "Interactive App" link ✅
- Homepage has 3-column layout ✅
- "Launch App →" button works ✅
- Link opens in new tab ✅
- Streamlit app loads correctly ✅

---

## Maintenance & Updates

### Updating the Quarto Website

```bash
# 1. Make changes to .qmd files
# Edit index.qmd, presentation.qmd, etc.

# 2. Render website
quarto render

# 3. Commit and push
git add .
git commit -m "Update website content"
git push origin main

# 4. GitHub Pages auto-deploys (1-2 minutes)
```

### Updating the Streamlit App

```bash
# 1. Make changes to app.py
# Edit Streamlit_python_app/app.py

# 2. Test locally (optional)
streamlit run Streamlit_python_app/app.py

# 3. Commit and push
git add Streamlit_python_app/app.py
git commit -m "Update Streamlit app"
git push origin main

# 4. Streamlit Cloud auto-deploys (1-2 minutes)
```

### Adding New Dependencies

If you add new Python libraries to `app.py`:

```bash
# 1. Update requirements.txt
echo "new-library>=1.0.0" >> Streamlit_python_app/requirements.txt

# 2. Commit and push
git add Streamlit_python_app/requirements.txt
git commit -m "Add new dependency"
git push origin main

# 3. Streamlit Cloud auto-installs and redeploys
```

### Monitoring Deployments

**GitHub Pages**:
- Check: https://github.com/LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing/actions
- Look for "pages build and deployment" workflow
- Green checkmark = successful deployment

**Streamlit Cloud**:
- Dashboard: https://share.streamlit.io/
- Click on your app → "Manage app"
- View logs, analytics, and deployment status

---

## Troubleshooting

### GitHub Pages Issues

#### Issue: Website shows README instead of Quarto site

**Cause**: GitHub Pages serving from wrong folder

**Solution**:
1. Go to repository settings → Pages
2. Change folder from "/ (root)" to "/docs"
3. Click Save
4. Wait 1-2 minutes

#### Issue: 404 errors for some pages

**Cause**: Missing `.nojekyll` file

**Solution**:
```bash
touch .nojekyll
git add .nojekyll
git commit -m "Add .nojekyll file"
git push origin main
```

#### Issue: Submodule error in GitHub Actions

**Error**: `No url found for submodule path '...' in .gitmodules`

**Solution**:
```bash
# Remove folder from git index
git rm --cached <folder-name>

# Re-add as regular directory
git add <folder-name>

# Commit and push
git commit -m "Fix submodule issue"
git push origin main
```

### Streamlit Cloud Issues

#### Issue: "Module not found" error

**Cause**: Missing dependency in `requirements.txt`

**Solution**:
```bash
# Add missing library to requirements.txt
echo "missing-library>=1.0.0" >> Streamlit_python_app/requirements.txt

# Commit and push
git add Streamlit_python_app/requirements.txt
git commit -m "Add missing dependency"
git push origin main
```

#### Issue: App won't start

**Cause**: Error in `app.py`

**Solution**:
1. Check logs in Streamlit Cloud dashboard
2. Fix error in `app.py`
3. Test locally: `streamlit run Streamlit_python_app/app.py`
4. Commit and push fix

#### Issue: App is slow or unresponsive

**Cause**: Heavy computations or large datasets

**Solution**:
```python
# Add caching to expensive functions
import streamlit as st

@st.cache_data
def expensive_computation(params):
    # Your computation here
    return result
```

#### Issue: App sleeps after inactivity

**Behavior**: This is normal for free tier

**Solution**: 
- App wakes up automatically when visited (5-10 seconds)
- No action needed
- This is expected behavior for Streamlit Community Cloud

---

## Performance Optimization

### Quarto Website

**Optimize images**:
```bash
# Compress images before adding to repository
# Use tools like ImageOptim, TinyPNG, or:
convert input.png -quality 85 output.png
```

**Enable caching**:
```yaml
# In _quarto.yml
execute:
  freeze: auto  # Cache computational results
```

### Streamlit App

**Cache expensive computations**:
```python
@st.cache_data
def compute_option_price(S, K, r, sigma, T):
    # Expensive calculation
    return price

@st.cache_resource
def load_large_dataset():
    # Load once, reuse across sessions
    return data
```

**Optimize plots**:
```python
# Use smaller datasets for plots
S_range = np.linspace(S0*0.7, S0*1.3, 50)  # Instead of 1000 points
```

---

## Security Considerations

### GitHub Pages

- ✅ **HTTPS enabled** by default
- ✅ **No server-side code** (static files only)
- ✅ **No sensitive data** in public repository
- ⚠️ **Repository must be public** for free GitHub Pages

### Streamlit Cloud

- ✅ **HTTPS enabled** by default
- ✅ **Secrets management** available (if needed)
- ✅ **No sensitive data** in public repository
- ⚠️ **Repository must be public** for free tier

**Best Practices**:
- Never commit API keys or passwords
- Use Streamlit secrets for sensitive configuration
- Keep repository public (required for free hosting)

---

## Cost Analysis

### Current Setup (FREE)

| Service | Plan | Cost | Limitations |
|---------|------|------|-------------|
| **GitHub Pages** | Free | $0/month | 100 GB bandwidth/month, 1 GB storage |
| **Streamlit Cloud** | Community | $0/month | 1 GB RAM per app, apps sleep after inactivity |
| **Total** | - | **$0/month** | Sufficient for academic projects |

### Upgrade Options (If Needed)

| Service | Paid Plan | Cost | Benefits |
|---------|-----------|------|----------|
| **GitHub Pages** | GitHub Pro | $4/month | Private repos, advanced features |
| **Streamlit Cloud** | Starter | $20/month | No sleep, more resources, private apps |

**Recommendation**: Free tier is perfect for academic projects and portfolios.

---

## Backup & Recovery

### Backup Strategy

**Git repository** = automatic backup
- All code versioned in Git
- Hosted on GitHub (cloud backup)
- Can clone to any machine

**Backup commands**:
```bash
# Clone repository to backup location
git clone https://github.com/LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing.git backup/

# Or pull latest changes
cd backup/
git pull origin main
```

### Recovery Procedures

**If GitHub Pages breaks**:
1. Check GitHub Actions for errors
2. Revert to last working commit:
   ```bash
   git revert HEAD
   git push origin main
   ```

**If Streamlit Cloud breaks**:
1. Check logs in Streamlit dashboard
2. Redeploy from dashboard
3. Or revert code and push:
   ```bash
   git revert HEAD
   git push origin main
   ```

**Complete disaster recovery**:
```bash
# Clone repository
git clone https://github.com/LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing.git

# Rebuild Quarto site
cd PDE_Garman_Kohlhagen_Currency_Option_Pricing
quarto render

# Push to GitHub
git push origin main

# Redeploy Streamlit app from dashboard
```

---

## Analytics & Monitoring

### GitHub Pages Analytics

**Built-in traffic stats**:
1. Go to repository → Insights → Traffic
2. View:
   - Unique visitors
   - Page views
   - Referring sites
   - Popular content

**Add Google Analytics** (optional):
```yaml
# In _quarto.yml
website:
  google-analytics: "G-XXXXXXXXXX"
```

### Streamlit Cloud Analytics

**Dashboard metrics**:
1. Go to https://share.streamlit.io/
2. Click on your app → "Analytics"
3. View:
   - Active users
   - Session duration
   - Error rates
   - Resource usage

---

## Summary

### What We Hosted

1. **Quarto Website** on GitHub Pages
   - Homepage with 3-column layout
   - Presentation slides (RevealJS)
   - Source code documentation
   - Professional navigation

2. **Streamlit App** on Streamlit Community Cloud
   - Interactive option pricing
   - Real-time parameter adjustments
   - 5 comprehensive sections
   - Professional UI/UX

### Key Files

| File | Purpose |
|------|---------|
| `_quarto.yml` | Website configuration |
| `index.qmd` | Homepage source |
| `.nojekyll` | Disable Jekyll processing |
| `Streamlit_python_app/app.py` | Streamlit application |
| `Streamlit_python_app/requirements.txt` | Python dependencies |
| `docs/` | Built website (served by GitHub Pages) |

### URLs

- **Website**: https://lengdevid.github.io/PDE_Garman_Kohlhagen_Currency_Option_Pricing/
- **Streamlit App**: https://pdegarmankohlhagencurrencyoptionpricing-aoph8lblbkhpztlgcxacck.streamlit.app
- **Repository**: https://github.com/LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing

### Total Cost

**$0.00/month** - Everything is 100% FREE! 🎉

---

## Additional Resources

### Documentation

- **Quarto**: https://quarto.org/docs/websites/
- **GitHub Pages**: https://docs.github.com/en/pages
- **Streamlit**: https://docs.streamlit.io/
- **Streamlit Cloud**: https://docs.streamlit.io/streamlit-community-cloud

### Support

- **Quarto Community**: https://github.com/quarto-dev/quarto-cli/discussions
- **Streamlit Forum**: https://discuss.streamlit.io/
- **GitHub Support**: https://support.github.com/

---

**Document Version**: 1.0  
**Last Updated**: February 1, 2026  
**Maintained By**: Leng Devid
