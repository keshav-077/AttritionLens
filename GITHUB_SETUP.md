# GitHub Setup Instructions

## Creating and Pushing AttritionLens to GitHub

### Step 1: Create New GitHub Repository

1. Go to https://github.com/new
2. **Repository name**: `AttritionLens`
3. **Description**: `HR Analytics Platform for Workforce Retention Intelligence - ML-powered attrition prediction with 96.2% accuracy`
4. **Visibility**: Public
5. **Do NOT** initialize with README, .gitignore, or license (we already have these)
6. Click **Create repository**

### Step 2: Initialize Local Git Repository

Open a terminal in the project directory and run:

```bash
cd C:\Github-all-repos\Employee-Churn-Prediction-main

# Initialize git repository
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: AttritionLens HR Analytics Platform

- Random Forest classifier with 96.2% accuracy, 93.8% AUC
- Feature engineering: overworked flag, data leakage prevention
- Streamlit web app with prediction form and EDA dashboard
- 7 structured Jupyter notebooks documenting full ML pipeline
- GridSearchCV hyperparameter tuning
- Interactive Plotly visualizations"

# Set main branch
git branch -M main

# Add remote (replace keshav-077 with your GitHub username)
git remote add origin https://github.com/keshav-077/AttritionLens.git

# Push to GitHub
git push -u origin main
```

### Step 3: Verify Upload

Go to `https://github.com/keshav-077/AttritionLens` and verify:
- ✅ README displays with logo and architecture diagram
- ✅ All SVG images render correctly
- ✅ Badges show properly
- ✅ LICENSE file is present

### Step 4: Add Topics (GitHub Repository Settings)

Click "Settings" → scroll to "Topics" → add:
- `machine-learning`
- `hr-analytics`
- `employee-attrition`
- `random-forest`
- `streamlit`
- `python`
- `scikit-learn`
- `data-science`
- `predictive-analytics`

### Step 5: Enable GitHub Pages (Optional - for Streamlit Cloud)

If you want to deploy the Streamlit app:

1. Go to https://share.streamlit.io/
2. Sign in with GitHub
3. Click "New app"
4. Select: `keshav-077/AttritionLens`
5. Main file path: `app.py`
6. Click "Deploy"

---

## Troubleshooting

### Large File Errors
If git complains about large model files:

```bash
# Add models to .gitignore
echo "models/*.pickle" >> .gitignore
echo "models/*.pkl" >> .gitignore
git rm --cached models/*.pickle models/*.pkl
git add .gitignore
git commit -m "Remove large model files from tracking"
```

Then re-upload models to GitHub Releases or use Git LFS.

### Authentication Issues
If push fails with authentication error:

1. Generate Personal Access Token: https://github.com/settings/tokens
2. Select scopes: `repo` (all)
3. Copy token
4. When prompted for password, paste the token (not your GitHub password)

Or use SSH:
```bash
git remote set-url origin git@github.com:keshav-077/AttritionLens.git
git push -u origin main
```
