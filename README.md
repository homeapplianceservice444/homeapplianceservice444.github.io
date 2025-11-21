<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Service Manager – Personal</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <style>
    :root {
      --primary-dark: #5B4636;
      --primary: #8C705E;
      --primary-light: #DCC6A3;

      --bg: #F4EDE3;
      --card-bg: #FAF7F3;

      --border: #CBBBA4;

      --text-main: #3C2F2F;
      --text-muted: #7C6A59;

      --danger: #9E4F3A;
      --accent-soft: #EFE1CF;
      --signature-bg: #FFF9C6;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", system-ui, sans-serif;
    }

    body {
      background: var(--bg);
      color: var(--text-main);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    header {
      background: linear-gradient(90deg, var(--primary-dark), var(--primary));
      color: #FAF7F3;
      padding: 10px 14px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      box-shadow: 0 2px 6px rgba(60, 47, 47, 0.25);
    }

    header .title {
      font-size: 17px;
      font-weight: 600;
      letter-spacing: 0.04em;
      text-transform: uppercase;
    }

    header .subtitle {
      font-size: 13px;
      opacity: 0.95;
    }

    main {
      flex: 1;
      padding: 10px;
      max-width: 980px;
      width: 100%;
      margin: 0 auto;
    }

    .card {
      background: var(--card-bg);
      border-radius: 6px;
      border: 1px solid var(--border);
      box-shadow: 0 1px 3px rgba(91, 70, 54, 0.16);
      margin-bottom: 10px;
    }

    .card-header {
      padding: 10px 12px;
      border-bottom: 1px solid var(--border);
      background: #F0E5D6;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .card-title {
      font-size: 15px;
      font-weight: 600;
    }

    .card-body {
      padding: 10px 12px 12px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border-radius: 4px;
      border: 1px solid transparent;
      padding: 7px 16px;
      font-size: 14px;
      cursor: pointer;
      text-decoration: none;
      background: #E4D8C9;
      color: var(--text-main);
      transition: background 0.12s, box-shadow 0.12s, transform 0.08s;
    }

    .btn-primary {
      background: var(--primary);
      border-color: var(--primary-dark);
      color: #FAF7F3;
    }

    .btn-primary:hover {
      background: var(--primary-dark);
      transform: translateY(-1px);
      box-shadow: 0 2px 6px rgba(60, 47, 47, 0.32);
    }

    .btn-secondary {
      background: #FAF7F3;
      border-color: var(--border);
      color: var(--text-main);
    }

    .btn-danger {
      background: #FAF7F3;
      border-color: var(--danger);
      color: var(--danger);
    }

    .btn-sm {
      padding: 4px 9px;
      font-size: 12px;
    }

    .btn + .btn {
      margin-left: 6px;
    }

    .menu-list button {
      width: 100%;
      justify-content: flex-start;
      margin-bottom: 8px;
    }

    .menu-list button span {
      margin-left: 6px;
    }

    .field-group {
      display: flex;
      flex-direction: column;
      margin-bottom: 8px;
    }

    .field-group label {
      font-size: 12px;
      color: var(--text-muted);
      margin-bottom: 2px;
    }

    .field-group input,
    .field-group textarea,
    .field-group select {
      border-radius: 4px;
      border: 1px solid var(--border);
      padding: 7px 9px;
      font-size: 14px;
      background: #FFFDF9;
      color: var(--text-main);
    }

    .field-group textarea {
      min-height: 60px;
      resize: vertical;
    }

    .field-group input:focus,
    .field-group textarea:focus,
    .field-group select:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: 0 0 0 1px rgba(140, 112, 94, 0.35);
    }

    .grid-2 {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 8px;
    }

    .section-title {
      font-size: 13px;
      font-weight: 600;
      margin: 6px 0 4px;
      color: var(--text-main);
    }

    .hint {
      font-size: 11px;
      color: var(--text-muted);
      margin-top: 4px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      font-size: 13px;
    }

    th, td {
      padding: 6px 6px;
      border-bottom: 1px solid var(--border);
      text-align: left;
      vertical-align: top;
    }

    th {
      background: var(--accent-soft);
      font-weight: 600;
      color: var(--text-main);
    }

    tr:last-child td {
      border-bottom: none;
    }

    .status-tag {
      display: inline-block;
      padding: 2px 6px;
      border-radius: 20px;
      background: #EDDFCD;
      color: var(--primary-dark);
      font-size: 11px;
    }

    .badge-id {
      font-family: "SF Mono", ui-monospace, Menlo, Monaco, monospace;
      font-size: 11px;
      color: var(--text-muted);
    }

    .search-row {
      display: flex;
      gap: 6px;
      margin-bottom: 8px;
    }

    .search-row input {
      flex: 1;
    }

    /* MODAL */
    .modal {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.35);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 20;
    }

    .modal.show {
      display: flex;
    }

    .modal-content {
      background: #FFFFFF;
      border-radius: 6px;
      border: 1px solid var(--border);
      width: 96%;
      max-width: 480px;
      box-shadow: 0 6px 18px rgba(0,0,0,0.3);
    }

    .modal-header {
      background: #F0E5D6;
      padding: 8px 12px;
      border-bottom: 1px solid var(--border);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .modal-header h3 {
      font-size: 14px;
      font-weight: 600;
    }

    .modal-body {
      padding: 10px 12px 4px;
    }

    .modal-footer {
      padding: 6px 12px 10px;
      text-align: right;
    }

    .close-x {
      cursor: pointer;
      font-size: 18px;
      color: var(--text-muted);
    }

    /* SIGNATURE */
    #signatureCanvas {
      width: 100%;
      max-width: 100%;
      border-radius: 4px;
      border: 1px solid var(--border);
      background: var(--signature-bg);
      touch-action: none;
      display: block;
    }

    .signature-toolbar {
      display: flex;
      justify-content: flex-end;
      margin-bottom: 4px;
      gap: 6px;
    }

    /* PHOTOS */
    .photos-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 6px;
    }

    .photo-thumb {
      position: relative;
      width: 90px;
      height: 90px;
      border-radius: 4px;
      overflow: hidden;
      border: 1px solid var(--border);
      background: #E0D4C4;
    }

    .photo-thumb img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .photo-remove {
      position: absolute;
      top: 2px;
      right: 2px;
      background: rgba(0,0,0,0.55);
      color: #fff;
      border: none;
      border-radius: 50%;
      width: 18px;
      height: 18px;
      font-size: 12px;
      cursor: pointer;
      line-height: 18px;
      text-align: center;
    }

    @media (max-width: 640px) {
      main {
        padding: 8px 6px 10px;
      }
      .grid-2 {
        grid-template-columns: 1fr;
      }
      header .subtitle {
        display: none;
      }
      .btn {
        padding: 7px 12px;
        font-size: 14px;
      }
    }
  </style>
