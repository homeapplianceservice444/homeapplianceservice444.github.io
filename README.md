<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Home Appliance Service</title>

<style>
    body {
        margin: 0;
        padding: 0;
        background: #000;
        font-family: "Times New Roman", serif;
        color: #d8b07f;
        text-align: center;
    }

    .container {
        max-width: 650px;
        margin: auto;
        padding: 25px;
    }

    h1 {
        font-size: 32px;
        font-weight: 600;
        margin-top: 20px;
        letter-spacing: 2px;
    }

    .subtitle {
        margin-top: 15px;
        font-size: 18px;
        line-height: 28px;
    }

    .line {
        width: 90%;
        height: 1px;
        background: linear-gradient(to right,
            transparent,
            #d8b07f,
            transparent);
        margin: 25px auto;
    }

    .contact {
        font-size: 22px;
        margin-top: 10px;
        margin-bottom: 5px;
    }

    a {
        color: #d8b07f;
    }

    form {
        margin-top: 35px;
        border: 1px solid #d8b07f;
        padding: 25px;
        border-radius: 12px;
    }

    input, select, textarea {
        width: 100%;
        background: #111;
        border: 1px solid #d8b07f;
        border-radius: 8px;
        padding: 12px;
        margin-top: 12px;
        font-size: 16px;
        color: #d8b07f;
    }

    textarea {
        height: 120px;
        resize: none;
    }

    .submit-btn {
        width: 100%;
        background: #d1a565;
        border: none;
        padding: 15px;
        font-size: 20px;
        color: black;
        border-radius: 10px;
        margin-top: 20px;
        cursor: pointer;
        font-weight: bold;
    }

</style>
</head>

<body>

<div class="container">

    <h1>HOME APPLIANCE SERVICE</h1>

    <div class="subtitle">
        Washers • Dryers • Ovens • Refrigerators • Dishwashers • Microwaves
    </div>

    <div class="line"></div>

    <div class="contact">call/text (253) 213-1651</div>
    <a href="mailto:homeapplianceservice444@gmail.com">
        homeapplianceservice444@gmail.com
    </a>

    <!-- ФОРМА -->
    <form action="https://formspree.io/f/xwpkljlo" method="POST">

        <input type="text" name="Full Name" placeholder="Full Name" required>

        <input type="text" name="Phone" placeholder="Phone Number" required>

        <input type="text" name="Address" placeholder="Address (City, ZIP)" required>

        <select name="Appliance Type" required>
            <option value="" disabled selected>Select Appliance Type</option>
            <option>Washer</option>
            <option>Dryer</option>
            <option>Refrigerator</option>
            <option>Oven</option>
            <option>Dishwasher</option>
            <option>Microwave</option>
        </select>

        <textarea name="Problem Description" placeholder="Description of Problem"></textarea>

        <button class="submit-btn" type="submit">SEND REQUEST</button>

    </form>

</div>

</body>
</html>
