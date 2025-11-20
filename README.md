<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>HOME APPLIANCE SERVICE</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: #000000;
      color: #f6d9a5;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
    }

    a { color: inherit; text-decoration: none; }

    .page-wrap { max-width: 900px; width: 100%; }

    /* КАРТИНКА-ВИЗИТКА */
    .card {
      background: #050505;
      border-radius: 32px;
      padding: 40px 24px 32px;
      position: relative;
      border: 3px solid #f6d9a5;
      text-align: center;
      box-shadow: 0 18px 40px rgba(0,0,0,0.8);
    }

    .card-inner {
      max-width: 520px;
      margin: 0 auto;
    }

    .title {
      font-size: 26px;
      letter-spacing: 0.28em;
      text-transform: uppercase;
      margin-bottom: 32px;
    }

    .services {
      font-size: 16px;
      letter-spacing: 0.10em;
      margin-bottom: 30px;
    }

    /* декоративная линия как на карточке */
    .divider-wrap {
      margin: 0 auto 40px;
      max-width: 360px;
      position: relative;
      height: 24px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .divider-line {
      position: absolute;
      left: 0;
      right: 0;
      height: 2px;
      background: linear-gradient(90deg, transparent, #f6d9a5, transparent);
      opacity: 0.9;
    }

    .divider-pill {
      position: relative;
      width: 110px;
      height: 18px;
      border-radius: 999px;
      border: 2px solid #f6d9a5;
      background: #050505;
    }

    .phone-label {
      font-size: 16px;
      margin-bottom: 12px;
    }

    .phone {
      font-size: 28px;
      letter-spacing: 0.18em;
      margin-bottom: 30px;
    }

    .email-label {
      font-size: 16px;
      margin-bottom: 8px;
    }

    .email {
      font-size: 14px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      margin-bottom: 32px;
    }

    .btn-main-wrap {
      display: flex;
      justify-content: center;
    }

    .btn-main {
      background: #f6d9a5;
      color: #000;
      border-radius: 999px;
      padding: 16px 40px;
      min-width: 260px;
      font-size: 15px;
      font-weight: 600;
      letter-spacing: 0.20em;
      text-transform: uppercase;
      border: none;
      cursor: pointer;
      box-shadow: 0 14px 26px rgba(0,0,0,0.75);
    }

    .btn-main:active {
      transform: translateY(1px);
      box-shadow: 0 10px 18px rgba(0,0,0,0.75);
    }

    /* ФОРМА ЗАЯВКИ */
    .form-wrap {
      margin-top: 26px;
      padding: 24px 18px 18px;
      border-radius: 24px;
      border: 1px solid #f6d9a5;
      background: #020202;
    }

    .form-title {
      font-size: 18px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      text-align: center;
      margin-bottom: 18px;
    }

    form {
      display: grid;
      gap: 12px;
      text-align: left;
      max-width: 520px;
      margin: 0 auto;
    }

    label {
      font-size: 12px;
      margin-bottom: 4px;
      display: block;
    }

    .row-2 {
      display: grid;
      gap: 12px;
    }

    @media (min-width: 640px) {
      .row-2 {
        grid-template-columns: 1fr 1fr;
      }
    }

    input, select, textarea {
      width: 100%;
      padding: 9px 10px;
      border-radius: 10px;
      border: 1px solid #4a3820;
      background: #080808;
      color: #f6d9a5;
      font-size: 13px;
    }

    textarea {
      resize: vertical;
      min-height: 90px;
    }

    input::placeholder,
    textarea::placeholder {
      color: #8e7348;
    }

    .submit-row {
      margin-top: 4px;
      text-align: right;
    }

    .btn-send {
      background: #f6d9a5;
      color: #000;
      border-radius: 999px;
      padding: 10px 22px;
      font-size: 12px;
      font-weight: 600;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      border: none;
      cursor: pointer;
    }

    .btn-send:active {
      transform: translateY(1px);
    }

    .hidden { display: none; }
  </style>
</head>

<body>
  <div class="page-wrap">
    <div class="card">
      <div class="card-inner">

        <!-- ТОП КАК НА КАРТИНКЕ -->
        <div class="title">HOME APPLIANCE<br>SERVICE</div>

        <div class="services">
          Washers Dryers Ovens Refrigerators<br>
          Dishwashers Microwaves
        </div>

        <div class="divider-wrap">
          <div class="divider-line"></div>
          <div class="divider-pill"></div>
        </div>

        <div class="phone-label">Call / Text</div>
        <div class="phone">
          <a href="tel:+19734758336">973 475 8336</a>
        </div>

        <div class="email-label">Email:</div>
        <div class="email">
          <a href="mailto:homeapplianceservice444@gmail.com">
            HOMEAPPLIANCESERVICE444@GMAIL.COM
          </a>
        </div>

        <!-- КНОПКА -->
        <div class="btn-main-wrap">
          <button id="request-btn" class="btn-main" type="button">
            SEND REQUEST
          </button>
        </div>

        <!-- ФОРМА, ПОЯВЛЯЕТСЯ ПОСЛЕ КЛИКА -->
        <div id="request-form-wrap" class="form-wrap hidden">
          <div class="form-title">Service Request</div>

          <form action="mailto:homeapplianceservice444@gmail.com"
                method="POST"
                enctype="text/plain">
            <div class="row-2">
              <div>
                <label for="firstName">First name *</label>
                <input id="firstName" name="First name" required />
              </div>
              <div>
                <label for="lastName">Last name *</label>
                <input id="lastName" name="Last name" required />
              </div>
            </div>

            <div class="row-2">
              <div>
                <label for="brand">Appliance brand *</label>
                <input id="brand" name="Brand" required />
              </div>
              <div>
                <label for="type">Appliance type *</label>
                <select id="type" name="Type" required>
                  <option value="">Choose…</option>
                  <option>Washer</option>
                  <option>Dryer</option>
                  <option>Oven</option>
                  <option>Range</option>
                  <option>Refrigerator</option>
                  <option>Dishwasher</option>
                  <option>Microwave</option>
                  <option>Other</option>
                </select>
              </div>
            </div>

            <div>
              <label for="problem">Problem description *</label>
              <textarea id="problem" name="Problem" required></textarea>
            </div>

            <div class="row-2">
              <div>
                <label for="phone">Phone *</label>
                <input id="phone" name="Phone" required />
              </div>
              <div>
                <label for="email">Email (optional)</label>
                <input id="email" name="Customer email" type="email" />
              </div>
            </div>

            <div class="submit-row">
              <button class="btn-send" type="submit">Send</button>
            </div>
          </form>
        </div>

      </div>
    </div>
  </div>

  <script>
    const btn = document.getElementById("request-btn");
    const formWrap = document.getElementById("request-form-wrap");

    btn.addEventListener("click", () => {
      formWrap.classList.toggle("hidden");
      if (!formWrap.classList.contains("hidden")) {
        formWrap.scrollIntoView({ behavior: "smooth", block: "start" });
      }
    });
  </script>
</body>
</html>
