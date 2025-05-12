Jo# Khawabo-ki-Tabeer
<!DOCTYPE html>
<html lang="ur" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>خوابوں کی تعبیر</title>
  <style>
    body {
      font-family: 'Noto Nastaliq Urdu', serif;
      background: #f9f9f9;
      color: #222;
      padding: 20px;
      max-width: 800px;
      margin: auto;
    }
    h1 { text-align: center; }
    input[type="text"] {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      margin-bottom: 20px;
      font-size: 18px;
    }
    .result {
      background: #fff;
      padding: 15px;
      border: 1px solid #ddd;
      border-radius: 5px;
    }
    .hidden { display: none; }
    form {
      margin-top: 20px;
      background: #fff;
      padding: 15px;
      border: 1px solid #ddd;
      border-radius: 5px;
    }
    label { display: block; margin-top: 10px; }
    textarea, input[type="text"] { width: 100%; }
    button {
      margin-top: 10px;
      padding: 10px 15px;
      font-size: 16px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
    }
  </style>
</head>
<body>
  <h1>خوابوں کی تعبیر</h1>
  <input type="text" id="search" placeholder="اپنا خواب تلاش کریں...">
  <div class="result" id="result"></div>

  <form id="contactForm" class="hidden">
    <h3>تعبیر نہ ملنے پر، رابطہ کریں</h3>
    <label>آپ کا نام:</label>
    <input type="text" id="name" required>
    <label>خواب کی تفصیل:</label>
    <textarea id="dream" required></textarea>
    <label>رابطہ نمبر یا ای میل:</label>
    <input type="text" id="contact" required>
    <button type="submit">ارسال کریں</button>
  </form>

  <script>
    const dreams = {
      "پتھر": "سخت دل لوگوں یا مشکلات کی علامت۔ صبر، آزمائش یا رکاوٹوں کی طرف اشارہ۔",
      "دودھ": "اگر کوئی عورت جگ سے دودھ پلائے تو خواب دیکھنے والا اس کا داماد ہوگا۔",
      "پرندہ": "سفید یا پیلا ہو تو اچھی جگہ سے دولت ملے گی، کالا یا نیلا یا گہرا سبز ہو تو بری دولت۔",
      "صدقہ": "خواب میں صدقہ دینا بہت بڑے نقصان کا خطرہ ہو سکتا ہے۔"
    };

    const searchInput = document.getElementById("search");
    const resultDiv = document.getElementById("result");
    const contactForm = document.getElementById("contactForm");

    searchInput.addEventListener("input", () => {
      const query = searchInput.value.trim();
      resultDiv.innerHTML = "";
      contactForm.classList.add("hidden");

      let found = false;
      for (const key in dreams) {
        if (query.includes(key)) {
          resultDiv.innerHTML = `<strong>تعبیر:</strong> ${dreams[key]}`;
          found = true;
          break;
        }
      }

      if (!found && query.length > 2) {
        resultDiv.innerHTML = "معذرت! اس خواب کی تعبیر دستیاب نہیں۔";
        contactForm.classList.remove("hidden");
        document.getElementById("dream").value = query;
      }
    });

    document.getElementById("contactForm").addEventListener("submit", function(e) {
      e.preventDefault();
      alert("آپ کا پیغام موصول ہو گیا ہے۔ جلد آپ سے رابطہ کیا جائے گا ان شاء اللہ۔");
      contactForm.reset();
      contactForm.classList.add("hidden");
    });
  </script>
</body>
</html>



