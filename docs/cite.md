---
hide:
  - navigation
  - toc
  - footer
---

The **Enigma-Mouse Dataset** builds on experimental data obtained from multiple projects and original sources. When using the Enigma-Mouse Dataset for scientific purposes, please cite:

<ol style="margin-top: .4rem;">
  <li><strong>the original data source(s)</strong> your results depend on and the corresponding paper,</li>
  <li>and, if possible, the Enigma-Mouse dataset repository/homepage.</li>
</ol>

You can find the corresponding paper for each individual experiment in the [__Dataset Details__](dataset_details.md) section. This ensures proper credit to the experimental labs and researchers, and improves reproducibility.

<style>
.cite-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1rem;
  margin-top: 1.2rem;
}

.cite-button {
  display: block;
  width: 100%;
  padding: 1rem;
  text-align: left;
  border: 1px solid var(--md-default-fg-color--lightest);
  border-radius: 14px;
  background: var(--md-default-bg-color);
  color: var(--md-default-fg-color);
  font-weight: 700;
  cursor: pointer;
  box-shadow: 0 1px 0 rgba(0,0,0,.04);
  transition: background 0.15s ease, transform 0.15s ease;
}

.cite-button:hover {
  background: color-mix(in srgb, var(--md-default-bg-color) 92%, var(--md-accent-fg-color) 8%);
  transform: translateY(-1px);
}

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
  font-size: 0.85rem;
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

.cite-note {
  margin-top: 1rem;
  color: var(--md-default-fg-color--light);
  font-size: 0.92rem;
}
</style>

<div class="cite-grid">
  <button class="cite-button" onclick="document.getElementById('cite-sxl').showModal()">Enigma-Mouse</button>
  <button class="cite-button" onclick="document.getElementById('cite-om').showModal()">OmniMouse</button>
  <button class="cite-button" onclick="document.getElementById('cite-s22').showModal()">Sensorium 2022</button>
  <button class="cite-button" onclick="document.getElementById('cite-s23').showModal()">Sensorium 2023</button>
  <button class="cite-button" onclick="document.getElementById('cite-foundation').showModal()">Foundation model paper</button>
</div>

<p class="cite-note">
Click a box to open the BibTeX citation.
</p>

<dialog id="cite-sxl" class="cite-dialog">
  <div class="cite-dialog-head">
    <strong>Enigma-Mouse</strong>
    <div class="cite-dialog-actions">
      <button class="cite-copy" onclick="copyBibtex('bibtex-sxl', this)">Copy</button>
      <button class="cite-close" onclick="document.getElementById('cite-sxl').close()">Close</button>
    </div>
  </div>
  <div class="cite-dialog-body">
    <p>Main dataset DOI.</p>
    <pre><code id="bibtex-doi">
    TBA
    </code></pre>
  </div>
</dialog>

<dialog id="cite-om" class="cite-dialog">
  <div class="cite-dialog-head">
    <strong>OmniMouse</strong>
    <div class="cite-dialog-actions">
      <button class="cite-copy" onclick="copyBibtex('bibtex-om', this)">Copy</button>
      <button class="cite-close" onclick="document.getElementById('cite-om').close()">Close</button>
    </div>
  </div>
  <div class="cite-dialog-body">
    <p>Original source for the novel OmniMouse subset</p>
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
      url={https://arxiv.org/abs/2206.08666}, 
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
      url={https://arxiv.org/abs/2305.19654}, 
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
  author  = {Wang, E.Y., Fahey, P.G., Ding, Z. et al. },
  journal = {Nature},
  year    = {2025},
  doi     = {https://doi.org/10.1038/s41586-025-08829-y}
}</code></pre>
  </div>
</dialog>

<script>
async function copyBibtex(codeId, button) {
  const codeEl = document.getElementById(codeId);
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