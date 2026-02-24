# Daily Blood Sugar Approximation Tool

A lightweight single-page prototype that estimates a person's daily blood glucose curve based on:

- What they ate/drank and when.
- Meal composition (carbs, protein, fat, fiber).
- Glycemic index choice.
- **Meal order** (vegetables/protein first vs mixed vs carbs first).

## Run locally

```bash
python3 -m http.server 4173
```

Then open <http://localhost:4173>.

## Deploy on GitHub Pages

This project is intentionally a plain static site (`index.html`) with no build step, so it works directly with GitHub Pages.

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select your publishing branch (usually `main`) and the `/ (root)` folder.
5. Save and wait for deployment.

The repo includes a `.nojekyll` file to ensure Pages serves files as-is.

## Model notes

This app uses a simplified educational model, not a medical device model:

- Baseline glucose starts around 90 mg/dL.
- Net carb load drives spike size.
- Fiber/protein/fat dampen fast absorption.
- GI and meal order alter rise magnitude and time-to-peak.
- Outputs include:
  - Peak glucose
  - Average glucose
  - Time above 140 mg/dL
  - Variability estimate (standard deviation)

## Disclaimer

For learning and rough self-experimentation only. Not medical advice.
