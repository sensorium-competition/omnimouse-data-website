---
hide:
  - navigation
  - toc
  - footer
---
<style>
#metadata-container { 
    font-family: var(--md-typeset-font-family, sans-serif); 
    margin-top: 20px;
    color: var(--md-sys-color-on-surface);
}

.box-styled {
    background-color: var(--md-sys-color-surface-container-high);
    border: 1px solid var(--md-sys-color-outline-variant);
    border-radius: 12px;
    padding: 10px 18px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    transition: all 0.2s ease-in-out;
}

.search-controls { 
    display: flex; 
    gap: 10px; 
    flex-wrap: wrap;
    align-items: center;
}

#query { 
    flex-grow: 1; 
    min-width: 200px; 
    color: var(--md-sys-color-on-surface);
    background-color: var(--md-sys-color-surface-container-lowest);
    outline: none;
}

#query:focus {
    border-color: var(--md-sys-color-primary);
    background-color: var(--md-sys-color-surface-container-high);
}

.btn { 
    cursor: pointer;
    font-weight: 500; 
    font-size: 14px;
    color: var(--md-sys-color-on-surface-variant);
    background-color: var(--md-sys-color-surface-variant);
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    justify-content: center;
}

.btn-search { 
    background-color: var(--md-sys-color-secondary-container);
    color: var(--md-sys-color-on-secondary-container);
    border-color: var(--md-sys-color-outline);
}

.btn:hover { 
    background-color: var(--md-sys-color-surface-container-highest);
    transform: translateY(-1px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.15);
}

.status-msg { 
    margin: 12px 4px;
    font-size: 13px;
    opacity: 0.8;
}

#table-wrapper {
    margin-top: 24px;
    overflow: hidden;
    display: none;
    padding: 0;
    text-align: center;
}

#result-table {
    display: inline-table;
    border-collapse: collapse;
    text-align: left;
}

#result-table th { 
    background-color: var(--md-sys-color-surface-variant);
    color: var(--md-sys-color-on-surface-variant);
    padding: 14px;
    text-align: left;
    font-size: 13px;
    font-weight: 600;
    border-bottom: 1px solid var(--md-sys-color-outline-variant);
}

#result-table td { 
    padding: 14px;
    border-bottom: 1px solid var(--md-sys-color-outline-variant);
}

#result-table tr:last-child td { border-bottom: none; }

#result-table td a {
    color: var(--md-accent-fg-color, #2094f3);
    text-decoration: none;
    font-weight: 600;
}

#result-table td a:hover {
    text-decoration: underline;
}

.box-styled{
  box-shadow:
    0 8px 20px rgba(0,0,0,.14),
    0 2px 6px rgba(0,0,0,.10),
    inset 0 1px 0 rgba(255,255,255,.06);
}

[data-md-color-scheme="default"] .box-styled{
  box-shadow:
    0 10px 22px rgba(0,0,0,.12),
    0 3px 8px rgba(0,0,0,.08),
    inset 0 1px 0 rgba(255,255,255,.30);
  border-color: color-mix(in srgb, var(--md-sys-color-outline-variant) 78%, #000 22%);
}

[data-md-color-scheme="slate"] .box-styled{
  box-shadow:
    0 22px 54px rgba(0,0,0,.62),
    0 7px 16px rgba(0,0,0,.38),
    0 0 0 1px rgba(255,255,255,.08),
    inset 0 1px 0 rgba(255,255,255,.12);
  border-color: color-mix(in srgb, var(--md-sys-color-outline-variant) 55%, #fff 45%);
}

[data-md-color-scheme="default"] .btn:hover{
  box-shadow:
    0 14px 30px rgba(0,0,0,.14),
    0 4px 10px rgba(0,0,0,.10);
}

[data-md-color-scheme="slate"] .btn:hover{
  box-shadow:
    0 26px 64px rgba(0,0,0,.70),
    0 10px 22px rgba(0,0,0,.45);
}

#table-wrapper.box-styled{
  box-shadow:
    0 12px 28px rgba(0,0,0,.14),
    0 4px 10px rgba(0,0,0,.10),
    inset 0 1px 0 rgba(255,255,255,.06);
}

[data-md-color-scheme="slate"] #table-wrapper.box-styled{
  box-shadow:
    0 26px 66px rgba(0,0,0,.72),
    0 10px 22px rgba(0,0,0,.45),
    0 0 0 1px rgba(255,255,255,.08),
    inset 0 1px 0 rgba(255,255,255,.12);
}

