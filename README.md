<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Men's Grooming Quiz</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #1e1e2f, #2c2c54);
      color: white;
      margin: 0;
      padding: 20px;
      text-align: center;
    }

    .container {
      max-width: 500px;
      margin: auto;
      background: #2f2f4f;
      padding: 20px;
      border-radius: 12px;
    }

    h1 {
      margin-bottom: 10px;
    }

    .question {
      margin: 20px 0;
      text-align: left;
    }

    select, input {
      width: 100%;
      padding: 10px;
      margin-top: 8px;
      border-radius: 6px;
      border: none;
    }

    button {
      margin-top: 20px;
      padding: 12px;
      width: 100%;
      border: none;
      border-radius: 8px;
      background: #ff7b54;
      color: white;
      font-size: 16px;
      cursor: pointer;
    }

    button:hover {
      background: #ff5722;
    }

    .hidden {
      display: none;
    }

    .result {
      margin-top: 20px;
      text-align: left;
    }

    .offer {
      margin-top: 15px;
      font-weight: bold;
      color: #ffd166;
    }
  </style>
</head>
<body>

<div class="container">
  <h1>Find Your Perfect Hairstyle & Skincare Routine</h1>
  <p>Answer a few quick questions</p>

  <div id="quiz">
    <div class="question">
      <label>Skin Type</label>
      <select id="skin">
        <option>Oily</option>
        <option>Dry</option>
        <option>Combination</option>
      </select>
    </div>

    <div class="question">
      <label>Hair Type</label>
      <select id="hair">
        <option>Straight</option>
        <option>Wavy</option>
        <option>Curly</option>
      </select>
    </div>

    <div class="question">
      <label>Face Shape</label>
      <select id="face">
        <option>Round</option>
        <option>Oval</option>
        <option>Square</option>
      </select>
    </div>

    <div class="question">
      <label>Main Concern</label>
      <select id="concern">
        <option>Acne</option>
        <option>Dull Skin</option>
        <option>Hair Fall</option>
      </select>
    </div>

    <div class="question">
      <label>Lifestyle</label>
      <select id="life">
        <option>Active</option>
        <option>Busy</option>
        <option>Relaxed</option>
      </select>
    </div>

    <button onclick="showResult()">Get My Result</button>
  </div>

  <div id="resultSection" class="hidden">
    <div class="result" id="resultText"></div>

    <div class="offer">🎉 Get ₹300 OFF on your first visit</div>

    <div class="question">
      <label>Name</label>
      <input type="text" id="name" placeholder="Enter your name">
    </div>

    <div class="question">
      <label>Phone Number</label>
      <input type="text" id="phone" placeholder="Enter your phone number">
    </div>

    <button onclick="submitForm()">Submit</button>
  </div>
</div>

<script>
  function showResult() {
    let skin = document.getElementById("skin").value;
    let face = document.getElementById("face").value;

    let facial = skin === "Oily" ? "Oil-control facial" :
                 skin === "Dry" ? "Hydrating facial" : "Balancing facial";

    let hairstyle = face === "Round" ? "Textured top with fade" :
                     face === "Oval" ? "Slick back or undercut" : "Side part or fade";

    let routine = "Cleanse twice daily, use moisturizer, and apply sunscreen.";

    document.getElementById("resultText").innerHTML =
      `<h3>Your Recommendations:</h3>
      <p><b>Facial:</b> ${facial}</p>
      <p><b>Hairstyle:</b> ${hairstyle}</p>
      <p><b>Routine:</b> ${routine}</p>`;

    document.getElementById("quiz").classList.add("hidden");
    document.getElementById("resultSection").classList.remove("hidden");
  }

  function submitForm() {
    let name = document.getElementById("name").value;
    let phone = document.getElementById("phone").value;

    if (name === "" || phone === "") {
      alert("Please fill all details");
      return;
    }

    alert("Thank you! We'll contact you soon.");
  }
</script>

</body>
</html>
