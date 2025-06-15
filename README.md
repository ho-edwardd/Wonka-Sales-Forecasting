## Overview
This project uses a two-segment (two latent classes) Burr XII or Weibull-Gamma model to forecast ticket sales for the movie "Wonka" after its release. The model incorporates a spike at 0 to account for Hardcore Never Buyers (HCNB) and segments the population into two latent classes to capture different viewing behaviors, such as the Christmas break effect for younger audiences and general weekend trends for older audiences. The power of this model comes from the fact that the model is able to achieve ~14% MAPE, 0.3% cumulative MAPE, and ~99% variance explained with static, determinsitic features. This allows for a robust, lightweight that could be extrapolated out to films for forecasting.

## Model Description
Key Components:
Two-Segment Burr XII/Weibull-Gamma Model:

Segment 1: Represents the general population with typical viewing patterns (e.g., weekend spikes).

Segment 2: Captures the "Christmas break" or "winter watchers" demographic, likely children with more flexible viewing schedules during holidays.

Hardcore Never Buyers (HCNB):

A spike at 0 accounts for individuals who are unlikely to purchase tickets under any circumstances.

Covariates:

Opening Weekend: Binary indicator for the first few days of release.

Day of Week: Friday, Saturday, Sunday indicators.

Holiday: Binary indicator for holidays (e.g., Christmas, New Year's).

Discount Tuesday: Binary indicator for discounted ticket days.

Streaming Availability: Binary indicator for when the movie becomes available on streaming platforms.

## Sheets:
Wonka Data:

Contains daily ticket sales (Unit sales) and covariates from December 15, 2023, to March 15, 2024.

Columns:

Date, Day, Unit sales, Opening Weekend, Saturday, Sunday, Holiday, Discount Tuesday, Streaming Available.

2-seg WG (Burr XII) HCNB:

Model parameters and predictions for the two-segment Burr XII/Weibull-Gamma model.

Includes:

Parameters for each segment (c1, r1, alpha1, pi1, etc.).

Predicted values (Predicted), absolute percentage errors (APE), and cumulative metrics.

Performance metrics: Log-Likelihood (LL), BIC, MAPE, MSE, R-squared.

Hold-out Testing (40 days):

Evaluates the model's performance on a hold-out dataset.

Similar structure to the "2-seg WG" sheet but with adjusted parameters for testing.
