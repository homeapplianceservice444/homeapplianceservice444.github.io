<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Service Manager - Home Appliance Service</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    :root {
      --bg: #f2e5d3;
      --card: #f7ecde;
      --panel: #fff9ef;
      --border: #d1b89d;
      --accent: #8b5a36;
      --accent-dark: #5f3a23;
      --accent-light: #b68250;
      --text: #3d2a1c;
      --muted: #7b6a58;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    body {
      background: var(--bg);
      color: var(--text);
    }

    .topbar {
      padding: 10px 14px;
      font-size: 20px;
      font-weight: 700;
      color: var(--accent-dark);
    }

    .page {
      max-width: 900px;
      margin: 0 auto;
      padding: 10px;
    }

    .card-main {
      background: var(--card);
      border-radius: 10px;
      border: 1px solid var(--border);
      overflow: hidden;
      box-shadow: 0 2px 5px rgba(0,0,0,0.08);
    }

    .card-header {
      background: linear-gradient(90deg, var(--accent-dark), var(--accent));
      color: #fff;
      padding: 8px 12px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 14px;
      font-weight: 600;
    }

    .card-header span {
      font-weight: 400;
      opacity: 0.9;
    }

    .card-body {
      padding: 10px;
    }

    .btn-menu {
      display: flex;
      align-items: center;
      gap: 8px;
      width: 100%;
      padding: 10px 12px;
      border-radius: 7px;
      border: 1px solid var(--border);
      background: var(--panel);
      cursor: pointer;
      font-size: 14px;
      margin-bottom: 6px;
      color: var(--text);
    }

    .btn-menu.main {
      background: var(--accent);
      border-color: var(--accent-dark);
      color: #fff;
      justify-content: center;
      font-weight: 600;
    }

    .btn-menu-main-icon {
      font-size: 18px;
    }

    .small-note {
      font-size: 11px;
      color: var(--muted);
      margin-top: 4px;
    }

    .section {
      margin-top: 8px;
      display: none;
    }

    .section.active {
      display: block;
    }

    .panel {
      border: 1px solid var(--border);
      border-radius: 8px;
      margin-bottom: 10px;
      background: var(--panel);
      overflow: hidden;
    }

    .panel-header {
      padding: 8px 10px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      cursor: pointer;
      font-size: 14px;
      font-weight: 600;
      color: var(--accent-dark);
      background: rgba(255,255,255,0.6);
    }

    .panel-header:hover {
      background: rgba(255,255,255,0.9);
    }

    .panel-body {
      padding: 8px 10px 10px;
      display: none;
      border-top: 1px solid var(--border);
    }

    .panel.open .panel-body {
      display: block;
    }

    .caret {
      font-size: 14px;
      color: var(--muted);
      transition: transform 0.15s ease;
    }

    .panel.open .caret {
      transform: rotate(90deg);
    }

    label {
      font-size: 13px;
      display: block;
      margin-bottom: 3px;
      color: var(--muted);
    }

    input[type="text"],
    input[type="tel"],
    input[type="email"],
    input[type="number"],
    input[type="date"],
    textarea {
      width: 100%;
      padding: 6px 7px;
      border-radius: 5px;
      border: 1px solid var(--border);
      margin-bottom: 6px;
      font-size: 14px;
      background: #fffdf7;
      color: var(--text);
    }

    textarea {
      min-height: 60px;
      resize: vertical;
    }

    .row {
      display: flex;
      gap: 6px;
      flex-wrap: wrap;
    }

    .row > div {
      flex: 1;
      min-width: 120px;
    }

    .btn-row {
      display: flex;
      gap: 8px;
      margin-top: 6px;
      flex-wrap: wrap;
    }

    .btn {
      padding: 8px 14px;
      border-radius: 6px;
      border: 1px solid var(--border);
      background: #f5ebdd;
      cursor: pointer;
      font-size: 14px;
      color: var(--text);
    }

    .btn.brown {
      background: var(--accent);
      border-color: var(--accent-dark);
      color: #fff;
    }

    .btn.secondary {
      background: #fdf6ec;
    }

    .btn.danger {
      background: #b54c3c;
      border-color: #96372a;
      color: #fff;
    }

    .btn.small {
      padding: 5px 9px;
      font-size: 12px;
    }

    .list {
      margin-top: 4px;
      max-height: 420px;
      overflow-y: auto;
    }

    .list-item {
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 8px 9px;
      margin-bottom: 6px;
      font-size: 13px;
      background: #fffdf7;
    }

    .list-top {
      display: flex;
      justify-content: space-between;
      margin-bottom: 4px;
    }

    .muted {
      color: var(--muted);
      font-size: 12px;
    }

    .tag {
      border: 1px solid var(--border);
      border-radius: 999px;
      padding: 1px 6px;
      font-size: 11px;
      color: var(--muted);
      background: #f3e3cf;
    }

    .search-input {
      margin-bottom: 6px;
    }

    .invoice-textarea {
      font-family: "SF Mono", Menlo, Consolas, monospace;
      font-size: 12px;
      white-space: pre-wrap;
      min-height: 120px;
      background: #fffef8;
    }

    .footer-note {
      font-size: 11px;
      color: var(--muted);
      text-align: center;
      margin-top: 8px;
    }

    #signaturePad {
      border: 1px solid var(--border);
      background: #fff8c9;
      width: 100%;
      height: 150px;
      touch-action: none;
    }

    .manage-pictures {
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 6px 0;
    }

    .circle-icon {
      width: 34px;
      height: 34px;
      border-radius: 50%;
      background: var(--accent);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      font-size: 18px;
    }

    @media (min-width: 768px) {
      .page {
        padding: 16px;
      }
    }
  </style>
