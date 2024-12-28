# Computational Urban Science

Source repository for the NetSI Computational Urban Science course

## Deploying labs based on private data

Because labs rely on private data that is only available in stella, the `.qmd` documents for labs need to be rendered in stella. We then version-control then rendered HTML documents and over-write these files with the correct versions in the GitHub Action that deploys the site. 

To update labs:

1. Render labs in stella with:

```
quarto render labs
```

2. Commit and push both the `labs/*.qmd` file and `_site/labs/*.html` files. 

This will trigger the GitHub Action to re-deploy the site with the updated labs.
