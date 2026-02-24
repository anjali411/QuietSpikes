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


## Optional ChatGPT meal autofill

You can paste a meal description in plain English (for example, `2 eggs, toast, banana, coffee`) and let ChatGPT estimate:

- carbs
- sugary drink grams
- protein
- fat
- fiber
- GI bucket (`low`/`medium`/`high`)
- likely eating order pattern

How to use it:

1. Enter your OpenAI API key in the app (client-side only, not stored by this project).
2. Click **Analyze with ChatGPT**.
3. Review/edit autofilled values before adding the event.

> Security note: because this is a static GitHub Pages app, API calls happen from the browser. Use a restricted key with limits; do not use a high-privilege production key.

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
