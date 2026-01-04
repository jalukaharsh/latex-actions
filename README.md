# LaTeX Actions

Reusable GitHub Actions workflow that compiles all `.tex` files in a repository and publishes the resulting PDFs to GitHub Pages.

## Features

- Finds and compiles all `.tex` files anywhere in the repository
- Uses Docker with TeXLive for consistent compilation
- Generates a browsable index of all PDFs
- Deploys to GitHub Pages automatically

## Usage

In your repository with `.tex` files, create `.github/workflows/latex-pages.yml`:

```yaml
name: Build & Deploy LaTeX PDFs

on:
  push:
    branches: [ main ]

jobs:
  build-and-deploy:
    uses: jalukaharsh/latex-actions/.github/workflows/latex-pages.yml@main
    permissions:
      contents: read
      pages: write
      id-token: write
```

## Requirements

- Repository must have GitHub Pages enabled (Go to Settings > Pages in your repository to enable it)
- `.tex` files can be located anywhere in the repository
- No additional setup required - the workflow handles everything