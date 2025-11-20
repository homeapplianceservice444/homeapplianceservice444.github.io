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
      background: #111;
      color: #f2d6a4;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
    }

    a { color: inherit; text-decoration: none; }

    .page-wrap { max-width: 960px; width: 100%; }

    .card {
      background: #000;
      border-radius: 18px;
      padding: 28px 24px 30px;
      position: relative;
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.7);
      border: 2px solid #0a407c;
    }

    .card::before {
      content: "";
      position: absolute;
      inset: 14px;
      border-radius: 14px;
      border: 2px solid #f2d6a4;
      pointer-events: none;
    }

    .card-inner { text-align: center; position: relative; }

    .title {
      font-size: 24px;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      margin-bottom: 12px;
    }

    .services {
      font-size: 14px;
      letter-spacing: 0.08em;
      margin-bottom: 26px;
    }

    .divider {
      margin: 0 auto 26px;
      height: 2px;
      max-width: 320px;
      background: linear-gradient(90deg, transparent, #f2d6a4, transparent);
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

    .phone-label { font-size: 14px; margin-bottom: 4px; }
    .phone { font-size: 20px; letter-spacing: 0.12em; margin-bottom: 20px; }

    .email-label { font-size: 13px; margin-bottom: 4px; }
    .email { font-size: 13px; letter-spacing: 0.06em; text-transform: uppercase; }

    .btn-row { margin-top: 26px; display: flex; justify-content: center; }

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

    .btn-primary:active { transform: translateY(1px); }

    /* === ФОРМА === */
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

    form { display: grid; gap: 10px; text-align: left; }

    label { font-size: 12px; margin-bottom: 2px; display: block; }

    .row-2 { display: grid; gap: 10px; }
    @media (min-width: 640px) { .row-2 { grid-template-columns: 1fr 1fr; } }

    input, select, textarea {
      width: 100%; padding: 8px 9px; border-radius: 8px;
      border: 1px solid #43351e; background: #111; color: #f2d6a4;
    }

    textarea { resize: vertical; min-height: 80px; }

    .submit-row { text-align: right; }

    .btn-send {
      background: #f2d6a4; color: #000; border-radius: 999px;
      padding: 9px 20px; font-size: 12px; font-weight: 600;
      border: none; cursor: pointer;
    }

    .hidden { display: none; }
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
        <div class="phone"><a href="tel:+12532131651">253 213 1651</a></div>

        <div class="email-label">Email:</div>
        <div class="email">
          
            
          
        </div>

        <div class="btn-row">
          <button id="request-btn" class="btn-primary" type="button">SEND REQUEST</button>
        </div>

        <!-- Форма -->
        <div id="request-form-wrap" class="form-wrap hidden">
          <div class="form-title">Service Request</div>

          <form action="mailto:homeapplianceservice444@gmail.com" method="POST" enctype="text/plain">
            <div class="row-2">
              <div>
                <label>First name *</label>
                <input name="First name" required />
              </div>
              <div>
                <label>Last name *</label>
                <input name="Last name" required />
              </div>
            </div>

            <div class="row-2">
              <div>
                <label>Appliance brand *</label>
                <input name="Brand" required />
              </div>
              <div>
                <label>Appliance type *</label>
                <select name="Type" required>
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
              <label>Problem description *</label>
              <textarea name="Problem" required></textarea>
            </div>

            <div class="row-2">
              <div>
                <label>Phone *</label>
                <input name="Phone" required />
              </div>
              <div>
                <label>Email (optional)</label>
                <input name="Customer email" type="email" />
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
    const form = document.getElementById("request-form-wrap");
    btn.addEventListener("click", () => form.classList.toggle("hidden"));
  </script>
</body>
</html>
