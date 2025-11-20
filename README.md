<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Home Appliance Service</title>

  <!-- Шрифт похожий на визитку -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&display=swap" rel="stylesheet">

  <style>
    :root {
      --gold: #d9b87c;
      --gold-soft: #caa569;
      --gold-dark: #8e6b3e;
      --bg: #000000;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      min-height: 100vh;
      background: var(--bg);
      color: var(--gold);
      font-family: "Playfair Display", serif;
      display: flex;
      justify-content: center;
    }

    .page {
      width: 100%;
      max-width: 720px;
      padding: 40px 16px 60px;
      text-align: center;
    }

    /* ===== ВИЗИТКА ===== */

    .title {
      font-size: 30px;
      letter-spacing: 0.18em;
      margin-bottom: 24px;
    }

    .subtitle {
      font-size: 18px;
      letter-spacing: 0.06em;
      margin-bottom: 26px;
    }

    /* декоративная линия как на визитке */
    .ornament-wrap {
      margin: 0 auto 32px;
      width: 100%;
      max-width: 640px;
      position: relative;
      height: 24px;
    }

    .ornament-wrap::before,
    .ornament-wrap::after {
      content: "";
      position: absolute;
      top: 50%;
      width: 43%;
      height: 1px;
      background: linear-gradient(
        90deg,
        transparent 0,
        var(--gold) 30%,
        var(--gold-soft) 70%,
        transparent 100%
      );
    }

    .ornament-wrap::before { left: 0; }
    .ornament-wrap::after  { right: 0; }

    .ornament {
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      font-size: 20px;
    }

    .phone {
      font-size: 22px;
      margin-bottom: 10px;
    }

    .email {
      font-size: 18px;
      margin-bottom: 32px;
    }

    .main-btn {
      display: inline-block;
      padding: 14px 60px;
      border-radius: 10px;
      border: 1px solid var(--gold-dark);
      background: linear-gradient(180deg, var(--gold) 0, var(--gold-soft) 55%, var(--gold-dark) 100%);
      color: #1d1307;
      font-size: 20px;
      font-weight: 600;
      letter-spacing: 0.06em;
      cursor: pointer;
      text-transform: uppercase;
    }

    .main-btn:active {
      transform: translateY(1px);
      filter: brightness(0.97);
    }

    /* ===== ФОРМА ЗАПРОСА ===== */

    .form-block {
      margin-top: 40px;
      border-radius: 18px;
      border: 1px solid var(--gold-soft);
      padding: 22px 16px 26px;
      background: #050404;
      display: none; /* по умолчанию скрыта */
      text-align: left;
    }

    .form-title {
      text-align: center;
      font-size: 18px;
      letter-spacing: 0.16em;
      margin-bottom: 8px;
    }

    .form-subtitle {
      text-align: center;
      font-size: 12px;
      color: #c7aa7e;
      margin-bottom: 18px;
    }

    .field {
      margin-bottom: 12px;
    }

    label {
      display: block;
      font-size: 13px;
      color: #f0dcba;
      margin-bottom: 4px;
    }

    input, select, textarea {
      width: 100%;
      border-radius: 8px;
      border: 1px solid #4b3824;
      background: #111;
      color: var(--gold);
      padding: 10px 11px;
      font-size: 14px;
      outline: none;
      font-family: inherit;
    }

    input:focus, select:focus, textarea:focus {
      border-color: var(--gold);
      box-shadow: 0 0 0 1px rgba(217,184,124,0.4);
    }

    textarea {
      min-height: 100px;
      resize: vertical;
    }

    .submit-btn {
      margin-top: 16px;
      width: 100%;
      border-radius: 10px;
      border: 1px solid var(--gold-dark);
      padding: 12px;
      font-size: 16px;
      font-weight: 600;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      background: linear-gradient(180deg, var(--gold) 0, var(--gold-soft) 55%, var(--gold-dark) 100%);
      color: #1d1307;
      cursor: pointer;
    }

    .submit-btn:active {
      transform: translateY(1px);
      filter: brightness(0.97);
    }

    @media (max-width: 600px) {
      .title { font-size: 24px; letter-spacing: 0.14em; }
      .subtitle { font-size: 14px; }
      .phone { font-size: 18px; }
      .email { font-size: 14px; }
      .main-btn { width: 100%; padding: 14px 10px; }
    }
  </style>
</head>
<body>
  <div class="page">

    <!-- ВЕРХ КАК ВИЗИТКА -->
    <section>
      <div class="title">HOME APPLIANCE SERVICE</div>

      <div class="subtitle">
        Washers Dryers Ovens Refrigerators Dishwashers
      </div>

      <div class="ornament-wrap">
        <div class="ornament">❧</div>
      </div>

      <div class="phone">call/text (253) 213-1651</div>
      <div class="email">homeapplianceservice444@gmail.com</div>

      <button class="main-btn" onclick="openForm()">SEND REQUEST</button>
    </section>

    <!-- ФОРМА ЗАПРОСА -->
    <section id="request-form" class="form-block">
      <div class="form-title">SEND REQUEST</div>
      <div class="form-subtitle">
        Leave your information and we will confirm your appointment as soon as possible.
      </div>

      <form onsubmit="sendEmail(event)">
        <div class="field">
          <label for="name">Full Name *</label>
          <input id="name" name="Name" required>
        </div>

        <div class="field">
          <label for="phone">Phone Number *</label>
          <input id="phone" name="Phone" required>
        </div>

        <div class="field">
          <label for="address">Address (City, ZIP) *</label>
          <input id="address" name="Address" required>
        </div>

        <div class="field">
          <label for="appliance">Appliance Type *</label>
          <select id="appliance" name="Appliance" required>
            <option value="" disabled selected>Select</option>
            <option>Washer</option>
            <option>Dryer</option>
            <option>Refrigerator</option>
            <option>Oven</option>
            <option>Dishwasher</option>
            <option>Microwave</option>
          </select>
        </div>

        <div class="field">
          <label for="problem">Description of Problem *</label>
          <textarea id="problem" name="Problem" required></textarea>
        </div>

        <button type="submit" class="submit-btn">SEND REQUEST</button>
      </form>
    </section>

  </div>

  <script>
    // показать блок формы
    function openForm() {
      const formSection = document.getElementById('request-form');
      formSection.style.display = 'block';
      formSection.scrollIntoView({ behavior: 'smooth' });
    }

    // отправка через mailto
    function sendEmail(event) {
      event.preventDefault();

      const name = document.getElementById('name').value;
      const phone = document.getElementById('phone').value;
      const address = document.getElementById('address').value;
      const appliance = document.getElementById('appliance').value;
      const problem = document.getElementById('problem').value;

      const subject = encodeURIComponent('Service Request');
      const body = encodeURIComponent(
        'Name: ' + name + '\n' +
        'Phone: ' + phone + '\n' +
        'Address: ' + address + '\n' +
        'Appliance: ' + appliance + '\n' +
        'Problem: ' + problem
      );

      window.location.href = 'mailto:homeapplianceservice444@gmail.com?subject=' +
        subject + '&body=' + body;
    }
  </script>
</body>
</html>