</head>
<body>

  <div class="topbar">homeapplianceservice444</div>

  <div class="page">
    <div class="card-main">
      <div class="card-header">
        <div>SERVICE MANAGER</div>
        <div><span>Welcome: MAX</span></div>
      </div>
      <div class="card-body">

        <!-- MAIN MENU -->
        <button class="btn-menu main" onclick="startNewCall()">
          <span class="btn-menu-main-icon">＋</span>
          <span>New Service Call</span>
        </button>
        <button class="btn-menu" onclick="showSection('list')">
          <span>📋</span>
          <span>Service List</span>
        </button>
        <button class="btn-menu" onclick="showSection('search')">
          <span>🔍</span>
          <span>Search</span>
        </button>
        <div class="small-note">
          Всё хранится только в твоём браузере (localStorage). Можно использовать оффлайн.
        </div>

        <!-- NEW / EDIT SERVICE CALL -->
        <div id="section-new" class="section">
          <div class="muted" id="editLabel" style="margin:4px 0 6px;"></div>

          <!-- CUSTOMER INFO -->
          <div class="panel" id="panel-customer">
            <div class="panel-header" onclick="togglePanel('panel-customer')">
              <span>Customer Info</span>
              <span class="caret">▸</span>
            </div>
            <div class="panel-body">
              <div class="row">
                <div>
                  <label>First Name</label>
                  <input type="text" id="firstName">
                </div>
                <div>
                  <label>Last Name</label>
                  <input type="text" id="lastName">
                </div>
              </div>

              <label>Address</label>
              <input type="text" id="address">

              <div class="row">
                <div>
                  <label>City</label>
                  <input type="text" id="city">
                </div>
              </div>

              <label>Instructions</label>
              <textarea id="instructions"></textarea>

              <div class="row">
                <div>
                  <label>Zip Code</label>
                  <input type="text" id="zip">
                </div>
                <div>
                  <label>State</label>
                  <input type="text" id="state">
                </div>
              </div>

              <label>Cell Phone</label>
              <input type="tel" id="cellPhone1">

              <label>Cell Phone</label>
              <input type="tel" id="cellPhone2">

              <label>Alt Phone</label>
              <input type="tel" id="altPhone">

              <label>E-mail</label>
              <input type="email" id="email">
            </div>
          </div>

          <!-- APPLIANCE INFO -->
          <div class="panel" id="panel-appl">
            <div class="panel-header" onclick="togglePanel('panel-appl')">
              <span>Appl Info</span>
              <span class="caret">▸</span>
            </div>
            <div class="panel-body">
              <label>Appl Type</label>
              <input type="text" id="applType">
              <label>Make</label>
              <input type="text" id="make">
              <label>Model#</label>
              <input type="text" id="model">
              <label>Serial#</label>
              <input type="text" id="serial">
              <label>Mfg#</label>
              <input type="text" id="mfg">
            </div>
          </div>

          <!-- SERVICE INFO -->
          <div class="panel" id="panel-service">
            <div class="panel-header" onclick="togglePanel('panel-service')">
              <span>Service Info</span>
              <span class="caret">▸</span>
            </div>
            <div class="panel-body">
              <label>Tech Notes</label>
              <textarea id="techNotes"></textarea>
              <label>Complaint</label>
              <textarea id="complaint"></textarea>
              <label>Description</label>
              <textarea id="description"></textarea>
              <label>Dealer</label>
              <input type="text" id="dealer">
              <label>Source</label>
              <input type="text" id="source">
            </div>
          </div>

          <!-- SERVICE DATES -->
          <div class="panel" id="panel-dates">
            <div class="panel-header" onclick="togglePanel('panel-dates')">
              <span>Service Dates</span>
              <span class="caret">▸</span>
            </div>
            <div class="panel-body">
              <label>Date Purchased</label>
              <input type="date" id="datePurchased">
              <label>Date Started</label>
              <input type="date" id="dateStarted">
              <label>Date Completed</label>
              <input type="date" id="dateCompleted">
            </div>
          </div>

          <!-- CHARGES (INTERNAL INVOICE) -->
          <div class="panel" id="panel-charges">
            <div class="panel-header" onclick="togglePanel('panel-charges')">
              <span>Charges (internal)</span>
              <span class="caret">▸</span>
            </div>
            <div class="panel-body">
              <label>Parts Total</label>
              <input type="number" step="0.01" id="partsTotal" value="0">

              <label>Flat Rate</label>
              <input type="number" step="0.01" id="flatRate" value="0">

              <label>Labor</label>
              <input type="number" step="0.01" id="labor" value="0">

              <label>Trip Charge</label>
              <input type="number" step="0.01" id="tripCharge" value="0">

              <label>Shipping</label>
              <input type="number" step="0.01" id="shipping" value="0">

              <label>Tax</label>
              <input type="number" step="0.01" id="tax" value="0">

              <label>Total</label>
              <input type="number" step="0.01" id="total" value="0">

              <div class="btn-row">
                <button class="btn small brown" type="button" onclick="addTax()">Add Tax</button>
                <button class="btn small brown" type="button" onclick="sumTotal()">Sum</button>
              </div>
              <div class="muted" style="margin-top:4px;">
                В этих полях идёт авто-подсчёт. Но клиент при отправке будет видеть только TOTAL.
              </div>
            </div>
          </div>

          <!-- MANAGE PICTURES -->
          <div class="panel" id="panel-pictures">
            <div class="panel-header" onclick="togglePanel('panel-pictures')">
              <span>Manage Pictures</span>
              <span class="caret">▸</span>
            </div>
            <div class="panel-body">
              <div class="manage-pictures">
                <div class="circle-icon">📷</div>
                <input type="file" id="pictures" accept="image/*" multiple>
              </div>
              <div class="muted">Фото не сохраняются в localStorage, только для просмотра/отправки сейчас.</div>
            </div>
          </div>

          <!-- SIGNATURE -->
          <div class="panel" id="panel-signature">
            <div class="panel-header" onclick="togglePanel('panel-signature')">
              <span>Signature</span>
              <span class="caret">▸</span>
            </div>
            <div class="panel-body">
              <div class="manage-pictures">
                <div class="circle-icon">✏️</div>
                <span>Customer Signature</span>
              </div>
              <canvas id="signaturePad"></canvas>
              <div class="btn-row">
                <button class="btn small secondary" type="button" onclick="clearSignature()">Clear</button>
              </div>
            </div>
          </div>

          <!-- FORM BUTTONS -->
          <div class="btn-row" style="justify-content:flex-end;margin-top:4px;">
            <button class="btn secondary" type="button" onclick="cancelForm()">Cancel</button>
            <button class="btn brown" type="button" onclick="saveCall()">Save</button>
          </div>
        </div>

        <!-- SERVICE LIST -->
        <div id="section-list" class="section">
          <div class="panel">
            <div class="panel-header">
              <span>Service List</span>
            </div>
            <div class="panel-body">
              <div class="muted">Сохранённые вызовы (редактирование, invoice, удаление).</div>
              <div id="listContainer" class="list"></div>
            </div>
          </div>
        </div>

        <!-- SEARCH -->
        <div id="section-search" class="section">
          <div class="panel">
            <div class="panel-header">
              <span>Search</span>
            </div>
            <div class="panel-body">
              <input id="searchQuery" class="search-input" type="text"
                     placeholder="Имя, телефон, адрес, модель, описание..."
                     oninput="renderSearchResults()">
              <div id="searchResults" class="list"></div>
            </div>
          </div>
        </div>

        <!-- INVOICE VIEW (INTERNAL + CUSTOMER PREVIEW) -->
        <div id="section-invoice" class="section">
          <div class="panel">
            <div class="panel-header">
              <span>Invoice</span>
            </div>
            <div class="panel-body">
              <div id="invoiceInfo" class="muted" style="margin-bottom:6px;"></div>

              <div class="muted" style="margin-bottom:4px;">
                Внутренние суммы (для тебя):
              </div>
              <textarea id="invoiceInternal" class="invoice-textarea" readonly></textarea>

              <div class="muted" style="margin:8px 0 4px;">
                Текст, который увидит клиент (только TOTAL):
              </div>
              <textarea id="invoiceCustomerText" class="invoice-textarea"></textarea>

              <div class="btn-row">
                <button class="btn brown small" type="button" onclick="copyCustomerInvoice()">Copy for Customer</button>
                <a id="invoiceSmsLink" class="btn small secondary" href="#" target="_blank">SMS to Customer</a>
                <button class="btn small secondary" type="button" onclick="printCustomerInvoice()">Print / PDF</button>
              </div>

              <div class="btn-row" style="margin-top:6px;">
                <button class="btn small secondary" type="button" onclick="showSection('list')">Back to List</button>
              </div>
            </div>
          </div>
        </div>

        <div class="footer-note">
          Home Appliance Service • Phone: (253)-213-1651
        </div>

      </div>
    </div>
  </div>

  <script>
    const STORAGE_KEY = 'serviceCalls_v4';
    let serviceCalls = [];
    let currentCallId = null; // null = new, иначе редактируем существующий

    /* ---------- STORAGE ---------- */
    function loadCalls() {
      try {
        const raw = localStorage.getItem(STORAGE_KEY);
        serviceCalls = raw ? JSON.parse(raw) : [];
      } catch (e) {
        serviceCalls = [];
      }
      renderList();
      renderSearchResults();
    }

    function saveToStorage() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(serviceCalls));
    }

    /* ---------- UI SECTIONS ---------- */
    function showSection(name) {
      ['new','list','search','invoice'].forEach(s => {
        const el = document.getElementById('section-' + s);
        if (!el) return;
        el.classList.toggle('active', s === name);
      });
    }

    function togglePanel(id) {
      const panel = document.getElementById(id);
      if (!panel) return;
      panel.classList.toggle('open');
    }

    function openOnlyCustomerPanel() {
      ['panel-customer','panel-appl','panel-service','panel-dates','panel-charges','panel-pictures','panel-signature']
        .forEach(id => {
          const el = document.getElementById(id);
          if (!el) return;
          el.classList.remove('open');
        });
      const cust = document.getElementById('panel-customer');
      if (cust) cust.classList.add('open');
    }

    /* ---------- FORM / CALL DATA ---------- */
    function startNewCall() {
      currentCallId = null;
      document.getElementById('editLabel').textContent = 'New Service Call';
      clearForm();
      openOnlyCustomerPanel();
      showSection('new');
    }

    function cancelForm() {
      clearForm();
      showSection('list');
    }

    function clearForm() {
      const fields = [
        'firstName','lastName','address','city','instructions','zip','state',
        'cellPhone1','cellPhone2','altPhone','email',
        'applType','make','model','serial','mfg',
        'techNotes','complaint','description','dealer','source',
        'datePurchased','dateStarted','dateCompleted',
        'partsTotal','flatRate','labor','tripCharge','shipping','tax','total'
      ];
      fields.forEach(id => {
        const el = document.getElementById(id);
        if (!el) return;
        if (el.type === 'number') el.value = 0;
        else el.value = '';
      });
      clearSignature();
    }

    function numberVal(id) {
      const el = document.getElementById(id);
      if (!el) return 0;
      const v = parseFloat(el.value);
      return isNaN(v) ? 0 : v;
    }

    function sumTotal() {
      const subtotal = numberVal('partsTotal') + numberVal('flatRate') +
                       numberVal('labor') + numberVal('tripCharge') +
                       numberVal('shipping') + numberVal('tax');
      document.getElementById('total').value = subtotal.toFixed(2);
    }

    function addTax() {
      const subtotalNoTax = numberVal('partsTotal') + numberVal('flatRate') +
                            numberVal('labor') + numberVal('tripCharge') +
                            numberVal('shipping');
      const tax = +(subtotalNoTax * 0.08875).toFixed(2); // примерный NYC tax
      document.getElementById('tax').value = tax.toFixed(2);
      document.getElementById('total').value = (subtotalNoTax + tax).toFixed(2);
    }

    function getFormData() {
      return {
        id: currentCallId || Date.now(),
        createdAt: currentCallId
          ? (serviceCalls.find(c => c.id === currentCallId)?.createdAt || new Date().toISOString())
          : new Date().toISOString(),
        customer: {
          firstName: document.getElementById('firstName').value.trim(),
          lastName: document.getElementById('lastName').value.trim(),
          address: document.getElementById('address').value.trim(),
          city: document.getElementById('city').value.trim(),
          instructions: document.getElementById('instructions').value.trim(),
          zip: document.getElementById('zip').value.trim(),
          state: document.getElementById('state').value.trim(),
          cellPhone1: document.getElementById('cellPhone1').value.trim(),
          cellPhone2: document.getElementById('cellPhone2').value.trim(),
          altPhone: document.getElementById('altPhone').value.trim(),
          email: document.getElementById('email').value.trim()
        },
        appliance: {
          applType: document.getElementById('applType').value.trim(),
          make: document.getElementById('make').value.trim(),
          model: document.getElementById('model').value.trim(),
          serial: document.getElementById('serial').value.trim(),
          mfg: document.getElementById('mfg').value.trim()
        },
        serviceInfo: {
          techNotes: document.getElementById('techNotes').value.trim(),
          complaint: document.getElementById('complaint').value.trim(),
          description: document.getElementById('description').value.trim(),
          dealer: document.getElementById('dealer').value.trim(),
          source: document.getElementById('source').value.trim()
        },
        dates: {
          purchased: document.getElementById('datePurchased').value,
          started: document.getElementById('dateStarted').value,
          completed: document.getElementById('dateCompleted').value
        },
        charges: {
          partsTotal: numberVal('partsTotal'),
          flatRate: numberVal('flatRate'),
          labor: numberVal('labor'),
          tripCharge: numberVal('tripCharge'),
          shipping: numberVal('shipping'),
          tax: numberVal('tax'),
          total: numberVal('total')
        }
      };
    }

    function fillFormFromCall(call) {
      currentCallId = call.id;
      document.getElementById('editLabel').textContent = 'Editing Call #' + call.id;

      const c = call.customer || {};
      const a = call.appliance || {};
      const s = call.serviceInfo || {};
      const d = call.dates || {};
      const ch = call.charges || {};

      document.getElementById('firstName').value = c.firstName || '';
      document.getElementById('lastName').value = c.lastName || '';
      document.getElementById('address').value = c.address || '';
      document.getElementById('city').value = c.city || '';
      document.getElementById('instructions').value = c.instructions || '';
      document.getElementById('zip').value = c.zip || '';
      document.getElementById('state').value = c.state || '';
      document.getElementById('cellPhone1').value = c.cellPhone1 || '';
      document.getElementById('cellPhone2').value = c.cellPhone2 || '';
      document.getElementById('altPhone').value = c.altPhone || '';
      document.getElementById('email').value = c.email || '';

      document.getElementById('applType').value = a.applType || '';
      document.getElementById('make').value = a.make || '';
      document.getElementById('model').value = a.model || '';
      document.getElementById('serial').value = a.serial || '';
      document.getElementById('mfg').value = a.mfg || '';

      document.getElementById('techNotes').value = s.techNotes || '';
      document.getElementById('complaint').value = s.complaint || '';
      document.getElementById('description').value = s.description || '';
      document.getElementById('dealer').value = s.dealer || '';
      document.getElementById('source').value = s.source || '';

      document.getElementById('datePurchased').value = d.purchased || '';
      document.getElementById('dateStarted').value = d.started || '';
      document.getElementById('dateCompleted').value = d.completed || '';

      document.getElementById('partsTotal').value = (ch.partsTotal ?? 0);
      document.getElementById('flatRate').value = (ch.flatRate ?? 0);
      document.getElementById('labor').value = (ch.labor ?? 0);
      document.getElementById('tripCharge').value = (ch.tripCharge ?? 0);
      document.getElementById('shipping').value = (ch.shipping ?? 0);
      document.getElementById('tax').value = (ch.tax ?? 0);
      document.getElementById('total').value = (ch.total ?? 0);
    }

    function saveCall() {
      // Авто-сумма перед сохранением
      sumTotal();

      const data = getFormData();
      const namePresent = data.customer.firstName || data.customer.lastName;
      const phonePresent = data.customer.cellPhone1 || data.customer.cellPhone2 || data.customer.altPhone;

      if (!namePresent && !phonePresent) {
        alert('Нужно указать хотя бы имя или телефон.');
        return;
      }

      if (currentCallId) {
        // update
        const idx = serviceCalls.findIndex(c => c.id === currentCallId);
        if (idx !== -1) {
          serviceCalls[idx] = data;
        } else {
          serviceCalls.unshift(data);
        }
      } else {
        // new
        serviceCalls.unshift(data);
        currentCallId = data.id;
      }

      saveToStorage();
      renderList();
      renderSearchResults();
      showSection('list');
    }

    /* ---------- LIST & SEARCH ---------- */
    function escapeHtml(str) {
      if (!str) return '';
      return String(str)
        .replace(/&/g, '&amp;')
        .replace(/</g, '&lt;')
        .replace(/>/g, '&gt;')
        .replace(/"/g, '&quot;')
        .replace(/'/g, '&#039;');
    }

    function renderList() {
      const container = document.getElementById('listContainer');
      if (!container) return;
      if (!serviceCalls.length) {
        container.innerHTML = '<div class="muted">Пока нет сохранённых вызовов.</div>';
        return;
      }
      container.innerHTML = serviceCalls.map(createListItemHtml).join('');
    }

    function createListItemHtml(call) {
      const date = new Date(call.createdAt || call.id).toLocaleString();
      const total = call.charges?.total || 0;
      const name = ((call.customer?.firstName || '') + ' ' + (call.customer?.lastName || '')).trim() || 'No name';
      const phone = call.customer?.cellPhone1 || call.customer?.cellPhone2 || call.customer?.altPhone || '';
      const appliance = [
        call.appliance?.applType,
        call.appliance?.make,
        call.appliance?.model
      ].filter(Boolean).join(' ');

      return `
        <div class="list-item">
          <div class="list-top">
            <div>${escapeHtml(name)}</div>
            <div class="tag">$${Number(total).toFixed(2)}</div>
          </div>
          <div class="muted">${escapeHtml(phone)}</div>
          <div class="muted">${escapeHtml(appliance)}</div>
          <div class="muted">${escapeHtml(call.customer?.address || '')}, ${escapeHtml(call.customer?.city || '')}</div>
          <div class="muted">Created: ${date}</div>
          <div class="btn-row" style="margin-top:4px;">
            <button class="btn small secondary" type="button" onclick="editCall(${call.id})">Edit</button>
            <button class="btn small secondary" type="button" onclick="openInvoice(${call.id})">Invoice</button>
            <button class="btn small danger" type="button" onclick="deleteCall(${call.id})">Delete</button>
          </div>
        </div>
      `;
    }

    function editCall(id) {
      const call = serviceCalls.find(c => c.id === id);
      if (!call) return;
      fillFormFromCall(call);
      openOnlyCustomerPanel();
      showSection('new');
    }

    function deleteCall(id) {
      if (!confirm('Удалить этот вызов?')) return;
      serviceCalls = serviceCalls.filter(c => c.id !== id);
      saveToStorage();
      renderList();
      renderSearchResults();
    }

    function renderSearchResults() {
      const qInput = document.getElementById('searchQuery');
      const container = document.getElementById('searchResults');
      if (!qInput || !container) return;
      const q = qInput.value.trim().toLowerCase();
      let filtered = serviceCalls;
      if (q) {
        filtered = serviceCalls.filter(c => {
          const t = [
            c.customer?.firstName,
            c.customer?.lastName,
            c.customer?.cellPhone1,
            c.customer?.cellPhone2,
            c.customer?.altPhone,
            c.customer?.address,
            c.customer?.city,
            c.appliance?.applType,
            c.appliance?.make,
            c.appliance?.model,
            c.serviceInfo?.techNotes,
            c.serviceInfo?.complaint,
            c.serviceInfo?.description
          ].join(' ').toLowerCase();
          return t.includes(q);
        });
      }
      if (!filtered.length) {
        container.innerHTML = '<div class="muted">Ничего не найдено.</div>';
        return;
      }
      container.innerHTML = filtered.map(createListItemHtml).join('');
    }

    /* ---------- INVOICE ---------- */
    function openInvoice(id) {
      const call = serviceCalls.find(c => c.id === id);
      if (!call) return;

      currentCallId = id;

      const fullName = ((call.customer?.firstName || '') + ' ' + (call.customer?.lastName || '')).trim();
      const phone = call.customer?.cellPhone1 || call.customer?.cellPhone2 || call.customer?.altPhone || '';
      const addressLine = [call.customer?.address, call.customer?.city, call.customer?.state, call.customer?.zip]
        .filter(Boolean).join(', ');
      const charges = call.charges || {};
      const total = Number(charges.total || 0);

      document.getElementById('invoiceInfo').textContent =
        `Call #${call.id} • ${fullName || 'customer'} • Total: $${total.toFixed(2)}`;

      // Внутренний breakdown (видишь только ты)
      const internalText =
`Internal Charges (for technician):

Parts Total: $${(charges.partsTotal || 0).toFixed(2)}
Flat Rate:   $${(charges.flatRate || 0).toFixed(2)}
Labor:       $${(charges.labor || 0).toFixed(2)}
Trip Charge: $${(charges.tripCharge || 0).toFixed(2)}
Shipping:    $${(charges.shipping || 0).toFixed(2)}
Tax:         $${(charges.tax || 0).toFixed(2)}
--------------------------
TOTAL:       $${total.toFixed(2)}`;
      document.getElementById('invoiceInternal').value = internalText;

      // Текст для клиента – ТОЛЬКО TOTAL
      const customerText =
`Home Appliance Service
Phone: (253)-213-1651

Total: $${total.toFixed(2)}

Thank you for your business!`;
      document.getElementById('invoiceCustomerText').value = customerText;

      // SMS ссылку тоже делаем только с total
      const smsPhone = (phone || '').replace(/[^\d+]/g, '');
      const smsLink = smsPhone
        ? `sms:${smsPhone}?&body=${encodeURIComponent(customerText)}`
        : '#';
      const anchor = document.getElementById('invoiceSmsLink');
      anchor.href = smsLink;
      anchor.style.pointerEvents = smsPhone ? 'auto' : 'none';
      anchor.style.opacity = smsPhone ? '1' : '0.5';

      showSection('invoice');
    }

    function copyCustomerInvoice() {
      const ta = document.getElementById('invoiceCustomerText');
      ta.select();
      ta.setSelectionRange(0, 99999);
      try {
        document.execCommand('copy');
        alert('Customer invoice скопирован (только total).');
      } catch (e) {
        alert('Не получилось автокопирование, скопируй вручную.');
      }
    }

    function printCustomerInvoice() {
      const text = document.getElementById('invoiceCustomerText').value;
      const win = window.open('', '_blank');
      win.document.write(`
        <html>
        <head>
          <meta charset="UTF-8">
          <title>Invoice</title>
          <style>
            body { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif; padding: 20px; }
            pre { white-space: pre-wrap; font-family: "SF Mono", Menlo, Monaco, Consolas, "Courier New", monospace; }
          </style>
        </head>
        <body>
          <pre>${escapeHtml(text)}</pre>
        </body>
        </html>
      `);
      win.document.close();
      win.focus();
      win.print();
    }

    /* ---------- SIGNATURE PAD ---------- */
    let sigCanvas, sigCtx, drawing = false, lastX = 0, lastY = 0;

    function initSignaturePad() {
      sigCanvas = document.getElementById('signaturePad');
      if (!sigCanvas) return;
      sigCtx = sigCanvas.getContext('2d');
      resizeSignatureCanvas();

      function startDraw(x, y) {
        drawing = true;
        lastX = x;
        lastY = y;
      }

      function draw(x, y) {
        if (!drawing) return;
        sigCtx.strokeStyle = '#000';
        sigCtx.lineWidth = 2;
        sigCtx.lineCap = 'round';
        sigCtx.beginPath();
        sigCtx.moveTo(lastX, lastY);
        sigCtx.lineTo(x, y);
        sigCtx.stroke();
        lastX = x;
        lastY = y;
      }

      function endDraw() {
        drawing = false;
      }

      sigCanvas.addEventListener('mousedown', e => {
        const rect = sigCanvas.getBoundingClientRect();
        startDraw(e.clientX - rect.left, e.clientY - rect.top);
      });
      sigCanvas.addEventListener('mousemove', e => {
        const rect = sigCanvas.getBoundingClientRect();
        draw(e.clientX - rect.left, e.clientY - rect.top);
      });
      window.addEventListener('mouseup', endDraw);

      sigCanvas.addEventListener('touchstart', e => {
        e.preventDefault();
        const t = e.touches[0];
        const rect = sigCanvas.getBoundingClientRect();
        startDraw(t.clientX - rect.left, t.clientY - rect.top);
      }, { passive: false });
      sigCanvas.addEventListener('touchmove', e => {
        e.preventDefault();
        const t = e.touches[0];
        const rect = sigCanvas.getBoundingClientRect();
        draw(t.clientX - rect.left, t.clientY - rect.top);
      }, { passive: false });
      sigCanvas.addEventListener('touchend', e => {
        e.preventDefault();
        endDraw();
      });
    }

    function resizeSignatureCanvas() {
      if (!sigCanvas) return;
      const rect = sigCanvas.getBoundingClientRect();
      sigCanvas.width = rect.width;
      sigCanvas.height = rect.height;
    }

    function clearSignature() {
      if (!sigCtx || !sigCanvas) return;
      sigCtx.clearRect(0, 0, sigCanvas.width, sigCanvas.height);
    }

    window.addEventListener('resize', resizeSignatureCanvas);

    /* ---------- INIT ---------- */
    function attachAutoSum() {
      ['partsTotal','flatRate','labor','tripCharge','shipping','tax']
        .forEach(id => {
          const el = document.getElementById(id);
          if (!el) return;
          el.addEventListener('input', sumTotal);
        });
    }

    loadCalls();
    showSection('list');
    window.addEventListener('load', () => {
      initSignaturePad();
      attachAutoSum();
      openOnlyCustomerPanel();
    });
  </script>
</body>
</html>