/* Filter dialog */
.filter-dialog {
  border: none;
  border-radius: 18px;
  padding: 0;
  width: min(960px, 94vw);
  height: min(86vh, 920px);
  max-height: 86vh;
  overflow: hidden;
  background: var(--md-default-bg-color, var(--md-sys-color-surface));
  color: var(--md-default-fg-color, var(--md-sys-color-on-surface));
  box-shadow: 0 18px 48px rgba(0,0,0,.22);
}

.filter-dialog[open] {
  display: grid;
  grid-template-rows: auto minmax(0, 1fr) auto;
}

.filter-dialog::backdrop {
  background: rgba(0,0,0,.45);
}

.filter-dialog-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  padding: 1.1rem 1.25rem 0.9rem 1.25rem;
  border-bottom: 1px solid var(--md-sys-color-outline-variant);
}

.filter-dialog-body {
  padding: 1.1rem 1.25rem;
  overflow-y: auto;
  overflow-x: hidden;
  min-height: 0;
  overscroll-behavior: contain;
}

.filter-dialog-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  flex-wrap: wrap;
  padding: 0.95rem 1.25rem 1.1rem 1.25rem;
  border-top: 1px solid var(--md-sys-color-outline-variant);
  background: var(--md-default-bg-color, var(--md-sys-color-surface));
}

.filter-footer-actions {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
}

.filter-close {
  border: 1px solid var(--md-sys-color-outline-variant);
  background: var(--md-sys-color-surface-container-high);
  color: var(--md-sys-color-on-surface);
  border-radius: 10px;
  padding: 0.4rem 0.7rem;
  cursor: pointer;
  font: inherit;
}

.filter-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 16px;
  align-items: start;
}

.filter-group {
  border: 1px solid var(--md-sys-color-outline-variant);
  border-radius: 12px;
  padding: 14px;
  background: var(--md-sys-color-surface-container-lowest);

  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  height: 300px;
  min-height: 300px;
  overflow: hidden;
}

.filter-group h4 {
  margin: 0 0 .75rem 0;
  font-size: 14px;
  flex: 0 0 auto;
}

.filter-options {
  display: flex;
  flex-direction: column;
  gap: 6px;
  flex: 1 1 auto;
  min-height: 0;
  height: 100%;
  overflow-y: auto;
  overflow-x: hidden;
  overscroll-behavior: contain;
  font-size: 13px;
  padding-right: 4px;
}

.filter-options label {
  display: flex;
  align-items: flex-start;
  gap: 8px;
}

.filter-actions {
  display: none;
}

.filter-count {
  font-size: 13px;
  opacity: .8;
}

.filter-mode {
  display: flex;
  flex-direction: column;
  gap: 6px;
  margin-bottom: 10px;
  padding-bottom: 10px;
  border-bottom: 1px solid var(--md-sys-color-outline-variant);
  font-size: 12px;
  flex: 0 0 auto;
}

.filter-mode label {
  display: flex;
  gap: 6px;
  align-items: center;
}

@media (max-width: 700px) {
  .filter-dialog {
    width: min(96vw, 960px);
    height: min(88vh, 920px);
    max-height: 88vh;
  }

  .filter-dialog-head,
  .filter-dialog-body,
  .filter-dialog-footer {
    padding-left: 1rem;
    padding-right: 1rem;
  }

  .filter-dialog-footer {
    align-items: stretch;
  }

  .filter-footer-actions {
    width: 100%;
  }

  .filter-footer-actions .btn {
    flex: 1 1 auto;
  }

  .filter-count {
    width: 100%;
  }

  .filter-group {
    height: 260px;
    min-height: 260px;
  }
}

html.filter-open,
body.filter-open {
  overflow: hidden !important;
}
</style>

<div id="metadata-container">
    <div class="search-controls">
        <input type="text" id="query" class="box-styled" placeholder="Enter Experiment ID..." onkeypress="if(event.key==='Enter') searchMetadata()">
        
        <button class="btn btn-search box-styled" onclick="searchMetadata()">Search</button>
        <button class="btn btn-all box-styled" onclick="showAllMetadata()">View All</button>
        <button class="btn btn-clear box-styled" onclick="clearResults()">Clear</button>
        <button id="filter-btn" class="btn box-styled" onclick="openFilterDialog()" disabled>Filters</button>

        <a id="download-meta"
           class="btn box-styled"
           href="#"
           download="cleaned_full_combined_meta.json"
           aria-disabled="true"
           style="pointer-events:none; opacity:.6;">
           Download metadata JSON
        </a>
    </div>

    <div id="status" class="status-msg">Loading metadata...</div>

    <div id="table-wrapper" class="box-styled">
        <table id="result-table">
            <thead id="table-head"></thead>
            <tbody id="table-body"></tbody>
        </table>
    </div>
