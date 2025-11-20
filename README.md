<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Home Appliance Service</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: #020307;
      color: #f5e3b8;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
    }

    .card {
      background: #050509;
      border-radius: 18px;
      border: 2px solid #0070ff; /* внешняя синяя рамка можно убрать */
      padding: 26px 20px 28px;
      max-width: 640px;
      width: 100%;
      position: relative;
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.7);
    }

    /* внутренняя золотая рамка как на визитке */
    .card-inner {
      border-radius: 14px;
      border: 2px solid #d8b26a;
      padding: 26px 18px 22px;
      text-align: center;
      position: relative;
    }

    .title {
      font-size: 22px;
      letter-spacing: 0.24em;
      text-transform: uppercase;
      color: #f4e1b2;
      margin-bottom: 18px;
    }

    .services {
      font-size: 14px;
      letter-spacing: 0.08em;
      text-transform: capitalize;
      color: #f0dab0;
      margin-bottom: 26px;
    }

    .divider {
      height: 1px;
      background: linear-gradient(90deg, transparent, #d8b26a, transparent);
      margin: 16px auto 10px;
      max-width: 360px;
      position: relative;
    }

    .divider::after {
      content: "✦";
      position: absolute;
      top: -10px;
      left: 50%;
      transform: translateX(-50%);
      background: #050509;
      padding: 0 12px;
      font-size: 16px;
      color: #d8b26a;
    }

    .call-text {
      font-size: 15px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-top: 16px;
      margin-bottom: 4px;
      color: #f3dfb4;
    }

    .phone {
      font-size: 18px;
      letter-spacing: 0.18em;
    }

    .phone a {
      color: inherit;
      text-decoration: none;
    }

    .label-email {
      margin-top: 20px;
      font-size: 12px;
      letter-spacing: 0.22em;
      text-transform: uppercase;
      color: #f0dab0;
    }

    .email {
      margin-top: 6px;
