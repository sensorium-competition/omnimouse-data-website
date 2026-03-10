---
hide:
  - navigation
---

<style>
/* Layout */
.om-wrap { max-width: 980px; margin: 0 auto; }

/* Cards */
.om-card{
  margin: 0 0 1.8rem 0;
  border-radius: 16px;
  border: 1px solid var(--md-default-fg-color--lightest);
  background: var(--md-default-bg-color);
  box-shadow: 0 1px 0 rgba(0,0,0,.04);
  overflow: hidden;
}

/* Card header */
.om-card__head{
  padding: .95rem 1.15rem;
  border-bottom: 1px solid var(--md-default-fg-color--lightest);
  background: color-mix(in srgb, var(--md-default-bg-color) 92%, var(--md-accent-fg-color) 8%);
}
.om-card__head h2{
  margin: 0;
  font-size: 1.05rem;
  line-height: 1.25;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: .55rem;
  flex-wrap: wrap;
}

/* Small BibTeX link in header */
.bibtex-link{
  display: inline-block;
  font-size: .8rem;
  font-weight: 600;
  text-decoration: none;
  padding: .18rem .5rem;
  border-radius: 999px;
  border: 1px solid var(--md-default-fg-color--lightest);
  background: var(--md-default-bg-color);
  color: var(--md-accent-fg-color);
  white-space: nowrap;
}
.bibtex-link:hover{
  text-decoration: none;
  background: color-mix(in srgb, var(--md-default-bg-color) 90%, var(--md-accent-fg-color) 10%);
}

/* Card body */
.om-card__body{ padding: 1.05rem 1.25rem 1.15rem 1.25rem; }
.om-card__body > p{ margin: 0 0 .9rem 0; color: var(--md-default-fg-color--light); }

/* Definition list formatting */
.om-dl { margin: 0; }
.om-dl dt{
  font-weight: 700;
  margin-top: .85rem;
}
.om-dl dt:first-child{ margin-top: 0; }
.om-dl dd{
  margin: .25rem 0 0 0;
  padding-left: 0;
}

/* DOI links */
.om-doi{
  word-break: break-word;
}
.om-doi a{
  text-decoration: none;
}
.om-doi a:hover{
  text-decoration: underline;
}

/* Simple section divider */
.om-divider{
  margin: 2.2rem 0 1.2rem 0;
  border-top: 1px solid var(--md-default-fg-color--lightest);
}

/* Dialog popup styling */
.cite-dialog {
  border: none;
  border-radius: 16px;
  padding: 0;
  max-width: 760px;
  width: min(760px, 92vw);
  background: var(--md-default-bg-color);
  color: var(--md-default-fg-color);
  box-shadow: 0 18px 48px rgba(0,0,0,.22);
}

.cite-dialog::backdrop {
  background: rgba(0, 0, 0, 0.45);
}

.cite-dialog-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  padding: 1rem 1rem 0.75rem 1rem;
  border-bottom: 1px solid var(--md-default-fg-color--lightest);
}