</div>

<dialog id="filter-dialog" class="filter-dialog">
  <div class="filter-dialog-head">
    <strong>Filter metadata</strong>
    <button class="filter-close" onclick="closeFilterDialog()">Close</button>
  </div>

  <div class="filter-dialog-body">
    <div id="filter-container" class="filter-grid"></div>
  </div>

  <div class="filter-dialog-footer">
    <div class="filter-footer-actions">
      <button class="btn box-styled" onclick="applyFilters()">Apply filters</button>
      <button class="btn box-styled" onclick="resetFilters()">Reset filters</button>
    </div>
    <span id="filter-summary" class="filter-count"></span>
  </div>
</dialog>

<script>
let metadata = {};
let animalSourceLookup = {};
let filterConfig = {};
let activeFilters = {};
let filterModes = {
    modalities: "inclusive"
};

const baseURL = window.location.origin + window.location.pathname.replace(/\/[^\/]*\/?$/, '');
const meta_path = `${baseURL}/experiment_metadata/cleaned_full_combined_meta.json`;
const animal_source_path = `${baseURL}/experiment_metadata/cite.json`;

const FILTER_FIELDS = {
  animal_id:      { path: ["scan_key", "animal_id"] },
  session:        { path: ["scan_key", "session"] },
  scan_idx:       { path: ["scan_key", "scan_idx"] },
  genotype:       { path: ["scan_key", "genotype"] },
  sex:            { path: ["scan_key", "sex"] },
  modalities:     { path: ["screen", "modalities"] },
  introduced_in:  { derived: "introduced_in" }
};

Promise.all([
  fetch(meta_path).then(response => {
    if (!response.ok) throw new Error('Metadata file not found');
    return response.json();
  }),
  fetch(animal_source_path).then(response => {
    if (!response.ok) throw new Error('Animal source lookup file not found');
    return response.json();
  })
])
.then(([metaData, sourceData]) => {
    metadata = metaData || {};
    animalSourceLookup = sourceData || {};

    document.getElementById('status').textContent = "Database synced successfully.";

    const dl = document.getElementById('download-meta');
    dl.href = meta_path;
    dl.style.pointerEvents = "auto";
    dl.style.opacity = "1";
    dl.removeAttribute("aria-disabled");

    buildFilterConfig();
    document.getElementById('filter-btn').disabled = false;

    showAllMetadata();
})
.catch(err => {
    document.getElementById('status').textContent = "⚠️ Error: Metadata file not found.";
});

function getFieldValue(obj, pathOrConfig) {
    if (pathOrConfig?.derived === "introduced_in") {
        const lookupKey = getExperimentLookupKey(obj);
        if (!lookupKey || !animalSourceLookup?.[lookupKey]) return null;

        const entry = animalSourceLookup[lookupKey];

        if (typeof entry === "string") return entry;

        if (Array.isArray(entry)) {
            const firstValid = entry.flat().find(
                item => item && typeof item === "object" && !Array.isArray(item)
            );
            return firstValid?.label ?? firstValid?.name ?? null;
        }

        if (entry && typeof entry === "object") {
            return entry.label ?? entry.name ?? null;
        }

        return null;
    }
}

function normalizeValue(val) {
    if (val === null || val === undefined) return null;

    if (Array.isArray(val)) {
        const cleaned = val
            .map(v => normalizeValue(v))
            .filter(v => v !== null);
        return cleaned.length ? cleaned : null;
    }

    const str = String(val).trim();
    return str === "" ? null : str;
}

function buildFilterConfig() {
    filterConfig = {};

    for (const [field, cfg] of Object.entries(FILTER_FIELDS)) {
        const values = new Set();

        for (const exp of Object.values(metadata)) {
            const raw = getFieldValue(exp, cfg);
            const normalized = normalizeValue(raw);

            if (normalized === null) continue;

            if (Array.isArray(normalized)) {
                normalized.forEach(v => values.add(v));
            } else {
                values.add(normalized);
            }
        }

        const sorted = Array.from(values).sort((a, b) =>
            a.localeCompare(b, undefined, { numeric: true, sensitivity: "base" })
        );

        if (sorted.length > 0) {
            filterConfig[field] = sorted;
        }
    }

    renderFilterUI();
}

