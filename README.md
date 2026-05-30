# CT ICU Learning App

GitHub Pages-ready static app.

## Required repository structure

```text
index.html
.nojekyll
content/
  domain1/
    cardiac-cycle.json
    afterload_svr_and_pvr.json
    cardiac_output_and_determinants.json
    contractility_and_inotropy.json
    frank_starling_mechanism.json
    mixed_venous_saturations.json
    oxygen_delivery_and_consumption.json
    preload_lvedp_and_cvp.json
versions/
  CT-ICU-Learning-App_v006_github_pages_ready.html
```

## GitHub Pages setup

1. Create a GitHub repository, for example `ct-icu-learning-app`.
2. Upload all files and folders in this package to the repository root.
3. Add your real JSON files to `content/domain1/`.
4. Go to repository Settings > Pages.
5. Under Build and deployment, choose Deploy from a branch.
6. Choose branch `main` and folder `/root`, then Save.
7. Open the Pages URL shown by GitHub after deployment.

## Why index.html exists

GitHub Pages automatically serves `index.html` at the site root. The versioned HTML copy is preserved in `versions/` so each build remains traceable.
