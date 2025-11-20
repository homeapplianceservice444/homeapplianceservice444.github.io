<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>HOME APPLIANCE SERVICE</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: #111;
      color: #f2d6a4;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .page-wrap {
      max-width: 960px;
      width: 100%;
    }

    .card {
      background: #000;
      border-radius: 18px;
      padding: 28px 24px 30px;
      position: relative;
      box-shadow:
        0 18px 40px rgba(0, 0, 0, 0.7),
        0 0 0 2px #0a407c;
    }

    /* внутренняя золотая рамка как на визитке */
    .card::before {
      content: "";
      position: absolute;
      inset: 14px;
      border-radius: 14px;
      border: 2px solid #f2d6a4;
      pointer-events: none;
    }

    .card-inner {
      position: relative;
      text-align: center;
    }

    .title {
      font-size: 24px;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      margin-bottom: 12px;
    }

    .services {
      font-size: 14px;
      letter-spacing: 0.08em;
      text-transform: capitalize;
      margin-bottom: 26px;
    }

    /* декоративная линия */
    .divider {
      margin: 0 auto 26px;
      height: 2px;
      max-width: 320px;
      background: linear-gradient(
        90deg,
        transparent,
        #f2d6a4,
        transparent
      );
      position: relative;
    }

    .divider::before {
      content: "";
      position: absolute;
      width: 60px;
      height: 12px;
      border-radius: 999px;
      border-top: 2px solid #f2d6a4;
      border-bottom: 2px solid #f2d6a4;
      left: 50%;
      transform: translateX(-50%);
      top: -5px;
    }

    .phone-label {
      font-size: 14px;
      margin-bottom: 4px;
    }

    .phone {
      font-size: 20px;
      letter-spacing: 0.12em;
      margin-bottom: 20px;
    }

    .email-label {
      font-size: 13px;
      margin-bottom: 4px;
    }

    .email {
      font-size: 13px;
      letter-spacing: 0.06em;
      text-transform: uppercase;
    }

    .btn-row {
      margin-top: 26px;
      display: flex;
      justify-content: center;
    }

    .btn-primary {
      background: #f2d6a4;
      color: #000;
      border-radius: 999px;
      padding: 10px 24px;
      font-size: 13px;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      border: none;
      cursor: pointer;
      box-shadow: 0 12px 20px rgba(0, 0, 0, 0.7);
    }

    .btn-primary:active {
      transform: translateY(1px);
      box-shadow: 0 8px 14px rgba(0, 0, 0, 0.7);
    }

    /* ФОРМА ЗАЯВКИ */

    .form-wrap {
      margin-top: 28px;
      background: #050505;
      border-radius: 16px;
      border: 1px solid #f2d6a4;
      padding: 18px 16px 18px;
    }

    .form-title {
      font-size: 16px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 10px;
    }

    .form-note {
      font-size: 12px;
      color: #d0b98b;
      margin-bottom: 14px;
    }

    form {
      display: grid;
      gap: 10px;
      text-align: left;
    }

    label {
      font-size: 12px;
      margin-bottom: 2px;
      display: block;
    }

    .row-2 {
      display: grid;
      gap: 10px;
    }

    @media (min-width: 640px) {
      .row-2 {
        grid-template-columns: 1fr 1fr;
      }
    }

    input,
    select,
    textarea {
      width: 100%;
      padding: 8px 9px;
      border-radius: 8px;
      border: 1px solid #43351e;
      background: #111;
      color: #f2d6a4;
      font-size: 13px;
    }

    input::placeholder,
    textarea::placeholder {
      color: #806a40;
    }

    textarea {
      resize: vertical;
      min-height: 80px;
    }

    .submit-row {
      margin-top: 6px;
      text-align: right;
    }

    .btn-send {
      background: #f2d6a4;
      color: #000;
      border-radius: 999px;
      padding: 9px 20px;
      font-size: 12px;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      border: none;
      cursor: pointer;
    }

    .btn-send:active {
      transform: translateY(1px);
    }

    .smallprint {
      margin-top: 8px;
      font-size: 10px;
      color: #c3aa7b;
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>
  <div class="page-wrap">
    <div class="card">
      <div class="card-inner">
        <div class="title">HOME APPLIANCE SERVICE</div>

        <div class="services">
          Washers Dryers Ovens Refrigerators Dishwashers Microwaves
        </div>

        <div class="divider"></div>

        <div class="phone-label">Call / Text</div>
        <div class="phone">
          <a href="tel:+19734758336">973&nbsp;475&nbsp;8336</a>
        </div>

        <div class="email-label">Email:</div>
        <div class="email">
          <a href="mailto:homeapplianceservice444@gmail.com">
            homeapplianceservice444@gmail.com
          </a>
        </div>

        <div class="btn-row">
          <button id="request-btn" class="btn-primary" type="button">
            Send Request
          </button>
        </div>

        <!-- Форма заявки (по умолчанию скрыта) -->
        <div id="request-form-wrap" class="form-wrap hidden">
          <div class="form-title">Service Request</div>
          <div class="form-note">
            Заполните форму, и черновик письма откроется в вашем почтовом приложении.
          </div>

          <!-- mailto-отправка на нужную почту -->
          <form
            action="mailto:homeapplianceservice444@gmail.com"
            method="POST"
            enctype="text/plain"
          >
            <div class="row-2">
              <div>
                <label for="firstName">First name *</label>
                <input
                  id="firstName"
                  name="First name"
                  type="text"
                  required
                  placeholder="John"
                />
              </div>
              <div>
                <label for="lastName">Last name *</label>
                <input
                  id="lastName"
                  name="Last name"
                  type="text"
                  required
                  placeholder="Doe"
                />
              </div>
            </div>

            <div class="row-2">
              <div>
                <label for="brand">Appliance brand *</label>
                <input
                  id="brand"
                  name="Brand"
                  type="text"
                  required
                  placeholder="Samsung, LG, GE..."
                />
              </div>
              <div>
                <label for="type">Appliance type *</label>
                <select id="type" name="Appliance type" required>
                  <option value="">Choose…</option>
                  <option>Washer</option>
                  <option>Dryer</option>
                  <option>Washer &amp; Dryer</option>
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
              <textarea
                id="problem"
                name="Problem"
                required
                placeholder="Does not start, makes noise, not cooling, error code, etc."
              ></textarea>
            </div>

            <div class="row-2">
              <div>
                <label for="phone">Phone number *</label>
                <input
                  id="phone"
                  name="Phone"
                  type="tel"
                  required
                  placeholder="(___) ___-____"
                />
              </div>
              <div>
                <label for="email">Email (optional)</label>
                <input
                  id="email"
                  name="Customer email"
                  type="email"
                  placeholder="you@example.com"
                />
              </div>
            </div>

            <div>
              <label for="contactPref">Preferred contact method</label>
              <select id="contactPref" name="Contact preference">
                <option>Call</option>
                <option>Text</option>
                <option>Call or text</option>
              </select>
            </div>

            <div class="submit-row">
              <button class="btn-send" type="submit">Send</button>
            </div>

            <div class="smallprint">
              * Required fields. После нажатия «Send» ваш почтовый клиент
              откроет письмо на
              <strong>homeapplianceservice444@gmail.com</strong> с текстом заявки.
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