function renderFilterUI() {
    const container = document.getElementById('filter-container');
    let html = "";

    for (const [field, values] of Object.entries(filterConfig)) {
        html += `<div class="filter-group">`;
        html += `<h4>${field}</h4>`;

        if (field === "modalities") {
            const mode = filterModes.modalities ?? "inclusive";
            html += `
              <div class="filter-mode">
                <label>
                  <input type="radio" name="modalities-mode" value="inclusive" ${mode === "inclusive" ? "checked" : ""}>
                  includes any selected
                </label>
                <label>
                  <input type="radio" name="modalities-mode" value="exclusive" ${mode === "exclusive" ? "checked" : ""}>
                  exact set only
                </label>
              </div>
            `;
        }

        html += `<div class="filter-options">`;

        values.forEach(value => {
            const checked = activeFilters[field]?.has(value) ? "checked" : "";
            const safeId = `filter-${field}-${String(value).replace(/[^a-zA-Z0-9_-]/g, "_")}`;
            html += `
              <label for="${safeId}">
                <input type="checkbox" id="${safeId}" data-field="${field}" value="${escapeHtml(value)}" ${checked}>
                ${escapeHtml(value)}
              </label>
            `;
        });

        html += `</div></div>`;
    }

    container.innerHTML = html;
    updateFilterSummary();
}

function openFilterDialog() {
    renderFilterUI();
    document.documentElement.classList.add("filter-open");
    document.body.classList.add("filter-open");
    document.getElementById('filter-dialog').showModal();
}

function closeFilterDialog() {
    document.documentElement.classList.remove("filter-open");
    document.body.classList.remove("filter-open");
    document.getElementById('filter-dialog').close();
}

document.getElementById('filter-dialog').addEventListener('close', () => {
    document.documentElement.classList.remove("filter-open");
    document.body.classList.remove("filter-open");
});

function applyFilters() {
    activeFilters = {};

    const modalityModeInput = document.querySelector('input[name="modalities-mode"]:checked');
    if (modalityModeInput) {
        filterModes.modalities = modalityModeInput.value;
    }

    const inputs = document.querySelectorAll('#filter-container input[type="checkbox"]:checked');

    inputs.forEach(input => {
        const field = input.dataset.field;
        const value = input.value;
        if (!activeFilters[field]) activeFilters[field] = new Set();
        activeFilters[field].add(value);
    });

    closeFilterDialog();
    renderDynamicTable(getFilteredMetadata());
}

function resetFilters() {
    activeFilters = {};
    filterModes.modalities = "inclusive";
    renderFilterUI();
    renderDynamicTable(metadata);
}

function setsAreEqual(a, b) {
    if (a.size !== b.size) return false;
    for (const item of a) {
        if (!b.has(item)) return false;
    }
    return true;
}

function getExperimentLookupKey(obj) {
    const animal = obj?.scan_key?.animal_id;
    const session = obj?.scan_key?.session;
    const scanIdx = obj?.scan_key?.scan_idx;

    if (animal == null || session == null || scanIdx == null) return null;
    return `${animal}_${session}_${scanIdx}`;
}

function experimentMatchesFilters(expData) {
    for (const [field, selectedValues] of Object.entries(activeFilters)) {
        if (!selectedValues || selectedValues.size === 0) continue;

        const cfg = FILTER_FIELDS[field];
        const raw = getFieldValue(expData, cfg);
        const normalized = normalizeValue(raw);

        if (field === "modalities") {
            if (normalized === null) return false;

            const experimentValues = Array.isArray(normalized) ? new Set(normalized) : new Set([normalized]);

            if ((filterModes.modalities ?? "inclusive") === "exclusive") {
                if (!setsAreEqual(experimentValues, selectedValues)) return false;
            } else {
                let anyMatch = false;
                for (const value of selectedValues) {
                    if (experimentValues.has(value)) {
                        anyMatch = true;
                        break;
                    }
                }
                if (!anyMatch) return false;
            }

            continue;
        }

        let match = false;

        if (Array.isArray(normalized)) {
            match = normalized.some(v => selectedValues.has(v));
        } else if (normalized !== null) {
            match = selectedValues.has(normalized);
        }

        if (!match) return false;
    }
    return true;
}

function getFilteredMetadata() {
    const filtered = {};
    for (const [id, expData] of Object.entries(metadata)) {
        if (experimentMatchesFilters(expData)) {
            filtered[id] = expData;
        }
    }
    return filtered;
}

