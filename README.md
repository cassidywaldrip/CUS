# Computational Urban Science

Source repository for the NetSI Computational Urban Science course

## Deploying labs based on private data

Because labs rely on private data that is only available in stella, the `.qmd` documents for labs need to be rendered in stella. We then version-control then rendered HTML documents and over-write these files with the correct versions in the GitHub Action that deploys the site. 

**WARNING:** the version of `quarto` used to render labs must be the same as the version used for deploying the rest of the site. Currently, the deployment action depends on Quarto [v1.5.57](https://github.com/SUNLab-NetSI/CUS/blob/10178606213356e41badb8a35e4d9693cdaf574a/.github/workflows/deploy.yml#L35-L38). This is the latest version of quarto available from conda-forge (as of Dec 28th 2024), making it easy to install in stella. If the rendered lab pages look different from the rest of the site when deployed, check that your local quarto installation has the same version as the deployment action.

To update labs:

1. Render labs in stella with:

```
quarto render labs
```

2. Commit and push both the `labs/*.qmd` file and `_site/labs/*.html` files. 

This will trigger the GitHub Action to re-deploy the site with the updated labs.
