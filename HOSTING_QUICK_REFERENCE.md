# Quick Reference: Hosting Commands

## 🚀 Quick Links

- **Website**: https://lengdevid.github.io/PDE_Garman_Kohlhagen_Currency_Option_Pricing/
- **Streamlit App**: https://pdegarmankohlhagencurrencyoptionpricing-aoph8lblbkhpztlgcxacck.streamlit.app
- **Repository**: https://github.com/LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing

---

## 📝 Common Tasks

### Update Website Content

```bash
# 1. Edit .qmd files (index.qmd, presentation.qmd, etc.)

# 2. Render website
quarto render

# 3. Deploy
git add .
git commit -m "Update website content"
git push origin main

# 4. Wait 1-2 minutes for GitHub Pages to update
```

### Update Streamlit App

```bash
# 1. Edit Streamlit_python_app/app.py

# 2. Test locally (optional)
streamlit run Streamlit_python_app/app.py

# 3. Deploy
git add Streamlit_python_app/app.py
git commit -m "Update Streamlit app"
git push origin main

# 4. Wait 1-2 minutes for Streamlit Cloud to update
```

### Add New Python Library

```bash
# 1. Add to requirements.txt
echo "library-name>=1.0.0" >> Streamlit_python_app/requirements.txt

# 2. Deploy
git add Streamlit_python_app/requirements.txt
git commit -m "Add new dependency"
git push origin main
```

### Preview Website Locally

```bash
# Start local preview server
quarto preview

# Opens at http://localhost:4200/
# Auto-reloads when you edit files
```

### Preview Streamlit App Locally

```bash
# Run Streamlit app locally
streamlit run Streamlit_python_app/app.py

# Opens at http://localhost:8501/
```

---

## 🔍 Check Deployment Status

### GitHub Pages

```bash
# Check GitHub Actions
open https://github.com/LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing/actions

# Or visit your website
open https://lengdevid.github.io/PDE_Garman_Kohlhagen_Currency_Option_Pricing/
```

### Streamlit Cloud

```bash
# Open Streamlit dashboard
open https://share.streamlit.io/

# Or visit your app
open https://pdegarmankohlhagencurrencyoptionpricing-aoph8lblbkhpztlgcxacck.streamlit.app
```

---

## 🛠️ Troubleshooting

### Website not updating?

```bash
# Hard refresh browser (bypass cache)
# Mac: Cmd + Shift + R
# Windows: Ctrl + Shift + R

# Or check GitHub Actions for errors
open https://github.com/LENGDEVID/PDE_Garman_Kohlhagen_Currency_Option_Pricing/actions
```

### Streamlit app not updating?

```bash
# Check Streamlit Cloud logs
# 1. Go to https://share.streamlit.io/
# 2. Click on your app
# 3. Click "Manage app" → "Logs"

# Or manually reboot app from dashboard
```

### Undo last commit

```bash
# Revert last commit
git revert HEAD
git push origin main
```

---

## 📊 Project Structure

```
PDE_Garman_Kohlhagen_Currency_Option_Pricing/
├── docs/                          # Built website (auto-generated)
├── Streamlit_python_app/
│   ├── app.py                     # Streamlit app
│   └── requirements.txt           # Dependencies
├── _quarto.yml                    # Website config
├── index.qmd                      # Homepage
├── .nojekyll                      # GitHub Pages config
├── HOSTING_DOCUMENTATION.md       # Full documentation
└── README.md                      # Repository info
```

---

## 💰 Costs

- **GitHub Pages**: FREE
- **Streamlit Cloud**: FREE
- **Total**: $0.00/month

---

## 📚 Full Documentation

See [HOSTING_DOCUMENTATION.md](HOSTING_DOCUMENTATION.md) for complete details on:
- Architecture
- Setup process
- Maintenance
- Troubleshooting
- Performance optimization
- Security considerations

---

**Last Updated**: February 1, 2026
