---
title: Sensorium-XL dataset
homepage: true
hide:
  - navigation
  - toc
  - footer
---

The **Sensorium-XL dataset** is the largest single-neuron dataset to date. It contains visual stimuli, neural responses, and behavioral measurements, and combines newly recorded data with recordings from the **Sensorium 2022** and **Sensorium 2023** Competitions. In total, it includes **333 experiments** collected from **78 mice**, and is being released alongside the **OmniMouse** project.

**Sensorium-XL** was used to train **OmniMouse**, a unified AI model that predicts activity in mouse visual cortex by jointly modeling visual input, neural responses, and behavior.

---

<h2 style="text-align: center; margin: 2.2rem 0 1.2rem 0;">Get started</h2>

<div class="grid cards" style="gap: 1.25rem;" markdown>

-   [:fontawesome-regular-newspaper:{ .lg .middle } __Read the OmniMouse paper__](https://openreview.net/forum?id=mEw4lhAn0F){:target="_blank"}

    Background, methodology, and results for OmniMouse, plus an overview of Sensorium-XL.

-   [:material-book-open:{ .lg .middle } __Explore the dataset on Hugging Face__](https://huggingface.co/datasets/sensorium-competition/omnimouse){:target="_blank"}

    Browse and download the full dataset used in the paper.

-   [:material-table:{ .lg .middle } __Dataset Details__](dataset_details.md)

    Session-level metadata and per-experiment information.

</div>

---

<h2 style="text-align: center; margin: 2.6rem 0 1.2rem 0;">Resources</h2>

<div class="grid cards" style="gap: 1.25rem;" markdown>

-   [:material-github:{ .lg .middle } __Experanto__](https://github.com/sensorium-competition/experanto){:target="_blank"}

    Python package for working with neuroscience recordings and stimuli, including interpolation utilities. Specifically designed for the dataformats of the Sensorium competitions and OmniMouse data.

-   [:material-github:{ .lg .middle } __Sensorium 2023 codebase__](https://github.com/ecker-lab/sensorium_2023){:target="_blank"}

    Tutorials, baseline models, and notebooks to get started quickly.

-   [:material-github:{ .lg .middle } __OmniMouse codebase__](#)

    OmniMouse model and data pipeline built on Experanto. (Link coming soon.)

</div>

<!-- Optional extra breathing room at page end -->
<div style="height: 1.5rem;"></div>