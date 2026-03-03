---
hide:
  - navigation
---

# Sensorium-XL dataset

On this page you can find summaries of the Sensorium-XL neurophysiological dataset used to train and evaluate OmniMouse, including sources, experimental modalities, and key recording characteristics. For details on individual experiment sessions, see [__Dataset Details__](dataset_details.md).  

All experiments were conducted in awake, head-fixed mice and approved by the Institutional Animal Care and Use Committee of Baylor College of Medicine.

## Sensorium-XL

The Sensorium-XL dataset was used for the OmniMouse Project and combines newly recorded data with prior recordings from other projects. The Sensorium-XL datasets contains all the othersets all the datasets listed below it.

**Source**
: Willeke et al., 2026 (OmniMouse)

**Animals / recordings**
: 78 unique mice overall (some appear in both training and evaluation), with 4,210–11,284 neurons per session and >3 million single-unit recordings in total.

**Neural data**
: Wide-field two-photon calcium imaging of excitatory neurons in layers 2–5 of right V1.

**Stimuli**
: Naturalistic images (ImageNet) and videos (cinatic movies + Sports-1M), plus parametric and synthetic stimuli (e.g., static/drifting Gabors, directional pink noise, flashing Gaussian dots, random dot kinematograms, model-generated stimuli). Presented at 30–60 Hz; images shown for 500 ms with 300–500 ms blank intervals.

**Behavior**
: Five aligned variables (locomotion speed, pupil size, pupil-size change, horizontal eye position, vertical eye position).  

## Sensorium 2022  

**Source**
: Willeke et al., 2022 (Sensorium 2022 competition)

**Animals / recordings**
: 7 behaving mice (7 recordings). Five “pretraining” recordings are released for training/generalization; two “competition” recordings are reserved for held-out evaluation (withheld responses for live and final test scoring).

**Stimuli**
: Natural images sampled from ImageNet, converted to grayscale; presented for 500 ms with 300–500 ms blank intervals.

**Neural data**
: Two-photon calcium imaging of excitatory neurons in layer 2/3 of right V1; responses aggregated 50–550 ms after stimulus onset (boxcar window).

**Behavior**
: Five aligned variables (locomotion speed, pupil size, pupil-size change, horizontal eye position, vertical eye position).

## Sensorium 2023  

**Source**
: Turishcheva et al., 2024 (Sensorium 2023 competition)

**Animals / recordings**
: 10 behaving mice (10 recordings). Five recordings are released fully as pretraining data; five additional recordings are used for held-out competition evaluation (live/final test responses withheld).

**Stimuli**
: Grayscale dynamic natural movies (cinematic clips + Sports-1M) presented at 30 Hz (~8–11 s clips), plus out-of-domain stimuli (ImageNet images, flashing Gaussian dots, random dot kinematograms, directional pink noise, drifting Gabors). For precise presentation details, see the whitepaper’s *Materials and Methods* section.

**Neural data**
: Wide-field two-photon calcium imaging of excitatory neurons in layers 2–5 of right V1.

**Behavior**
: Four aligned behavioral variables (locomotion speed, pupil size, horizontal pupil position, vertical pupil position).

## Paul’s paper (TBA)  

**Source**
: TBA

**Animals / recordings**
: 16 behaving mice (16 recordings). Eleven “pretraining” recordings are released for training/generalization; five recordings are reserved for held-out evaluation.

**Stimuli**
: TBA

**Neural data**
: Wide-field two-photon calcium imaging of excitatory neurons in layers 2–5 of right V1.

**Behavior**
: Four aligned behavioral variables (locomotion speed, pupil size, horizontal pupil position, vertical pupil position).
