# Deployment Guide - Recall Network Tutorial Website

## 🚀 GitHub Integration

### Step 1: Create GitHub Repository

1. Go to [GitHub.com](https://github.com) and sign in
2. Click the "+" icon in the top right corner
3. Select "New repository"
4. Repository name: `recall-network-tutorial` (or your preferred name)
5. Description: "Complete tutorial website for building AI trading agents on Recall Network using Mastra framework"
6. Make it **Public** (recommended for open source)
7. **Don't** initialize with README (we already have one)
8. Click "Create repository"

### Step 2: Connect Local Repository to GitHub

Run these commands in your terminal (replace `YOUR_USERNAME` with your GitHub username):

```bash
# Add GitHub remote
git remote add origin https://github.com/YOUR_USERNAME/recall-network-tutorial.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Scroll down to "Pages" section
4. Under "Source", select "Deploy from a branch"
5. Select "main" branch and "/ (root)" folder
6. Click "Save"
7. Your website will be available at: `https://YOUR_USERNAME.github.io/recall-network-tutorial`

## 🌐 Alternative Deployment Options

### Netlify (Recommended)
1. Go to [Netlify.com](https://netlify.com)
2. Sign up/login with GitHub
3. Click "New site from Git"
4. Connect your GitHub repository
5. Deploy settings:
   - Build command: (leave empty)
   - Publish directory: (leave empty - root)
6. Click "Deploy site"

### Vercel
1. Go to [Vercel.com](https://vercel.com)
2. Sign up/login with GitHub
3. Click "New Project"
4. Import your GitHub repository
5. Deploy settings:
   - Framework Preset: Other
   - Build Command: (leave empty)
   - Output Directory: (leave empty)
6. Click "Deploy"

### GitHub Pages (Alternative Method)
If you prefer to use GitHub Actions:

1. Create `.github/workflows/deploy.yml`:
```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./
```

## 🔧 Custom Domain (Optional)

If you have a custom domain:

1. Add a `CNAME` file to your repository root:
```
your-domain.com
```

2. Configure DNS:
   - Add a CNAME record pointing to `YOUR_USERNAME.github.io`

## 📱 PWA Features

The website includes PWA capabilities:
- Service Worker for offline functionality
- App manifest for mobile installation
- Caching for fast loading

## 🔄 Updates

To update the website:
1. Make changes to your local files
2. Commit changes: `git add . && git commit -m "Update message"`
3. Push to GitHub: `git push origin main`
4. The website will automatically update (depending on deployment method)

## 📊 Performance

The website is optimized for:
- Fast loading times
- Mobile responsiveness
- SEO optimization
- Accessibility compliance

## 🛠️ Local Development

To run locally:
```bash
# Using Python (if installed)
python -m http.server 8000

# Using Node.js (if installed)
npx serve .

# Using PHP (if installed)
php -S localhost:8000
```

Then visit: `http://localhost:8000`

## 📞 Support

For issues or questions:
- Create an issue on GitHub
- Contact: developer@recall.network
- Official Recall Network: https://docs.recall.network
