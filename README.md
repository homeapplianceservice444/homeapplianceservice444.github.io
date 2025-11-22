<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Service Manager - Home Appliance Service</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    :root {
      --blue: #0285d9;
      --blue-dark: #006ab0;
      --border: #d0d0d0;
      --bg: #f3f3f3;
      --text: #222;
      --muted: #666;
      --btn-blue: #1993ff;
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
      background: var(--blue);
      color: #fff;
      padding: 10px 14px;
      font-size: 18px;
      font-weight: 600;
    }

    .page {
      max-width: 900px;
      margin: 0 auto;
      padding: 10px;
    }

    .card-main {
      background: #fff;
      border-radius: 6px;
      border: 1px solid var(--border);
      margin-top: 10px;
      overflow: hidden;
    }

    .card-header {
      background: #f7f7f7;
      border-bottom: 1px solid var(--border);
      padding: 8px 10px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 14px;
      font-weight: 600;
    }

    .card-header span {
      font-weight: 400;
      color: var(--muted);
    }

    .card-body {
      padding: 10px;
    }

    .btn-menu {
      display: block;
      width: 100%;
      text-align: left;
      padding: 10px 12px;
      margin-bottom: 6px;
      border-radius: 4px;
      border: 1px solid var(--border);
      background: #fff;
      cursor: pointer;
      font-size: 14px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .btn-menu.main {
      background: var(--btn-blue);
      border-color: var(--blue-dark);
      color: #fff;
      justify-content: center;
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
      border-radius: 4px;
      margin-bottom: 10px;
      background: #fff;
    }

    .panel-header {
      padding: 8px 10px;
      border-bottom: 1px solid var(--border);
      font-weight: 600;
      font-size: 14px;
    }

    .panel-body {
      padding: 8px 10px 10px;
    }

    label {
      font-size: 13px;
      display: block;
      margin-bottom: 3px;
    }

    input[type="text"],
    input[type="tel"],
    input[type="email"],
    input[type="number"],
    input[type="date"],
    textarea {
      width: 100%;
      padding: 6px 7px;
      border-radius: 3px;
      border: 1px solid var(--border);
      margin-bottom: 6px;
      font-size: 14px;
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
      border-radius: 4px;
      border: 1px solid var(--border);
      background: #f7f7f7;
      cursor: pointer;
      font-size: 14px;
    }

    .btn.blue {
      background: var(--btn-blue);
      border-color: var(--blue-dark);
      color: #fff;
    }

    .btn.danger {
      background: #e34a4a;
      border-color: #c73737;
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
      border-radius: 3px;
      padding: 8px 9px;
      margin-bottom: 6px;
      font-size: 13px;
      background: #fff;
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
    }

    .search-input {
      margin-bottom: 6px;
    }

    .invoice-textarea {
      font-family: "SF Mono", Menlo, Consolas, monospace;
      font-size: 12px;
      white-space: pre-wrap;
      min-height: 180px;
    }

    .footer-note {
      font-size: 11px;
      color: var(--muted);
      text-align: center;
      margin-top: 8px;
    }

    /* Signature */
    #signaturePad {
      border: 1px solid var(--border);
      background: #fffde0;
      width: 100%;
      height: 160px;
      touch-action: none;
    }

    .manage-pictures {
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 8px 0;
    }

    .circle-icon {
      width: 34px;
      height: 34px;
      border-radius: 50%;
      background: var(--btn-blue);
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
        <button class="btn-menu main" onclick="showSection('new')">
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

        <!-- NEW SERVICE CALL -->
        <div id="section-new" class="section">
          <!-- CUSTOMER INFO -->
          <div class="panel">
            <div class="panel-header">Customer Info</div>
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
          <div class="panel">
            <div class="panel-header">Appl Info</div>
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
          <div class="panel">
            <div class="panel-header">Service Info</div>
            <div class="panel-body">
              <label>Tech Notes</label>
              <textarea id="techNotes"></textarea>
              <label>Compliant</label>
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
          <div class="panel">
            <div class="panel-header">Service Dates</div>
            <div class="panel-body">
              <label>Date Purchased</label>
              <input type="date" id="datePurchased">
              <label>Date Started</label>
              <input type="date" id="dateStarted">
              <label>Date Completed</label>
              <input type="date" id="dateCompleted">
            </div>
          </div>

          <!-- CHARGES -->
          <div class="panel">
            <div class="panel-header">Charges</div>
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
              <input type="number" step="0.01" id="total" value="0" readonly>

              <div class="btn-row">
                <button class="btn small blue" type="button" onclick="addTax()">Add Tax</button>
                <button class="btn small blue" type="button" onclick="sumTotal()">Sum</button>
              </div>
            </div>
          </div>

          <!-- MANAGE PICTURES -->
          <div class="panel">
            <div class="panel-header">Manage pictures</div>
            <div class="panel-body">
              <div class="manage-pictures">
                <div class="circle-icon">📷</div>
                <input type="file" id="pictures" accept="image/*" multiple>
              </div>
              <div class="muted">Картинки не сохраняются в localStorage, только для отправки/просмотра сейчас.</div>
            </div>
          </div>

          <!-- SIGNATURE -->
          <div class="panel">
            <div class="panel-header">Signature</div>
            <div class="panel-body">
              <div class="manage-pictures">
                <div class="circle-icon">✏️</div>
                <span>Get Signature</span>
              </div>
              <canvas id="signaturePad"></canvas>
              <div class="btn-row">
                <button class="btn small" type="button" onclick="clearSignature()">Clear</button>
              </div>
            </div>
          </div>

          <!-- FORM BUTTONS -->
          <div class="btn-row" style="justify-content:flex-end;margin-top:4px;">
            <button class="btn" type="button" onclick="resetForm()">Cancel</button>
            <button class="btn blue" type="button" onclick="saveCall()">Save</button>
          </div>
        </div>

        <!-- SERVICE LIST -->
        <div id="section-list" class="section">
          <div class="panel">
            <div class="panel-header">Service List</div>
            <div class="panel-body">
              <div class="muted">Последние сохранённые вызовы.</div>
              <div id="listContainer" class="list"></div>
            </div>
          </div>
        </div>

        <!-- SEARCH -->
        <div id="section-search" class="section">
          <div class="panel">
            <div class="panel-header">Search</div>
            <div class="panel-body">
              <input id="searchQuery" class="search-input" type="text"
                     placeholder="Имя, телефон, адрес, модель, описание..."
                     oninput="renderSearchResults()">
              <div id="searchResults" class="list"></div>
            </div>
          </div>
        </div>

        <!-- INVOICE -->
        <div id="section-invoice" class="section">
          <div class="panel">
            <div class="panel-header">Invoice</div>
            <div class="panel-body">
              <div id="invoiceInfo" class="muted" style="margin-bottom:4px;"></div>
              <textarea id="invoiceText" class="invoice-textarea"></textarea>
              <div class="btn-row">
                <button class="btn blue small" type="button" onclick="copyInvoice()">Copy Invoice</button>
                <a id="invoiceSmsLink" class="btn small" href="#" target="_blank">SMS to Customer</a>
                <button class="btn small" type="button" onclick="printInvoice()">Print / PDF</button>
              </div>
              <div class="btn-row" style="margin-top:6px;">
                <button class="btn small" type="button" onclick="showSection('list')">Back to List</button>
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
    const STORAGE_KEY = 'serviceCalls_v3';
    let serviceCalls = [];

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

    function showSection(name) {
      ['new','list','search','invoice'].forEach(s => {
        const el = document.getElementById('section-' + s);
        if (!el) return;
        el.classList.toggle('active', s === name);
      });
    }

    /* Charges helpers */
    function numberVal(id) {
      return parseFloat(document.getElementById(id).value) || 0;
    }

    function sumTotal() {
      const subtotal = numberVal('partsTotal') + numberVal('flatRate') + numberVal('labor') +
                       numberVal('tripCharge') + numberVal('shipping') + numberVal('tax');
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

    function resetForm() {
      document.querySelectorAll('#section-new input, #section-new textarea')
        .forEach(el => {
          if (el.type === 'number') el.value = 0;
          else if (el.type === 'date') el.value = '';
          else el.value = '';
        });
      document.getElementById('total').value = '0';
      clearSignature();
    }

    function getFormData() {
      return {
        id: Date.now(),
        createdAt: new Date().toISOString(),
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
        // подпись / картинки можно добавить позже
      };
    }

    function saveCall() {
      const data = getFormData();
      if (!data.customer.firstName && !data.customer.cellPhone1) {
        alert('Нужно указать хотя бы First Name или Cell Phone.');
        return;
      }
      serviceCalls.unshift(data);
      saveToStorage();
      resetForm();
      renderList();
      renderSearchResults();
      showSection('list');
    }

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
      const name = (call.customer.firstName || '') + ' ' + (call.customer.lastName || '');
      const phone = call.customer.cellPhone1 || call.customer.cellPhone2 || call.customer.altPhone || '';
      const appliance =
        [call.appliance.applType, call.appliance.make, call.appliance.model].filter(Boolean).join(' ');
      return `
        <div class="list-item">
          <div class="list-top">
            <div>${escapeHtml(name || 'No name')}</div>
            <div class="tag">$${total.toFixed(2)}</div>
          </div>
          <div class="muted">${escapeHtml(phone)}</div>
          <div class="muted">${escapeHtml(appliance)}</div>
          <div class="muted">${escapeHtml(call.customer.address)}, ${escapeHtml(call.customer.city)}</div>
          <div class="muted">Created: ${date}</div>
          <div class="btn-row" style="margin-top:4px;">
            <button class="btn small" type="button" onclick="openInvoice(${call.id})">Invoice</button>
            <button class="btn small danger" type="button" onclick="deleteCall(${call.id})">Delete</button>
          </div>
        </div>
      `;
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
          const text = [
            c.customer.firstName,
            c.customer.lastName,
            c.customer.cellPhone1,
            c.customer.cellPhone2,
            c.customer.altPhone,
            c.customer.address,
            c.customer.city,
            c.appliance.applType,
            c.appliance.make,
            c.appliance.model,
            c.serviceInfo.techNotes,
            c.serviceInfo.complaint,
            c.serviceInfo.description
          ].join(' ').toLowerCase();
          return text.includes(q);
        });
      }
      if (!filtered.length) {
        container.innerHTML = '<div class="muted">Ничего не найдено.</div>';
        return;
      }
      container.innerHTML = filtered.map(createListItemHtml).join('');
    }

    /* INVOICE */
    function openInvoice(id) {
      const call = serviceCalls.find(c => c.id === id);
      if (!call) return;

      const fullName = (call.customer.firstName || '') + ' ' + (call.customer.lastName || '');
      const phone = call.customer.cellPhone1 || call.customer.cellPhone2 || call.customer.altPhone || '';
      const addressLine =
        [call.customer.address, call.customer.city, call.customer.state, call.customer.zip]
          .filter(Boolean).join(', ');

      const charges = call.charges || {};
      const total = charges.total || 0;

      const invoiceText =
`Home Appliance Service
Phone: (253)-213-1651

INVOICE #${call.id}
Date: ${new Date(call.createdAt || call.id).toLocaleDateString()}

Customer:
${fullName}
${addressLine}
Phone: ${phone}
E-mail: ${call.customer.email || ''}

Appliance:
Type: ${call.appliance.applType || ''}
Make: ${call.appliance.make || ''}
Model: ${call.appliance.model || ''}
Serial: ${call.appliance.serial || ''}
Mfg#: ${call.appliance.mfg || ''}

Service:
Complaint: ${call.serviceInfo.complaint || ''}
Description: ${call.serviceInfo.description || ''}
Tech Notes: ${call.serviceInfo.techNotes || ''}

Service Dates:
Purchased: ${call.dates.purchased || ''}
Started:   ${call.dates.started || ''}
Completed: ${call.dates.completed || ''}

Charges:
Parts Total: $${(charges.partsTotal || 0).toFixed(2)}
Flat Rate:   $${(charges.flatRate || 0).toFixed(2)}
Labor:       $${(charges.labor || 0).toFixed(2)}
Trip Charge: $${(charges.tripCharge || 0).toFixed(2)}
Shipping:    $${(charges.shipping || 0).toFixed(2)}
Tax:         $${(charges.tax || 0).toFixed(2)}
--------------------------
TOTAL:       $${total.toFixed(2)}

Thank you for your business!
Home Appliance Service
Phone: (253)-213-1651`;

      document.getElementById('invoiceText').value = invoiceText;
      document.getElementById('invoiceInfo').textContent =
        `Invoice for ${fullName || 'customer'} (${phone || 'no phone'})`;

      const smsPhone = (phone || '').replace(/[^\d+]/g, '');
      const smsLink = smsPhone
        ? `sms:${smsPhone}?&body=${encodeURIComponent(invoiceText)}`
        : '#';
      const anchor = document.getElementById('invoiceSmsLink');
      anchor.href = smsLink;
      anchor.style.pointerEvents = smsPhone ? 'auto' : 'none';
      anchor.style.opacity = smsPhone ? '1' : '0.5';

      showSection('invoice');
    }

    function copyInvoice() {
      const ta = document.getElementById('invoiceText');
      ta.select();
      ta.setSelectionRange(0, 99999);
      try {
        document.execCommand('copy');
        alert('Invoice скопирован в буфер обмена.');
      } catch (e) {
        alert('Не получилось автокопирование, скопируй вручную.');
      }
    }

    function printInvoice() {
      const text = document.getElementById('invoiceText').value;
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

    /* Signature pad */
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
      }, {passive:false});
      sigCanvas.addEventListener('touchmove', e => {
        e.preventDefault();
        const t = e.touches[0];
        const rect = sigCanvas.getBoundingClientRect();
        draw(t.clientX - rect.left, t.clientY - rect.top);
      }, {passive:false});
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

    // init
    loadCalls();
    showSection('new');
    window.addEventListener('load', initSignaturePad);
  </script>
</body>
</html>