</head>

<body>
  <header>
    <div>
      <div class="title">SERVICE MANAGER</div>
      <div class="subtitle">Personal use • Offline tool</div>
    </div>
    <div style="font-size:13px;">Welcome: MAX</div>
  </header>

  <main>
    <!-- MAIN MENU -->
    <section id="view-menu" class="card">
      <div class="card-header">
        <div class="card-title">Main Menu</div>
      </div>
      <div class="card-body">
        <div class="menu-list">
          <button class="btn btn-primary" onclick="openNewCall()">
            ➕ <span>New Service Call</span>
          </button>
          <button class="btn btn-secondary" onclick="showView('list')">
            📋 <span>Service List</span>
          </button>
          <button class="btn btn-secondary" onclick="showView('search')">
            🔍 <span>Search</span>
          </button>
        </div>
        <div class="hint">
          Всё хранится только в твоём браузере (localStorage). Можно использовать оффлайн.
        </div>
      </div>
    </section>

    <!-- NEW / EDIT SERVICE CALL -->
    <section id="view-form" class="card" style="display:none;">
      <div class="card-header">
        <div class="card-title" id="form-title">New Service Call</div>
        <div>
          <button class="btn btn-secondary btn-sm" onclick="backToMenu()">Back</button>
        </div>
      </div>
      <div class="card-body">
        <form id="serviceForm" onsubmit="saveCall(event)">
          <input type="hidden" id="callId" />

          <div class="section-title">Customer Info</div>
          <div class="grid-2">
            <div class="field-group">
              <label for="customerName">Name</label>
              <input id="customerName" type="text" autocomplete="off" />
            </div>
            <div class="field-group">
              <label for="customerPhone">Phone</label>
              <input id="customerPhone" type="tel" autocomplete="off" />
            </div>
          </div>
          <div class="field-group">
            <label for="customerAddress">Address</label>
            <input id="customerAddress" type="text" autocomplete="off" />
          </div>

          <div class="section-title" style="margin-top:10px;">Service Info</div>
          <div class="field-group">
            <label for="techNotes">Tech Notes</label>
            <textarea id="techNotes"></textarea>
          </div>
          <div class="field-group">
            <label for="complaint">Complaint</label>
            <textarea id="complaint"></textarea>
          </div>
          <div class="field-group">
            <label for="description">Description (for yourself)</label>
            <textarea id="description"></textarea>
          </div>
          <div class="grid-2">
            <div class="field-group">
              <label for="dealer">Dealer</label>
              <input id="dealer" type="text" />
            </div>
            <div class="field-group">
              <label for="source">Source</label>
              <input id="source" type="text" />
            </div>
          </div>

          <div class="section-title" style="margin-top:10px;">Appliance Info</div>
          <div class="field-group">
            <label for="applType">Appl Type</label>
            <input id="applType" type="text" placeholder="Washer / Dryer / Oven / etc." />
          </div>
          <div class="grid-2">
            <div class="field-group">
              <label for="make">Make</label>
              <input id="make" type="text" />
            </div>
            <div class="field-group">
              <label for="model">Model#</label>
              <input id="model" type="text" />
            </div>
          </div>
          <div class="grid-2">
            <div class="field-group">
              <label for="serial">Serial#</label>
              <input id="serial" type="text" />
            </div>
            <div class="field-group">
              <label for="mfg">Mfg#</label>
              <input id="mfg" type="text" />
            </div>
          </div>

          <div class="grid-2" style="margin-top:10px;">
            <div class="field-group">
              <label for="status">Status</label>
              <select id="status">
                <option value="open">Open</option>
                <option value="scheduled">Scheduled</option>
                <option value="completed">Completed</option>
                <option value="cancelled">Cancelled</option>
              </select>
            </div>
            <div class="field-group">
              <label for="callDate">Call Date</label>
              <input id="callDate" type="date" />
            </div>
          </div>

          <!-- PARTS -->
          <div class="section-title" style="margin-top:12px;">Parts</div>
          <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:4px;">
            <div class="hint">Запчасти для этого вызова.</div>
            <button type="button" class="btn btn-secondary btn-sm" onclick="openPartsModal()">Add Part</button>
          </div>
          <div id="parts-table-wrapper" class="hint">No parts yet.</div>

          <!-- INVOICE -->
          <div class="section-title" style="margin-top:12px;">Invoice</div>
          <div class="grid-2">
            <div class="field-group">
              <label for="invLabor">Labor ($)</label>
              <input id="invLabor" type="number" step="0.01" min="0" oninput="recalcInvoice()" />
            </div>
            <div class="field-group">
              <label for="invExtra">Extra charges ($)</label>
              <input id="invExtra" type="number" step="0.01" min="0" oninput="recalcInvoice()" />
            </div>
          </div>
          <div class="grid-2">
            <div class="field-group">
              <label for="invTax">Tax %</label>
              <input id="invTax" type="number" step="0.01" min="0" oninput="recalcInvoice()" />
            </div>
            <div class="field-group">
              <label for="invStatus">Status</label>
              <select id="invStatus">
                <option value="unpaid">Unpaid</option>
                <option value="paid">Paid</option>
                <option value="warranty">Warranty / No charge</option>
              </select>
            </div>
          </div>
          <div class="grid-2">
            <div class="field-group">
              <label>Parts subtotal ($)</label>
              <input id="invSubtotalDisplay" type="text" readonly />
            </div>
            <div class="field-group">
              <label>Total ($)</label>
              <input id="invTotalDisplay" type="text" readonly />
            </div>
          </div>
          <div class="field-group">
            <label for="invNotes">Invoice Notes</label>
            <textarea id="invNotes"></textarea>
          </div>

          <!-- SIGNATURE -->
          <div class="section-title" style="margin-top:12px;">Signature</div>
          <div class="signature-toolbar">
            <button type="button" class="btn btn-secondary btn-sm" onclick="clearSignature()">Clear</button>
          </div>
          <canvas id="signatureCanvas" height="150"></canvas>
          <div class="hint">Подпись клиента или свои пометки. Рисуй пальцем / мышкой.</div>

          <!-- PHOTOS -->
          <div class="section-title" style="margin-top:12px;">Photos</div>
          <button type="button" class="btn btn-secondary btn-sm" onclick="triggerPhotoInput()">Add Photo</button>
          <input id="photoInput" type="file" accept="image/*" multiple style="display:none" />
          <div id="photos-wrapper" class="photos-grid"></div>
          <div class="hint">Фото серийника, платы, повреждений и т.п.</div>

          <div style="margin-top:14px; display:flex; justify-content:flex-end;">
            <button type="button" class="btn btn-secondary" onclick="backToMenu()">Cancel</button>
            <button type="submit" class="btn btn-primary">Save</button>
          </div>
        </form>
      </div>
    </section>

    <!-- SERVICE LIST -->
    <section id="view-list" class="card" style="display:none;">
      <div class="card-header">
        <div class="card-title">Service List</div>
        <div>
          <button class="btn btn-secondary btn-sm" onclick="backToMenu()">Back</button>
          <button class="btn btn-primary btn-sm" onclick="openNewCall()">New</button>
        </div>
      </div>
      <div class="card-body">
        <div id="list-empty" class="hint" style="display:none;">
          Пока нет ни одного вызова. Нажми <b>New</b>, чтобы добавить.
        </div>
        <div id="list-table-wrapper"></div>
      </div>
    </section>

    <!-- SEARCH -->
    <section id="view-search" class="card" style="display:none;">
      <div class="card-header">
        <div class="card-title">Search</div>
        <div>
          <button class="btn btn-secondary btn-sm" onclick="backToMenu()">Back</button>
        </div>
      </div>
      <div class="card-body">
        <div class="search-row">
          <input id="searchInput" type="text" placeholder="Name, phone, model, serial..." />
          <button class="btn btn-primary btn-sm" onclick="runSearch()">Go</button>
        </div>
        <div id="search-results"></div>
        <div class="hint">
          Поиск по имени, телефону, адресу, типу, модели и серийному номеру.
        </div>
      </div>
    </section>
  </main>

  <!-- PARTS MODAL -->
  <div id="partsModal" class="modal">
    <div class="modal-content">
      <div class="modal-header">
        <h3>Add New Part</h3>
        <span class="close-x" onclick="closePartsModal()">&times;</span>
      </div>
      <form id="partsForm" onsubmit="savePart(event)">
        <div class="modal-body">
          <input type="hidden" id="partId" />
          <div class="field-group">
            <label for="partQty">Qty</label>
            <input id="partQty" type="number" step="1" min="0" />
          </div>
          <div class="field-group">
            <label for="partNo">Part No</label>
            <input id="partNo" type="text" />
          </div>
          <div class="field-group">
            <label for="partDescr">Descr</label>
            <input id="partDescr" type="text" />
          </div>
          <div class="field-group">
            <label for="partDateOrder">Date Order</label>
            <input id="partDateOrder" type="date" />
          </div>
          <div class="field-group">
            <label for="partDateRecv">Date Recvd</label>
            <input id="partDateRecv" type="date" />
          </div>
          <div class="field-group">
            <label for="partNotes">Notes</label>
            <input id="partNotes" type="text" />
          </div>
          <div class="grid-2">
            <div class="field-group">
              <label for="partCost">Cost</label>
              <input id="partCost" type="number" step="0.01" min="0" />
            </div>
            <div class="field-group">
              <label for="partExt">Extension</label>
              <input id="partExt" type="number" step="0.01" min="0" />
            </div>
          </div>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary btn-sm" onclick="closePartsModal()">Cancel</button>
          <button type="submit" class="btn btn-primary btn-sm">Save</button>
        </div>
      </form>
    </div>
  </div>

  <script>
    const STORAGE_KEY = "service_calls_v5";

    let currentParts = [];
    let currentPhotos = [];
    let currentSignatureData = null;

    function loadCalls() {
      try {
        const raw = localStorage.getItem(STORAGE_KEY);
        return raw ? JSON.parse(raw) : [];
      } catch (e) {
        console.error(e);
        return [];
      }
    }

    function saveCalls(calls) {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(calls));
    }

    function showView(name) {
      document.getElementById("view-menu").style.display   = name === "menu"   ? "block" : "none";
      document.getElementById("view-form").style.display   = name === "form"   ? "block" : "none";
      document.getElementById("view-list").style.display   = name === "list"   ? "block" : "none";
      document.getElementById("view-search").style.display = name === "search" ? "block" : "none";

      if (name === "list") renderList();
    }

    function backToMenu() {
      showView("menu");
    }

    function resetForm() {
      document.getElementById("serviceForm").reset();
      document.getElementById("callId").value = "";
      document.getElementById("status").value = "open";

      const today = new Date().toISOString().split("T")[0];
      document.getElementById("callDate").value = today;

      document.getElementById("invLabor").value = "";
      document.getElementById("invExtra").value = "";
      document.getElementById("invTax").value   = "0";
      document.getElementById("invStatus").value = "unpaid";
      document.getElementById("invNotes").value = "";
      document.getElementById("invSubtotalDisplay").value = "";
      document.getElementById("invTotalDisplay").value = "";

      currentParts = [];
      currentPhotos = [];
      currentSignatureData = null;
      renderParts();
      renderPhotos();
      clearSignature(true);
    }

    function openNewCall() {
      resetForm();
      document.getElementById("form-title").textContent = "New Service Call";
      showView("form");
    }

    function calcPartsSubtotal() {
      let sum = 0;
      currentParts.forEach(p => {
        let ext = parseFloat(p.ext);
        if (!ext) {
          const qty = parseFloat(p.qty) || 0;
          const cost = parseFloat(p.cost) || 0;
          ext = qty * cost;
        }
        if (!isNaN(ext)) sum += ext;
      });
      return sum;
    }

    function recalcInvoice() {
      const labor = parseFloat(document.getElementById("invLabor").value) || 0;
      const extra = parseFloat(document.getElementById("invExtra").value) || 0;
      const taxRate = parseFloat(document.getElementById("invTax").value) || 0;

      const partsSubtotal = calcPartsSubtotal();
      document.getElementById("invSubtotalDisplay").value = partsSubtotal.toFixed(2);

      const base = partsSubtotal + labor + extra;
      const taxAmount = base * (taxRate / 100);
      const total = base + taxAmount;
      document.getElementById("invTotalDisplay").value = total.toFixed(2);
    }

    function saveCall(e) {
      e.preventDefault();
      recalcInvoice();

      const idField = document.getElementById("callId");
      const calls = loadCalls();

      const invoice = {
        labor: parseFloat(document.getElementById("invLabor").value) || 0,
        extra: parseFloat(document.getElementById("invExtra").value) || 0,
        taxRate: parseFloat(document.getElementById("invTax").value) || 0,
        status: document.getElementById("invStatus").value,
        notes: document.getElementById("invNotes").value.trim(),
        subtotalParts: parseFloat(document.getElementById("invSubtotalDisplay").value) || 0,
        total: parseFloat(document.getElementById("invTotalDisplay").value) || 0
      };

      const data = {
        id: idField.value || Date.now().toString(),
        customerName: document.getElementById("customerName").value.trim(),
        customerPhone: document.getElementById("customerPhone").value.trim(),
        customerAddress: document.getElementById("customerAddress").value.trim(),
        techNotes: document.getElementById("techNotes").value.trim(),
        complaint: document.getElementById("complaint").value.trim(),
        description: document.getElementById("description").value.trim(),
        dealer: document.getElementById("dealer").value.trim(),
        source: document.getElementById("source").value.trim(),
        applType: document.getElementById("applType").value.trim(),
        make: document.getElementById("make").value.trim(),
        model: document.getElementById("model").value.trim(),
        serial: document.getElementById("serial").value.trim(),
        mfg: document.getElementById("mfg").value.trim(),
        status: document.getElementById("status").value,
        callDate: document.getElementById("callDate").value,
        parts: currentParts,
        photos: currentPhotos,
        signature: currentSignatureData,
        invoice
      };

      const existingIndex = calls.findIndex(c => c.id === data.id);
      if (existingIndex >= 0) {
        calls[existingIndex] = data;
      } else {
        calls.push(data);
      }
      saveCalls(calls);
      showView("list");
    }

    function renderList() {
      const calls = loadCalls().sort((a, b) => (b.callDate || "").localeCompare(a.callDate || ""));
      const wrapper = document.getElementById("list-table-wrapper");
      const empty = document.getElementById("list-empty");

      if (!calls.length) {
        wrapper.innerHTML = "";
        empty.style.display = "block";
        return;
      }
      empty.style.display = "none";

      let html = `
        <table>
          <thead>
            <tr>
              <th>Call#</th>
              <th>Date</th>
              <th>Customer</th>
              <th>Appliance</th>
              <th>Status</th>
              <th>Total</th>
              <th></th>
            </tr>
          </thead>
          <tbody>
      `;
      for (const c of calls) {
        const total = c.invoice && c.invoice.total ? Number(c.invoice.total).toFixed(2) : "";
        html += `
          <tr>
            <td><span class="badge-id">${c.id.slice(-6)}</span></td>
            <td>${c.callDate || ""}</td>
            <td>${c.customerName || ""}<br/><span class="badge-id">${c.customerPhone || ""}</span></td>
            <td>${c.applType || ""}<br/><span class="badge-id">${c.model || ""}</span></td>
            <td><span class="status-tag">${c.status || "open"}</span></td>
            <td>${total ? "$" + total : ""}</td>
            <td>
              <button class="btn btn-secondary btn-sm" onclick="editCall('${c.id}')">View</button>
            </td>
          </tr>
        `;
      }
      html += "</tbody></table>";
      wrapper.innerHTML = html;
    }

    function editCall(id) {
      const calls = loadCalls();
      const c = calls.find(x => x.id === id);
      if (!c) return;

      document.getElementById("form-title").textContent = "Edit Service Call";
      document.getElementById("callId").value = c.id;
      document.getElementById("customerName").value = c.customerName || "";
      document.getElementById("customerPhone").value = c.customerPhone || "";
      document.getElementById("customerAddress").value = c.customerAddress || "";
      document.getElementById("techNotes").value = c.techNotes || "";
      document.getElementById("complaint").value = c.complaint || "";
      document.getElementById("description").value = c.description || "";
      document.getElementById("dealer").value = c.dealer || "";
      document.getElementById("source").value = c.source || "";
      document.getElementById("applType").value = c.applType || "";
      document.getElementById("make").value = c.make || "";
      document.getElementById("model").value = c.model || "";
      document.getElementById("serial").value = c.serial || "";
      document.getElementById("mfg").value = c.mfg || "";
      document.getElementById("status").value = c.status || "open";
      document.getElementById("callDate").value = c.callDate || "";

      currentParts = Array.isArray(c.parts) ? c.parts : [];
      currentPhotos = Array.isArray(c.photos) ? c.photos : [];
      currentSignatureData = c.signature || null;
      renderParts();
      renderPhotos();
      clearSignature(true);
      if (currentSignatureData) drawSignatureFromData(currentSignatureData);

      const inv = c.invoice || {};
      document.getElementById("invLabor").value = inv.labor || "";
      document.getElementById("invExtra").value = inv.extra || "";
      document.getElementById("invTax").value   = inv.taxRate != null ? inv.taxRate : 0;
      document.getElementById("invStatus").value = inv.status || "unpaid";
      document.getElementById("invNotes").value  = inv.notes || "";
      document.getElementById("invSubtotalDisplay").value = inv.subtotalParts != null ? Number(inv.subtotalParts).toFixed(2) : "";
      document.getElementById("invTotalDisplay").value    = inv.total != null ? Number(inv.total).toFixed(2) : "";

      recalcInvoice();
      showView("form");
    }

    function runSearch() {
      const q = document.getElementById("searchInput").value.trim().toLowerCase();
      const resultsDiv = document.getElementById("search-results");
      if (!q) {
        resultsDiv.innerHTML = '<div class="hint">Введите запрос для поиска.</div>';
        return;
      }

      const calls = loadCalls();
      const filtered = calls.filter(c => {
        const hay = [
          c.customerName,
          c.customerPhone,
          c.customerAddress,
          c.applType,
          c.make,
          c.model,
          c.serial
        ].join(" ").toLowerCase();
        return hay.includes(q);
      });

      if (!filtered.length) {
        resultsDiv.innerHTML = '<div class="hint">Ничего не найдено.</div>';
        return;
      }

      let html = "<table><thead><tr><th>Call#</th><th>Customer</th><th>Appliance</th><th>Date</th><th></th></tr></thead><tbody>";
      for (const c of filtered) {
        html += `
          <tr>
            <td><span class="badge-id">${c.id.slice(-6)}</span></td>
            <td>${c.customerName || ""}<br/><span class="badge-id">${c.customerPhone || ""}</span></td>
            <td>${c.applType || ""}<br/><span class="badge-id">${c.model || ""}</span></td>
            <td>${c.callDate || ""}</td>
            <td><button class="btn btn-secondary btn-sm" onclick="editCall('${c.id}')">Open</button></td>
          </tr>
        `;
      }
      html += "</tbody></table>";
      resultsDiv.innerHTML = html;
    }

    /* PARTS */

    function renderParts() {
      const wrapper = document.getElementById("parts-table-wrapper");
      if (!currentParts.length) {
        wrapper.className = "hint";
        wrapper.textContent = "No parts yet.";
        recalcInvoice();
        return;
      }
      let html = `
        <table>
          <thead>
            <tr>
              <th>Qty</th>
              <th>Part No</th>
              <th>Descr</th>
              <th>Order</th>
              <th>Recvd</th>
              <th>Cost</th>
              <th>Ext</th>
              <th></th>
            </tr>
          </thead>
          <tbody>
      `;
      for (const p of currentParts) {
        html += `
          <tr>
            <td>${p.qty || ""}</td>
            <td>${p.partNo || ""}</td>
            <td>${p.descr || ""}</td>
            <td>${p.dateOrder || ""}</td>
            <td>${p.dateRecv || ""}</td>
            <td>${p.cost || ""}</td>
            <td>${p.ext || ""}</td>
            <td>
              <button class="btn btn-secondary btn-sm" onclick="removePart('${p.id}')">✕</button>
            </td>
          </tr>
        `;
      }
      html += "</tbody></table>";
      wrapper.className = "";
      wrapper.innerHTML = html;
      recalcInvoice();
    }

    function openPartsModal() {
      document.getElementById("partsForm").reset();
      document.getElementById("partId").value = "";
      document.getElementById("partsModal").classList.add("show");
    }

    function closePartsModal() {
      document.getElementById("partsModal").classList.remove("show");
    }

    function savePart(e) {
      e.preventDefault();
      const idField = document.getElementById("partId");
      let qty = parseFloat(document.getElementById("partQty").value) || 0;
      let cost = parseFloat(document.getElementById("partCost").value) || 0;
      let ext = document.getElementById("partExt").value;
      if (!ext && qty && cost) {
        ext = (qty * cost).toFixed(2);
      }

      const part = {
        id: idField.value || (Date.now().toString() + Math.random()),
        qty: qty || "",
        partNo: document.getElementById("partNo").value.trim(),
        descr: document.getElementById("partDescr").value.trim(),
        dateOrder: document.getElementById("partDateOrder").value,
        dateRecv: document.getElementById("partDateRecv").value,
        notes: document.getElementById("partNotes").value.trim(),
        cost: cost ? cost.toFixed(2) : "",
        ext: ext
      };

      const existingIndex = currentParts.findIndex(p => p.id === part.id);
      if (existingIndex >= 0) {
        currentParts[existingIndex] = part;
      } else {
        currentParts.push(part);
      }
      renderParts();
      closePartsModal();
    }

    function removePart(id) {
      currentParts = currentParts.filter(p => p.id !== id);
      renderParts();
    }

    /* PHOTOS */

    function triggerPhotoInput() {
      document.getElementById("photoInput").click();
    }

    document.getElementById("photoInput").addEventListener("change", function(event) {
      const files = event.target.files;
      if (!files || !files.length) return;

      Array.from(files).forEach(file => {
        const reader = new FileReader();
        reader.onload = e => {
          currentPhotos.push(e.target.result);
          renderPhotos();
        };
        reader.readAsDataURL(file);
      });

      this.value = "";
    });

    function renderPhotos() {
      const wrapper = document.getElementById("photos-wrapper");
      wrapper.innerHTML = "";
      if (!currentPhotos.length) return;

      currentPhotos.forEach((src, index) => {
        const div = document.createElement("div");
        div.className = "photo-thumb";
        const img = document.createElement("img");
        img.src = src;
        const btn = document.createElement("button");
        btn.className = "photo-remove";
        btn.textContent = "×";
        btn.onclick = () => {
          currentPhotos.splice(index, 1);
          renderPhotos();
        };
        div.appendChild(img);
        div.appendChild(btn);
        wrapper.appendChild(div);
      });
    }

    /* SIGNATURE */

    const canvas = document.getElementById("signatureCanvas");
    const ctx = canvas.getContext("2d");
    let drawing = false;
    let hasSignature = false;

    function resizeCanvas() {
      const rect = canvas.getBoundingClientRect();
      const data = hasSignature ? canvas.toDataURL() : null;
      canvas.width = rect.width;
      canvas.height = 150;
      if (data) drawSignatureFromData(data);
    }

    function startDraw(x, y) {
      drawing = true;
      ctx.strokeStyle = "#333";
      ctx.lineWidth = 2;
      ctx.lineCap = "round";
      ctx.beginPath();
      ctx.moveTo(x, y);
    }

    function moveDraw(x, y) {
      if (!drawing) return;
      ctx.lineTo(x, y);
      ctx.stroke();
      hasSignature = true;
    }

    function endDraw() {
      drawing = false;
      if (hasSignature) {
        currentSignatureData = canvas.toDataURL("image/png");
      }
    }

    function getCanvasPos(e) {
      const rect = canvas.getBoundingClientRect();
      let clientX, clientY;
      if (e.touches && e.touches[0]) {
        clientX = e.touches[0].clientX;
        clientY = e.touches[0].clientY;
      } else {
        clientX = e.clientX;
        clientY = e.clientY;
      }
      return {
        x: clientX - rect.left,
        y: clientY - rect.top
      };
    }

    canvas.addEventListener("mousedown", e => {
      const pos = getCanvasPos(e);
      startDraw(pos.x, pos.y);
    });
    canvas.addEventListener("mousemove", e => {
      const pos = getCanvasPos(e);
      moveDraw(pos.x, pos.y);
    });
    window.addEventListener("mouseup", endDraw);

    canvas.addEventListener("touchstart", e => {
      e.preventDefault();
      const pos = getCanvasPos(e);
      startDraw(pos.x, pos.y);
    }, {passive:false});
    canvas.addEventListener("touchmove", e => {
      e.preventDefault();
      const pos = getCanvasPos(e);
      moveDraw(pos.x, pos.y);
    }, {passive:false});
    canvas.addEventListener("touchend", e => {
      e.preventDefault();
      endDraw();
    });

    function clearSignature(skipDataReset) {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      hasSignature = false;
      if (!skipDataReset) currentSignatureData = null;
    }

    function drawSignatureFromData(dataUrl) {
      const img = new Image();
      img.onload = () => {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
        hasSignature = true;
      };
      img.src = dataUrl;
    }

    window.addEventListener("resize", resizeCanvas);

    (function init() {
      resizeCanvas();
      const today = new Date().toISOString().split("T")[0];
      document.getElementById("callDate").value = today;
      document.getElementById("invTax").value = "0";
      showView("menu");
    })();
  </script>
</body>
</html>
