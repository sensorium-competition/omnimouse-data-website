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
    padding: 0; /* Ensures the table header hits the edges of the box */
}

#result-table { 
    width: 100%; 
    border-collapse: collapse; 
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
// Get the base URL of the site (without the current page or subfolder)
const baseURL = window.location.origin + window.location.pathname.replace(/\/[^\/]*\/?$/, '');

// Build the path to your JSON
const json_path = `${baseURL}/experiment_metadata/combined_metadata.json`;

fetch(json_path)
  .then(response => {
    if (!response.ok) throw new Error('File not found');
    return response.json();
  })
  .then(data => { 
    metadata = data; 
    document.getElementById('status').textContent = "Database synced successfully.";
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

    const importantFields = ["date", "subject", "status"];  // fields to show

    // Table header
    let headHtml = `<tr><th>Experiment ID</th>`;
    importantFields.forEach(field => { headHtml += `<th>${field}</th>`; });
    headHtml += `<th>Details</th></tr>`;
    head.innerHTML = headHtml;

    // Table body
    let bodyHtml = "";
    keys.forEach(id => {
        const expData = dataObj[id];
        bodyHtml += `<tr><td><strong>${id}</strong></td>`;
        importantFields.forEach(field => {
            const val = expData[field] !== undefined ? expData[field] : "-";
            bodyHtml += `<td>${val}</td>`;
        });
        // Pass the entire experiment object as JSON in the URL using encodeURIComponent
        const expJson = encodeURIComponent(JSON.stringify(expData));
        bodyHtml += `<td><a href="../experiments.html?id=EXP001">View full metadata</a></td>`;
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
