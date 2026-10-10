# Calibrate the Horizon

A small offline betting game based on one idea from [Nguyen and Fithian's time-horizon paper](https://arxiv.org/abs/2610.12466): equal multipliers in human task time can correspond to different changes in AI task difficulty. Compare two jumps, place a bet, and build a streak.

## Run

Open `demo/index.html` directly in a modern browser. It has no build step, server, install, or network request.

## Play

Adjust the start and end time sliders for jumps A and B. Choose which jump gains more difficulty points along the curve. A correct bet earns points and extends your streak; an incorrect bet ends it. Choose **Next round** for a deterministic new comparison or **Reset game** to replay from the opening pair. The chart marks the selected endpoints and highlights the 2–30 minute flat zone.

Every categorical bet is treated as a fixed 75% forecast on the selected answer. The reveal reports log loss and Brier score; lower values are better. These are examples of proper scoring rules, not measurements from the paper's cross-validation.

## What this demo does and does not show

The game uses a monotone, hand-shaped teaching curve with a nearly flat segment from 2 to 30 minutes and a steeper rise outside it. Difficulty points have arbitrary units. The curve is not fitted from METR data and is not the paper's Model 2 output. There are no METR task records, no AI success estimates, no model fitting, and no benchmark accuracy claims. This is an independent educational implementation, not endorsed by the authors.

The source paper analyzed 228 tasks and 26 AIs and describes a fitted function that converts human time to AI task difficulty. It reports a nearly flat fitted region from 2–30 minutes and argues that equal time multipliers can have different meanings in different parts of the curve. Read the paper for the statistical model and data analysis.

## Provenance and license

- Paper inspiration: Drew T. Nguyen and William Fithian, [“On the estimation and validity of AI time horizons—a statistical look at the METR plot”](https://arxiv.org/abs/2610.12466), arXiv:2610.12466.
- Implementation and original interface copy: Virtual Lab engineer agent Rivet, running in the Paperclip frontier-model environment. The exact runtime model name is not exposed to this workspace.
- Third-party code, data, weights, fonts, and image assets: none.
- Original demo code: MIT License; see `LICENSE`.