.cite-dialog-actions {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.cite-dialog-body {
  padding: 1rem 1rem 1.1rem 1rem;
}

.cite-close,
.cite-copy {
  border: 1px solid var(--md-default-fg-color--lightest);
  background: var(--md-default-bg-color);
  color: var(--md-default-fg-color);
  border-radius: 10px;
  padding: 0.4rem 0.7rem;
  cursor: pointer;
  font: inherit;
}

.cite-close:hover,
.cite-copy:hover {
  background: color-mix(in srgb, var(--md-default-bg-color) 92%, var(--md-accent-fg-color) 8%);
}

.cite-dialog p {
  margin-top: 0;
  color: var(--md-default-fg-color--light);
}

.cite-dialog pre {
  margin: 0;
  padding: 0.9rem;
  border-radius: 10px;
  overflow-x: auto;
  font-size: 0.82rem;
  line-height: 1.45;
  background: var(--md-code-bg-color, rgba(127,127,127,.08));
  border: 1px solid var(--md-default-fg-color--lightest);
}

.toc-heading {
  position: absolute;
  left: -9999px;
  height: 0;
  margin: 0;
  overflow: hidden;
}
</style>

<div class="om-wrap" markdown>

# Subsets and references

On this page you can find summaries of the Sensorium-XL neurophysiological dataset used to train and evaluate OmniMouse, including sources, experimental modalities, and key recording characteristics. For details on individual experiment sessions, see [Dataset Details](dataset_details.md).

All experiments were conducted in awake, head-fixed mice and approved by the Institutional Animal Care and Use Committee of Baylor College of Medicine.

## Sensorium-XL { .toc-heading }

<div class="om-card">
  <div class="om-card__head">
    <h2>
      Sensorium-XL
      <a href="#" class="bibtex-link" onclick="document.getElementById('cite-om').showModal(); return false;">BibTeX</a>
    </h2>
  </div>
  <div class="om-card__body" markdown>
  Sensorium-XL combines newly recorded data with prior recordings from other projects (sub-datasets listed below). It was introduced in the OmniMouse paper by Willeke et al. in 2026 and is published here as the Sensorium-XL dataset with it's own DOI.

  <dl class="om-dl">
    <dt>Source</dt>
    <dd>Willeke et al., 2026 (OmniMouse)</dd>

    <dt>DOI Sensorium-XL dataset</dt>
    <dd class="om-doi">TBA</dd>

    <dt>DOI OmniMouse paper</dt>
    <dd class="om-doi">TBA</dd>

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

<div class="om-divider"></div>

## Sensorium-2022 { .toc-heading }

<div class="om-card">
  <div class="om-card__head">
    <h2>
      Sensorium 2022
      <a href="#" class="bibtex-link" onclick="document.getElementById('cite-s22').showModal(); return false;">BibTeX</a>
    </h2>
  </div>
  <div class="om-card__body" markdown>
  <dl class="om-dl">
    <dt>Source</dt>
    <dd>Willeke et al., 2022 (Sensorium 2022 competition)</dd>

    <dt>DOI</dt>
    <dd class="om-doi"><a href="https://doi.org/10.48550/arXiv.2206.08666">10.48550/arXiv.2206.08666</a></dd>

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

## Sensorium-2023 { .toc-heading }

<div class="om-card">
  <div class="om-card__head">
    <h2>
      Sensorium 2023
      <a href="#" class="bibtex-link" onclick="document.getElementById('cite-s23').showModal(); return false;">BibTeX</a>
    </h2>
  </div>
  <div class="om-card__body" markdown>
  <dl class="om-dl">
    <dt>Source</dt>
    <dd>Turishcheva et al., 2024 (Sensorium 2023 competition)</dd>

    <dt>DOI</dt>
    <dd class="om-doi"><a href="https://doi.org/10.48550/arXiv.2305.19654">10.48550/arXiv.2305.19654</a></dd>

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

## Foundation model of neural activity predicts response to new stimulus types { .toc-heading }

<div class="om-card">
  <div class="om-card__head">
    <h2>
      Foundation model of neural activity predicts response to new stimulus types
      <a href="#" class="bibtex-link" onclick="document.getElementById('cite-foundation').showModal(); return false;">BibTeX</a>
    </h2>
  </div>
  <div class="om-card__body" markdown>
  <dl class="om-dl">
    <dt>Source</dt>
    <dd>Wang et al., 2023 (Foundation model of neural activity predicts response to new stimulus types)</dd>

    <dt>DOI</dt>
    <dd class="om-doi"><a href="https://doi.org/10.1038/s41586-025-08829-y">10.1038/s41586-025-08829-y</a></dd>

    <dt>Animals / recordings</dt>
    <dd>16 behaving mice (16 recording sessions). Eleven “pretraining” recordings are released for training/generalization; five recordings are reserved for held-out evaluation.</dd>

    <dt>Stimuli</dt>
    <dd>Trained on natural videos and tested on held out natural videos as well as out of domain gratings.</dd>

    <dt>Neural data</dt>
    <dd>Wide-field two-photon calcium imaging of excitatory neurons in layers 2–5 of right V1.</dd>

    <dt>Behavior</dt>
    <dd>Four aligned behavioral variables (locomotion speed, pupil size, horizontal pupil position, vertical pupil position).</dd>
  </dl>
  </div>
</div>

</div>

<dialog id="cite-om" class="cite-dialog">
  <div class="cite-dialog-head">
    <strong>OmniMouse</strong>
    <div class="cite-dialog-actions">
      <button class="cite-copy" onclick="copyBibtex('bibtex-om', this)">Copy</button>
      <button class="cite-close" onclick="document.getElementById('cite-om').close()">Close</button>
    </div>
  </div>
  <div class="cite-dialog-body">
    <p>Main dataset citation.</p>
    <pre><code id="bibtex-om">@inproceedings{
      willeke2026omnimouse,
      title={OmniMouse: Scaling properties of multi-modal, multi-task Brain Models on 150B Neural Tokens},
      author={Konstantin Friedrich Willeke and Polina Turishcheva and Alex Gilbert and Goirik Chakrabarty and Hasan Atakan Bedel and Paul G. Fahey and Yongrong Qiu and Marissa A. Weis and Michaela Vystr{\v{c}}ilov{\'a} and Taliah Muhammad and Lydia Ntanavara and Rachel E Froebe and Kayla Ponder and Zheng Huan Tan and Emin Orhan and Erick Cobos and Sophia Sanborn and Katrin Franke and Fabian H. Sinz and Alexander S. Ecker and Andreas S. Tolias},
      booktitle={The Fourteenth International Conference on Learning Representations},
      year={2026},
      url={https://openreview.net/forum?id=mEw4lhAn0F}
}</code></pre>
  </div>
</dialog>

<dialog id="cite-s22" class="cite-dialog">
  <div class="cite-dialog-head">
    <strong>Sensorium 2022</strong>
    <div class="cite-dialog-actions">
      <button class="cite-copy" onclick="copyBibtex('bibtex-s22', this)">Copy</button>
      <button class="cite-close" onclick="document.getElementById('cite-s22').close()">Close</button>
    </div>
  </div>
  <div class="cite-dialog-body">
    <p>Original source citation for the Sensorium 2022 subset.</p>
    <pre><code id="bibtex-s22">@misc{willeke2022sensoriumcompetitionpredictinglargescale,
  title={The Sensorium competition on predicting large-scale mouse primary visual cortex activity},
  author={Konstantin F. Willeke and Paul G. Fahey and Mohammad Bashiri and Laura Pede and Max F. Burg and Christoph Blessing and Santiago A. Cadena and Zhiwei Ding and Konstantin-Klemens Lurz and Kayla Ponder and Taliah Muhammad and Saumil S. Patel and Alexander S. Ecker and Andreas S. Tolias and Fabian H. Sinz},
  year={2022},
  eprint={2206.08666},
  archivePrefix={arXiv},
  primaryClass={q-bio.NC},
  url={https://arxiv.org/abs/2206.08666}
}</code></pre>
  </div>
</dialog>

<dialog id="cite-s23" class="cite-dialog">
  <div class="cite-dialog-head">
    <strong>Sensorium 2023</strong>
    <div class="cite-dialog-actions">
      <button class="cite-copy" onclick="copyBibtex('bibtex-s23', this)">Copy</button>
      <button class="cite-close" onclick="document.getElementById('cite-s23').close()">Close</button>
    </div>
  </div>
  <div class="cite-dialog-body">
    <p>Original source citation for the Sensorium 2023 subset.</p>
    <pre><code id="bibtex-s23">@misc{turishcheva2024dynamicsensoriumcompetitionpredicting,
  title={The Dynamic Sensorium competition for predicting large-scale mouse visual cortex activity from videos},
  author={Polina Turishcheva and Paul G. Fahey and Laura Hansel and Rachel Froebe and Kayla Ponder and Michaela Vystrčilová and Konstantin F. Willeke and Mohammad Bashiri and Eric Wang and Zhiwei Ding and Andreas S. Tolias and Fabian H. Sinz and Alexander S. Ecker},
  year={2024},
  eprint={2305.19654},
  archivePrefix={arXiv},
  primaryClass={q-bio.NC},
  url={https://arxiv.org/abs/2305.19654}
}</code></pre>
  </div>
</dialog>

<dialog id="cite-foundation" class="cite-dialog">
  <div class="cite-dialog-head">
    <strong>Foundation model paper</strong>
    <div class="cite-dialog-actions">
      <button class="cite-copy" onclick="copyBibtex('bibtex-foundation', this)">Copy</button>
      <button class="cite-close" onclick="document.getElementById('cite-foundation').close()">Close</button>
    </div>
  </div>
  <div class="cite-dialog-body">
    <p>Original source citation for this subset.</p>
    <pre><code id="bibtex-foundation">@article{wang2023foundation,
  title   = {Foundation model of neural activity predicts response to new stimulus types},
  author  = {Wang, E.Y. and Fahey, P.G. and Ding, Z. and others},
  journal = {Nature},
  year    = {2025},
  doi     = {10.1038/s41586-025-08829-y}
}</code></pre>
  </div>
</dialog>

<script>
async function copyBibtex(codeId, button) {
  const codeEl = document.getElementById(codeId);
  if (!codeEl) return;

  const text = codeEl.innerText;

  try {
    await navigator.clipboard.writeText(text);
    const original = button.textContent;
    button.textContent = 'Copied';
    setTimeout(() => {
      button.textContent = original;
    }, 1200);
  } catch (err) {
    const original = button.textContent;
    button.textContent = 'Failed';
    setTimeout(() => {
      button.textContent = original;
    }, 1200);
  }
}
</script>