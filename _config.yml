name: Deploy Marflow Website
on:
  push:
    branches: ["main"] # Make sure your branch is named 'main'
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Pages
        uses: actions/configure-pages@v4
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: '.' # This looks for your index.html in the main folder
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
