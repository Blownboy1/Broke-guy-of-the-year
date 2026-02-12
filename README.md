# Broke-guy-of-the-year
Blownboy
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Hey Fisayo... 💕</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: 'Segoe UI', sans-serif;
      overflow: hidden;
    }
    .container {
      text-align: center;
      color: white;
      background: rgba(255, 105, 180, 0.7);
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.3);
      max-width: 90%;
    }
    h1 {
      font-size: 3em;
      margin-bottom: 10px;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.4);
    }
    p {
      font-size: 1.4em;
      margin: 20px 0;
    }
    .buttons {
      margin-top: 30px;
    }
    button {
      font-size: 1.5em;
      padding: 15px 40px;
      margin: 10px;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s;
    }
    #yesBtn {
      background: #ff4757;
      color: white;
    }
    #yesBtn:hover {
      background: #ff6b81;
      transform: scale(1.1);
    }
    #noBtn {
      background: #57606f;
      color: white;
      position: relative;
    }
    .hearts {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
    }
    .heart {
      position: absolute;
      font-size: 2em;
      animation: float 6s infinite;
      color: #fff;
      opacity: 0.8;
    }
    @keyframes float {
      0% { transform: translateY(100vh); }
      100% { transform: translateY(-20vh); }
    }
  </style>
</head>
<body>

  <div class="hearts" id="hearts"></div>

  <div class="container">
    <h1>Hey Fisayo! 💖</h1>
    <p>I've been waiting for the perfect moment...<br>Will you be my Valentine? 🥺❤️</p>
    
    <div class="buttons">
      <button id="yesBtn" onclick="sayYes()">Yes! 💕</button>
      <button id="noBtn" onmouseover="runAway()" onclick="sayNo()">No 😢</button>
    </div>
    
    <div id="response" style="margin-top: 30px; font-size: 1.8em; display: none;"></div>
  </div>

  <script>
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.innerHTML = "❤️";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (Math.random() * 3 + 4) + "s";
      document.getElementById("hearts").appendChild(heart);
      setTimeout(() => heart.remove(), 7000);
    }
    setInterval(createHeart, 800);

    let noAttempts = 0;
    const noPhrases = [
      "Are you sure? 😭",
      "Please rethink... 🥺",
      "Nooo come onnn 💔",
      "Think again, Fisayo! ❤️",
      "Pretty please? 🥹"
    ];

    function runAway() {
      const btn = document.getElementById("noBtn");
      const x = Math.random() * 80 + 10;
      const y = Math.random() * 80 + 10;
      btn.style.position = "absolute";
      btn.style.left = x + "%";
      btn.style.top = y + "%";
    }

    function sayYes() {
      document.querySelector(".container").innerHTML = `
        <h1>Yayyyy! 🎉💖</h1>
        <p>Thank you Fisayo! You just made me the happiest person 😍<br>
        Can't wait to spend Valentine's with you! ❤️<br>
        (Now text me back quick! 😘)</p>
        <div style="font-size: 5em; margin: 20px;">🥰💕❤️</div>
      `;
      for(let i=0; i<30; i++) createHeart();
    }

    function sayNo() {
      noAttempts++;
      const response = document.getElementById("response");
      response.style.display = "block";
      response.innerHTML = noPhrases[noAttempts % noPhrases.length] || "Please don't do this to me 😭❤️";
      document.getElementById("yesBtn").style.fontSize = (1.5 + noAttempts * 0.3) + "em";
    }
  </script>

</body>
</html>
