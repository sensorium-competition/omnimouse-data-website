---
title: omnimouse docs
homepage: true
hide:
  - navigation
  - toc
  - footer
---

**OmniMouse** is a unified AI model that predicts brain activity in the mouse visual cortex by jointly modeling visual input, neural activity, and behavior at unprecedented scale.

Trained on the largest single-neuron dataset to date, OmniMouse reveals a clear scaling law for neural modeling: predictive performance improves steadily with more data, while gains from increasing model size saturate beyond moderate scales. This identifies data — not model complexity — as the primary bottleneck for progress.

By combining multi-modal inputs and multi-task learning within a single transformer framework, OmniMouse supports forecasting and stimulus-conditioned prediction across neurons, stimuli, time, and animals. The model achieves state-of-the-art performance across nearly all evaluated tasks, demonstrating that unified architectures can match and exceed specialized approaches.

---

<div class="grid cards" markdown>

-   [:fontawesome-regular-newspaper:{ .lg .middle } __Read the paper__](https://openreview.net/forum?id=mEw4lhAn0F){:target="_blank"}

    ---

    `OmniMouse` paper!

-   [:material-book-open:{ .lg .middle } __Checkout the dataset__](https://huggingface.co/sinzlab)

    ---

    The entire dataset used in the paper uploaded to HuggingFace

- [__Interactive Metadata query__](metadata_query.md)

</div>

---