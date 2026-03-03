---
hide:
  - navigation
---

<style>
/* Layout */
.sxl-wrap { max-width: 980px; margin: 0 auto; }

/* Cards */
.sxl-card{
  margin: 0 0 1.8rem 0;
  border-radius: 16px;
  border: 1px solid var(--md-default-fg-color--lightest);
  background: var(--md-default-bg-color);
  box-shadow: 0 1px 0 rgba(0,0,0,.04);
  overflow: hidden; /* keeps header corners clean */
}

/* Card header */
.sxl-card__head{
  padding: .95rem 1.15rem;
  border-bottom: 1px solid var(--md-default-fg-color--lightest);
  background: color-mix(in srgb, var(--md-default-bg-color) 92%, var(--md-accent-fg-color) 8%);
}
.sxl-card__head h2{
  margin: 0;
  font-size: 1.05rem;
  line-height: 1.25;
  text-align: center;
}

/* Card body */
.sxl-card__body{ padding: 1.05rem 1.25rem 1.15rem 1.25rem; }
.sxl-card__body > p{ margin: 0 0 .9rem 0; color: var(--md-default-fg-color--light); }

/* Definition list formatting */
.sxl-dl { margin: 0; }
.sxl-dl dt{
  font-weight: 700;
  margin-top: .85rem;
}
.sxl-dl dt:first-child{ margin-top: 0; }
.sxl-dl dd{
  margin: .25rem 0 0 0;
  padding-left: 0;
}

/* Simple section divider */
.sxl-divider{
  margin: 2.2rem 0 1.2rem 0;
  border-top: 1px solid var(--md-default-fg-color--lightest);
}
</style>

<div class="sxl-wrap" markdown>

# Neurophysiological experiments

On this page you can find summaries of the Sensorium-XL neurophysiological dataset used to train and evaluate OmniMouse, including sources, experimental modalities, and key recording characteristics. For details on individual experiment sessions, see [Dataset Details](dataset_details.md).

All experiments were conducted in awake, head-fixed mice and approved by the Institutional Animal Care and Use Committee of Baylor College of Medicine.

<div class="sxl-card">
  <div class="sxl-card__head"><h2>Sensorium-XL</h2></div>
  <div class="sxl-card__body" markdown>
  Sensorium-XL combines newly recorded data with prior recordings from other projects (sub-datasets listed below).

  <dl class="sxl-dl">
    <dt>Source</dt>
    <dd>Willeke et al., 2026 (OmniMouse)</dd>

    <dt>Animals / recordings</dt>
    <dd>78 unique mice overall (some appear in both training and evaluation), with 4,210–11,284 neurons per session and &gt;3 million single-unit recordings in total.</dd>

    <dt>Neural data</dt>
    <dd>Wide-field two-photon calcium imaging of excitatory neurons in layers 2–5 of right V1.</dd>

    <dt>Stimuli</dt>
    <dd>Naturalistic images (ImageNet) and videos (cinematic movies + Sports-1M), plus parametric and synthetic stimuli (e.g., static/drifting Gabors, directional pink noise, flashing Gaussian dots, random dot kinematograms, model-generated stimuli). Presented at 30–60 Hz; images shown for 500 ms with 300–500 ms blank intervals.</dd>

    <dt>Behavior</dt>
    <dd>Five aligned variables (locomotion speed, pupil size, pupil-size change, horizontal eye position, vertical eye position).</dd>
  </dl>
  </div>
</div>

<div class="sxl-divider"></div>

<div class="sxl-card">
  <div class="sxl-card__head"><h2>Sensorium 2022</h2></div>
  <div class="sxl-card__body" markdown>
  <dl class="sxl-dl">
    <dt>Source</dt>
    <dd>Willeke et al., 2022 (Sensorium 2022 competition)</dd>

    <dt>Animals / recordings</dt>
    <dd>7 behaving mice (7 recording sessions). Five “pretraining” recordings are released for training/generalization; two “competition” recordings are reserved for held-out evaluation (withheld responses for live and final test scoring).</dd>

    <dt>Stimuli</dt>
    <dd>Natural images sampled from ImageNet, converted to grayscale; presented for 500 ms with 300–500 ms blank intervals.</dd>

    <dt>Neural data</dt>
    <dd>Two-photon calcium imaging of excitatory neurons in layer 2/3 of right V1; responses aggregated 50–550 ms after stimulus onset (boxcar window).</dd>

    <dt>Behavior</dt>
    <dd>Five aligned variables (locomotion speed, pupil size, pupil-size change, horizontal eye position, vertical eye position).</dd>
  </dl>
  </div>
</div>

<div class="sxl-card">
  <div class="sxl-card__head"><h2>Sensorium 2023</h2></div>
  <div class="sxl-card__body" markdown>
  <dl class="sxl-dl">
    <dt>Source</dt>
    <dd>Turishcheva et al., 2024 (Sensorium 2023 competition)</dd>

    <dt>Animals / recordings</dt>
    <dd>10 behaving mice (10 recording sessions). Five recordings are released fully as pretraining data; five additional recordings are used for held-out competition evaluation (live/final test responses withheld).</dd>

    <dt>Stimuli</dt>
    <dd>Grayscale dynamic natural movies (cinematic clips + Sports-1M) presented at 30 Hz (~8–11 s clips), plus out-of-domain stimuli (ImageNet images, flashing Gaussian dots, random dot kinematograms, directional pink noise, drifting Gabors). For precise presentation details, see the whitepaper’s <em>Materials and Methods</em> section.</dd>

    <dt>Neural data</dt>
    <dd>Wide-field two-photon calcium imaging of excitatory neurons in layers 2–5 of right V1.</dd>

    <dt>Behavior</dt>
    <dd>Four aligned behavioral variables (locomotion speed, pupil size, horizontal pupil position, vertical pupil position).</dd>
  </dl>
  </div>
</div>

<div class="sxl-card">
  <div class="sxl-card__head"><h2>Paul’s paper (TBA)</h2></div>
  <div class="sxl-card__body" markdown>
  <dl class="sxl-dl">
    <dt>Source</dt>
    <dd>TBA</dd>

    <dt>Animals / recordings</dt>
    <dd>16 behaving mice (16 recording sessions). Eleven “pretraining” recordings are released for training/generalization; five recordings are reserved for held-out evaluation.</dd>

    <dt>Stimuli</dt>
    <dd>TBA</dd>

    <dt>Neural data</dt>
    <dd>Wide-field two-photon calcium imaging of excitatory neurons in layers 2–5 of right V1.</dd>

    <dt>Behavior</dt>
    <dd>Four aligned behavioral variables (locomotion speed, pupil size, horizontal pupil position, vertical pupil position).</dd>
  </dl>
  </div>
</div>

</div>