function updateFilterSummary() {
    const parts = [];
    for (const [field, values] of Object.entries(activeFilters)) {
        if (values && values.size > 0) {
            if (field === "modalities") {
                parts.push(`${field} (${filterModes.modalities}): ${values.size}`);
            } else {
                parts.push(`${field}: ${values.size}`);
            }
        }
    }
    document.getElementById('filter-summary').textContent =
        parts.length ? `Active filters — ${parts.join(" | ")}` : "No active filters";
}

function renderDynamicTable(dataObj) {
    const wrapper = document.getElementById('table-wrapper');
    const head = document.getElementById('table-head');
    const body = document.getElementById('table-body');
    const status = document.getElementById('status');
    
    const keys = Object.keys(dataObj);

    if (keys.length === 0) {
        wrapper.style.display = "none";
        status.textContent = "No matches found.";
        updateFilterSummary();
        return;
    }

    const importantFields = ["animal_id", "session", "scan_idx", "introduced in"];

    let headHtml = `<tr><th>Experiment ID (click for details)</th>`;
    importantFields.forEach(field => { headHtml += `<th>${field}</th>`; });
    headHtml += `</tr>`;
    head.innerHTML = headHtml;

    let bodyHtml = "";
    keys.forEach(id => {
        const expData = dataObj[id] || {};
        const scan = expData.scan_key || {};

        const animal = scan.animal_id ?? "-";
        const session = scan.session ?? "-";
        const scanIdx = scan.scan_idx ?? "-";

        let sourceCell = "-";
        const lookupKey = getExperimentLookupKey(expData);

        if (lookupKey && animalSourceLookup && animalSourceLookup[lookupKey]) {
            const entry = animalSourceLookup[lookupKey];

            if (typeof entry === "string") {
                sourceCell = entry;
            } else {
                let chosenEntry = entry;

                if (Array.isArray(entry)) {
                    chosenEntry = entry.flat().find(
                        item => item && typeof item === "object" && !Array.isArray(item)
                    );
                }

                if (chosenEntry && typeof chosenEntry === "object") {
                    const label = chosenEntry.label ?? chosenEntry.name ?? "introduced in";

                    let url = "#";
                    if (chosenEntry.url) {
                        url = chosenEntry.url;
                    } else if (chosenEntry.anchor) {
                        url = `${baseURL}/subsets_and_references/#${chosenEntry.anchor}`;
                    } else {
                        url = `${baseURL}/subsets_and_references/`;
                    }

                    sourceCell = `<a href="${url}">${label}</a>`;
                }
            }
        }

        const encodedId = encodeURIComponent(id);
        bodyHtml += `<tr>`;
        bodyHtml += `<td><a href="../experiment/?id=${encodedId}"><strong>${id}</strong></a></td>`;
        bodyHtml += `<td>${animal}</td>`;
        bodyHtml += `<td>${session}</td>`;
        bodyHtml += `<td>${scanIdx}</td>`;
        bodyHtml += `<td>${sourceCell}</td>`;
        bodyHtml += `</tr>`;
    });

    body.innerHTML = bodyHtml;
    wrapper.style.display = "block";

    const activeCount = Object.values(activeFilters).reduce((n, s) => n + (s?.size || 0), 0);
    status.textContent = activeCount > 0
        ? `Showing ${keys.length} filtered result(s).`
        : `Showing ${keys.length} result(s).`;

    updateFilterSummary();
}

function searchMetadata() {
    let q = document.getElementById('query').value.trim();
    if (!q) {
        renderDynamicTable(getFilteredMetadata());
        return;
    }
    q = q.padStart(3, '0');
    const filtered = getFilteredMetadata();
    const result = filtered[q];
    renderDynamicTable(result ? { [q]: result } : {});
}

function showAllMetadata() {
    renderDynamicTable(getFilteredMetadata());
}

function clearResults() {
    document.getElementById('query').value = "";
    activeFilters = {};
    filterModes.modalities = "inclusive";
    document.getElementById('table-wrapper').style.display = "none";
    document.getElementById('status').textContent = "Database synced successfully.";
    updateFilterSummary();
}

function escapeHtml(str) {
    return String(str)
      .replaceAll("&", "&amp;")
      .replaceAll("<", "&lt;")
      .replaceAll(">", "&gt;")
      .replaceAll('"', "&quot;")
      .replaceAll("'", "&#39;");
}
</script>