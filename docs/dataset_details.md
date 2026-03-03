---
hide:
  - navigation
  - toc
  - footer
---
<style>
/* Container & Text */
#metadata-container { 
    font-family: var(--md-typeset-font-family, sans-serif); 
    margin-top: 20px;
    color: var(--md-sys-color-on-surface);
}

/* Individual Box styling - Adapts to Theme */
.box-styled {
    background-color: var(--md-sys-color-surface-container-high);
    border: 1px solid var(--md-sys-color-outline-variant);
    border-radius: 12px;
    padding: 10px 18px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    transition: all 0.2s ease-in-out;
}

/* Controls Layout */
.search-controls { 
    display: flex; 
    gap: 10px; 
    flex-wrap: wrap;
    align-items: center;
}

/* Specific Input Styling */
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

/* Muted Button Styling */
.btn { 
    cursor: pointer;
    font-weight: 500; 
    font-size: 14px;
    color: var(--md-sys-color-on-surface-variant);
    background-color: var(--md-sys-color-surface-variant);
}

.btn-search { 
    /* Muted Primary - avoids the "Strong Purple" */
    background-color: var(--md-sys-color-secondary-container);
    color: var(--md-sys-color-on-secondary-container);
    border-color: var(--md-sys-color-outline);
}

.btn:hover { 
    background-color: var(--md-sys-color-surface-container-highest);
    transform: translateY(-1px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.15);
}

/* Status Message */
.status-msg { 
    margin: 12px 4px;
    font-size: 13px;
    opacity: 0.8;
}

/* Table Box Styling */
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

.btn:hover{
  transform: translateY(-1px);
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

</style>

<div id="metadata-container">
    <div class="search-controls">
        <input type="text" id="query" class="box-styled" placeholder="Enter Experiment ID..." onkeypress="if(event.key==='Enter') searchMetadata()">
        
        <button class="btn btn-search box-styled" onclick="searchMetadata()">Search</button>
        <button class="btn btn-all box-styled" onclick="showAllMetadata()">View All</button>
        <button class="btn btn-clear box-styled" onclick="clearResults()">Clear</button>
    </div>

    <div id="status" class="status-msg">Database synced successfully.</div>

    <div id="table-wrapper" class="box-styled">
        <table id="result-table">
            <thead id="table-head"></thead>
            <tbody id="table-body"></tbody>
        </table>
    </div>
</div>

<script>
let metadata = {};
let animalSourceLookup = {};

// Get the base URL of the site (without the current page or subfolder)
const baseURL = window.location.origin + window.location.pathname.replace(/\/[^\/]*\/?$/, '');

// Paths to JSON files
const meta_path = `${baseURL}/experiment_metadata/cleaned_full_combined_meta.json`;
const animal_source_path = `${baseURL}/experiment_metadata/cite.json`;

// Load both JSONs (metadata + animal->source lookup)
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
    showAllMetadata();
  })
  .catch(err => {
    document.getElementById('status').textContent = "⚠️ Error: Metadata file not found.";
  });

function renderDynamicTable(dataObj) {
    const wrapper = document.getElementById('table-wrapper');
    const head = document.getElementById('table-head');
    const body = document.getElementById('table-body');
    const status = document.getElementById('status');
    
    const keys = Object.keys(dataObj);

    if (keys.length === 0) {
        wrapper.style.display = "none";
        status.textContent = "No matches found.";
        return;
    }

    const importantFields = ["animal_id", "session", "scan_idx", "source"];

    // Table header
    let headHtml = `<tr><th>Experiment ID (click for details)</th>`;
    importantFields.forEach(field => { headHtml += `<th>${field}</th>`; });
    headHtml += `</tr>`;
    head.innerHTML = headHtml;

    // Table body
    let bodyHtml = "";
    keys.forEach(id => {
        const expData = dataObj[id] || {};
        const scan = expData.scan_key || {};

        const animal = scan.animal_id ?? "-";
        const session = scan.session ?? "-";
        const scanIdx = scan.scan_idx ?? "-";

        let sourceCell = "-";
        if (animal !== "-" && animalSourceLookup && animalSourceLookup[animal]) {
            const entry = animalSourceLookup[animal];

            // Expected format: {label, url} (also supports string fallback)
            if (typeof entry === "string") {
                sourceCell = entry;
            } else {
                const label = entry.label ?? entry.name ?? "source";
                const url = entry.url ?? "#";
                sourceCell = `<a href="${url}" target="_blank" rel="noopener">${label}</a>`;
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
    status.textContent = `Showing ${keys.length} result(s).`;
}

function searchMetadata() {
    let q = document.getElementById('query').value.trim();
    if (!q) {
        showAllMetadata();
        return;
    }
    q = q.padStart(3,'0');
    const result = metadata[q];
    renderDynamicTable(result ? { [q]: result } : {});
}

function showAllMetadata() { renderDynamicTable(metadata); }

function clearResults() {
    document.getElementById('query').value = "";
    document.getElementById('table-wrapper').style.display = "none";
    document.getElementById('status').textContent = "Database synced successfully.";
}
</script>