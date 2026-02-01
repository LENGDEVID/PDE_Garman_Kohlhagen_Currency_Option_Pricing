# How to Host This Presentation on GitHub Pages

This project has been configured to be easily hosted on GitHub Pages. The Quarto presentation has been set to generate an `index.html` file, which is the default entry point for web servers.

## Prerequisites
- A GitHub account.
- Git installed on your computer.

## Step-by-Step Instructions

### 1. Initialize Git Repository
Open your terminal, navigate to this folder (`Presentation_Slide_Currency_Option_Pricing`), and run:

```bash
git init
git add .
git commit -m "Initial commit of presentation"
```

### 2. Create a Repository on GitHub
1. Log in to [GitHub](https://github.com).
2. Click the **+** icon in the top right and select **New repository**.
3. Name your repository (e.g., `currency-option-pricing-slides`).
4. **Important**: Make sure the repository is **Public** (unless you have GitHub Pro, Pages for private repos requires a paid plan).
5. **DO NOT** initialize with README, .gitignore, or license (you already have files).
6. Click **Create repository**.

### 3. Push to GitHub
Copy the commands provided by GitHub under "…or push an existing repository from the command line" and run them in your terminal. They will look like this:

```bash
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git push -u origin main
```
*(Replace `YOUR_USERNAME` and `YOUR_REPO_NAME` with your actual details)*

### 4. Enable GitHub Pages
1. On your repository page on GitHub, click **Settings** (top tab bar).
2. In the left sidebar, scroll down and click **Pages**.
3. Under **Build and deployment** > **Source**, select **Deploy from a branch**.
4. Under **Branch**, select `main` (or `master`) and ensure the folder is set to `/ (root)`.
5. Click **Save**.

### 5. View Your Presentation
GitHub will take a minute or two to build and deploy your site. 
- You will see the URL displayed at the top of the Pages settings page (usually `https://username.github.io/repo-name/`).
- Visit that URL to see your live presentation!

## Updating the Presentation
If you make changes to `presentation.qmd`:
1. Run `quarto render presentation.qmd` locally to regenerate `index.html`.
2. Commit and push the changes:
   ```bash
   git add .
   git commit -m "Update slides"
   git push
   ```
The site will automatically update.
