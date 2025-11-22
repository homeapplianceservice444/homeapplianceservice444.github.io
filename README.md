<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Service Manager - Home Appliance Service</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    :root {
      --bg: #f3e7d8;
      --card: #f5ecdf;
      --accent: #8a5a3b;
      --accent-light: #b07a4c;
      --accent-dark: #64402a;
      --text-main: #3c2a1e;
      --border: #d1bba4;
      --muted: #7c6a58;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    body {
      background: var(--bg);
      color: var(--text-main);
      padding: 12px;
    }

    .header {
      font-weight: 700;
      font-size: 26px;
      margin-bottom: 10px;
      color: #1e64c8; /* как на скрине */
    }

    .card {
      background: var(--card);
      border-radius: 10px;
      border: 1px solid var(--border);
      padding: 10px 12px 12px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.05);
      margin-bottom: 12px;
    }

    .card-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 8px 10px;
      border-radius: 8px;
      background: linear-gradient(90deg, var(--accent-dark), var(--accent));
      color: #fff;
      font-size: 14px;
      font-weight: 600;
      margin-bottom: 10px;
    }

    .card-header span {
      opacity: 0.85;
      font-weight: 500;
    }

    .btn {
      display: block;
      width: 100%;
      padding: 10px 12px;
      border-radius: 8px;
      border: none;
      font-size: 15px;
      text-align: left;
      margin-bottom: 8px;
      cursor: pointer;
      background: #ffffff;
      color: var(--text-main);
      border: 1px solid var(--border);
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .btn-main {
      background: var(--accent);
      color: #fff;
      border-color: var(--accent-dark);
      font-weight: 600;
      justify-content: center;
      text-align: center;
    }

    .btn-main:hover { background: var(--accent-dark); }

    .btn-icon {
      font-size: 16px;
      width: 18px;
      text-align: center;
    }

    .small-note {
      font-size: 11px;
      color: var(--muted);
      margin-top: 4px;
    }

    .section {
      display: none;
      margin-top: 8px;
    }

    .section.active { display: block; }

    label {
      font-size: 13px;
      margin-bottom: 4px;
      display: block;
      color: var(--muted);
    }

    input[type="text"],
    input[type="tel"],
    input[type="number"],
    textarea,
    select {
      width: 100%;
      padding: 7px 8px;
      border-radius: 7px;
      border: 1px solid var(--border);
      font-size: 14px;
      margin-bottom: 8px;
      background: #fdf8f1;
    }

    textarea { min-height: 70px; resize: vertical; }

    .row {
      display: flex;
      gap: 8px;
    }

    .row > div { flex: 1; }

    .btn-row {
      display: flex;
      gap: 8px;
      margin-top: 4px;
      flex-wrap: wrap;
    }

    .btn-sm {
      flex: 1;
      padding: 7px 8px;
      font-size: 13px;
      text-align: center;
      justify-content: center;
    }

    .btn-danger {
      background: #b14a3d;
      border-color: #8c372e;
      color: #fff;
    }

    .btn-secondary {
      background: #e7d6c4;
      border-color: #c8b19b;
    }

    .list {
      max-height: 400px;
      overflow-y: auto;
      margin-top: 6px;
    }

    .list-item {
      border-radius: 8px;
      border: 1px solid var(--border);
      padding: 8px 9px;
      background: #fff;
      margin-bottom: 6px;
      font-size: 13px;
    }

    .list-top {
      display: flex;
      justify-content: space-between;
      font-weight: 600;
      margin-bottom: 3px;
    }

    .tag {
      display: inline-block;
      padding: 1px 6px;
      border-radius: 999px;
      font-size: 11px;
      border: 1px solid var(--border);
      color: var(--muted);
    }

    .search-input {
      margin-bottom: 6px;
    }

    .muted { color: var(--muted); font-size: 12px; }

    .invoice-textarea {
      font-family: "SF Mono", Menlo, Monaco, Consolas, "Courier New", monospace;
      font-size: 12px;
      white-space: pre-wrap;
    }

    .footer-note {
      font-size: 11px;
      color: var(--muted);
      margin-top: 10px;
      text-align: center;
    }

    @media (min-width: 768px) {
      body {
        max-width: 600px;
        margin: 0 auto;
      }
    }
  </style>
</head>
<body>

  <div class="header">homeapplianceservice444</div>

  <div class="card">
    <div class="card-header">
      <div>SERVICE MANAGER</div>
      <div><span>Welcome: MAX</span></div>
    </div>

    <!-- MAIN MENU -->
    <div id="mainMenu">
      <button class="btn btn-main" onclick="showSection('new-call')">
        <span class="btn-icon">＋</span>
        <span>New Service Call</span>
      </button>
      <button class="btn" onclick="showSection('list')">
        <span class="btn-icon">📋</span>
        <span>Service List</span>
      </button>
      <button class="btn" onclick="showSection('search')">
        <span class="btn-icon">🔍</span>
        <span>Search</span>
      </button>
      <div class="small-note">
        Всё хранится только в твоём браузере (localStorage). Можно использовать оффлайн.
      </div>
    </div>

    <!-- NEW SERVICE CALL -->
    <div id="section-new-call" class="section">
      <h3 style="font-size:15px;margin-bottom:6px;">New Service Call</h3>

      <div class="row">
        <div>
          <label>Customer Name</label>
          <input type="text" id="customerName">
        </div>
        <div>
          <label>Phone</label>
          <input type="tel" id="customerPhone" placeholder="+1 (___) ___-____">
        </div>
      </div>

      <label>Address</label>
      <input type="text" id="customerAddress" placeholder="Street, Apt, City">

      <div class="row">
        <div>
          <label>Appliance</label>
          <input type="text" id="applianceType" placeholder="Washer, Dryer...">
        </div>
        <div>
          <label>Brand</label>
          <input type="text" id="applianceBrand" placeholder="LG, Samsung...">
        </div>
      </div>

      <label>Model</label>
      <input type="text" id="applianceModel">

      <label>Problem Description</label>
      <textarea id="problemDesc"></textarea>

      <div class="row">
        <div>
          <label>Labor ($)</label>
          <input type="number" id="laborPrice" step="0.01">
        </div>
        <div>
          <label>Parts ($)</label>
          <input type="number" id="partsPrice" step="0.01">
        </div>
      </div>

      <label>Status</label>
      <select id="status">
        <option value="Pending">Pending</option>
        <option value="In progress">In progress</option>
        <option value="Completed">Completed</option>
        <option value="Cancelled">Cancelled</option>
      </select>

      <div class="btn-row">
        <button class="btn btn-main btn-sm" onclick="saveCall()">Save Call</button>
        <button class="btn btn-secondary btn-sm" onclick="cancelForm()">Cancel</button>
      </div>
    </div>

    <!-- SERVICE LIST -->
    <div id="section-list" class="section">
      <h3 style="font-size:15px;margin-bottom:4px;">Service List</h3>
      <div class="muted">Последние вызовы (сохраняются в браузере).</div>
      <div id="listContainer" class="list"></div>
    </div>

    <!-- SEARCH -->
    <div id="section-search" class="section">
      <h3 style="font-size:15px;margin-bottom:4px;">Search</h3>
      <input id="searchQuery" class="search-input" type="text"
             placeholder="Имя, телефон, адрес, appliance, модель..."
             oninput="renderSearchResults()">
      <div id="searchResults" class="list"></div>
    </div>

    <!-- INVOICE -->
    <div id="section-invoice" class="section">
      <h3 style="font-size:15px;margin-bottom:4px;">Invoice</h3>
      <div class="muted" id="invoiceInfo"></div>
      <textarea id="invoiceText" class="invoice-textarea"></textarea>

      <div class="btn-row">
        <button class="btn btn-main btn-sm" onclick="copyInvoice()">Copy Invoice</button>
        <a id="invoiceSmsLink" class="btn btn-secondary btn-sm" href="#" target="_blank">
          SMS to Customer
        </a>
        <button class="btn btn-secondary btn-sm" onclick="printInvoice()">Print / PDF</button>
      </div>

      <div class="btn-row" style="margin-top:6px;">
        <button class="btn btn-secondary btn-sm" onclick="showSection('list')">Back to List</button>
      </div>
    </div>

    <div class="footer-note">
      Home Appliance Service • Phone: (253)-213-1651
    </div>
  </div>

  <script>
    const STORAGE_KEY = 'serviceCalls_v2';

    let serviceCalls = [];

    function loadCalls() {
      try {
        const raw = localStorage.getItem(STORAGE_KEY);
        if (raw) serviceCalls = JSON.parse(raw);
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
      const sections = ['new-call','list','search','invoice'];
      sections.forEach(s => {
        const el = document.getElementById('section-' + s);
        if (!el) return;
        el.classList.toggle('active', s === name);
      });

      // возврат в меню, если name пустой
      if (!name) {
        document.querySelector('.header');
      }
    }

    function cancelForm() {
      clearForm();
      hideAllSections();
    }

    function hideAllSections() {
      ['new-call','list','search','invoice'].forEach(s => {
        const el = document.getElementById('section-' + s);
        if (el) el.classList.remove('active');
      });
    }

    function getFormData() {
      return {
        id: Date.now(),
        createdAt: new Date().toISOString(),
        customerName: document.getElementById('customerName').value.trim(),
        customerPhone: document.getElementById('customerPhone').value.trim(),
        customerAddress: document.getElementById('customerAddress').value.trim(),
        applianceType: document.getElementById('applianceType').value.trim(),
        applianceBrand: document.getElementById('applianceBrand').value.trim(),
        applianceModel: document.getElementById('applianceModel').value.trim(),
        problemDesc: document.getElementById('problemDesc').value.trim(),
        laborPrice: parseFloat(document.getElementById('laborPrice').value) || 0,
        partsPrice: parseFloat(document.getElementById('partsPrice').value) || 0,
        status: document.getElementById('status').value
      };
    }

    function clearForm() {
      ['customerName','customerPhone','customerAddress','applianceType',
       'applianceBrand','applianceModel','problemDesc','laborPrice','partsPrice']
        .forEach(id => document.getElementById(id).value = '');
      document.getElementById('status').value = 'Pending';
    }

    function saveCall() {
      const data = getFormData();
      if (!data.customerName && !data.customerPhone) {
        alert('Нужно указать хотя бы имя или телефон.');
        return;
      }
      serviceCalls.unshift(data);
      saveToStorage();
      clearForm();
      renderList();
      renderSearchResults();
      showSection('list');
    }

    function renderList() {
      const container = document.getElementById('listContainer');
      if (!container) return;
      if (!serviceCalls.length) {
        container.innerHTML = '<div class="muted">Пока нет сохранённых вызовов.</div>';
        return;
      }
      container.innerHTML = serviceCalls.map(call => createListItemHtml(call)).join('');
    }

    function createListItemHtml(call) {
      const date = new Date(call.createdAt || call.id).toLocaleString();
      const total = (Number(call.laborPrice) || 0) + (Number(call.partsPrice) || 0);
      return `
        <div class="list-item" data-id="${call.id}">
          <div class="list-top">
            <div>${escapeHtml(call.customerName || 'No name')}</div>
            <div class="tag">${escapeHtml(call.status || 'Pending')}</div>
          </div>
          <div class="muted">${escapeHtml(call.customerPhone || '')}</div>
          <div class="muted">${escapeHtml(call.applianceType || '')} ${escapeHtml(call.applianceBrand || '')} ${escapeHtml(call.applianceModel || '')}</div>
          <div class="muted">${escapeHtml(call.customerAddress || '')}</div>
          <div class="muted">Created: ${date} • Total: $${total.toFixed(2)}</div>
          <div class="btn-row" style="margin-top:4px;">
            <button class="btn btn-secondary btn-sm" onclick="openInvoice(${call.id})">Invoice</button>
            <button class="btn btn-danger btn-sm" onclick="deleteCall(${call.id})">Delete</button>
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
            c.customerName, c.customerPhone, c.customerAddress,
            c.applianceType, c.applianceBrand, c.applianceModel,
            c.problemDesc, c.status
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

    function openInvoice(id) {
      const call = serviceCalls.find(c => c.id === id);
      if (!call) return;

      const labor = Number(call.laborPrice) || 0;
      const parts = Number(call.partsPrice) || 0;
      const total = labor + parts;
      const date = new Date(call.createdAt || call.id);

      const invoiceText =
`Home Appliance Service
Phone: (253)-213-1651

INVOICE #${call.id}
Date: ${date.toLocaleDateString()}

Customer: ${call.customerName || ''}
Phone: ${call.customerPhone || ''}
Address: ${call.customerAddress || ''}

Appliance: ${call.applianceType || ''} ${call.applianceBrand || ''} ${call.applianceModel || ''}
Problem: ${call.problemDesc || ''}

Labor: $${labor.toFixed(2)}
Parts: $${parts.toFixed(2)}
-------------------------
TOTAL: $${total.toFixed(2)}

Thank you for your business!`;

      document.getElementById('invoiceText').value = invoiceText;
      document.getElementById('invoiceInfo').textContent =
        `Invoice for ${call.customerName || 'customer'} (${call.customerPhone || 'no phone'})`;

      const phone = (call.customerPhone || '').replace(/[^\d+]/g, '');
      const smsLink = phone
        ? `sms:${phone}?&body=${encodeURIComponent(invoiceText)}`
        : '#';
      const smsAnchor = document.getElementById('invoiceSmsLink');
      smsAnchor.href = smsLink;
      smsAnchor.style.pointerEvents = phone ? 'auto' : 'none';
      smsAnchor.style.opacity = phone ? '1' : '0.5';

      showSection('invoice');
    }

    function copyInvoice() {
      const ta = document.getElementById('invoiceText');
      ta.select();
      ta.setSelectionRange(0, 99999);
      try {
        document.execCommand('copy');
        alert('Invoice скопирован в буфер.');
      } catch (e) {
        alert('Не получилось автоматически скопировать. Скопируй вручную.');
      }
    }

    function printInvoice() {
      const text = document.getElementById('invoiceText').value;
      const win = window.open('', '_blank');
      win.document.write(`
        <html>
        <head>
          <title>Invoice</title>
          <meta charset="UTF-8">
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

    function escapeHtml(str) {
      if (!str) return '';
      return String(str)
        .replace(/&/g, '&amp;')
        .replace(/</g, '&lt;')
        .replace(/>/g, '&gt;')
        .replace(/"/g, '&quot;')
        .replace(/'/g, '&#039;');
    }

    // старт
    loadCalls();
  </script>

</body>
</html>
