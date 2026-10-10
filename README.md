<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Love Letter 💌</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #f8d7df;
      font-family: Georgia, serif;
      overflow: hidden;
    }

    /* Folder */
    .folder {
      position: relative;
      width: 280px;
      height: 210px;
      background: #d9a441;
      border-radius: 8px;
      cursor: pointer;
      box-shadow: 0 15px 30px rgba(0,0,0,0.2);
      transition: 0.4s;
    }

    .folder:hover {
      transform: scale(1.05);
    }

    .folder::before {
      content: "";
      position: absolute;
      top: -25px;
      left: 0;
      width: 110px;
      height: 35px;
      background: #d9a441;
      border-radius: 8px 8px 0 0;
    }

    .folder::after {
      content: "💌";
      position: absolute;
      font-size: 55px;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
    }

    .folder-text {
      position: absolute;
      bottom: 18px;
      width: 100%;
      text-align: center;
      font-size: 18px;
      color: white;
      font-weight: bold;
    }

    /* Letter */
    .letter {
      display: none;
      position: relative;
      width: 90%;
      max-width: 600px;
      max-height: 85vh;
      padding: 40px;
      background: #fffaf0;
      border-radius: 5px;
      box-shadow: 0 15px 40px rgba(0,0,0,0.25);
      animation: openLetter 0.8s ease;
      overflow-y: auto;
    }

    .letter h1 {
      text-align: center;
      color: #c94f68;
      margin-top: 0;
    }

    .letter p {
      color: #4a3a3a;
      font-size: 18px;
      line-height: 1.8;
    }

    .heart {
      text-align: center;
      font-size: 45px;
    }

    .close {
      display: block;
      margin: 25px auto 0;
      padding: 10px 25px;
      border: none;
      border-radius: 20px;
      background: #c94f68;
      color: white;
      cursor: pointer;
      font-size: 15px;
    }

    @keyframes openLetter {
      from {
        opacity: 0;
        transform: scale(0.5) rotate(-5deg);
      }

      to {
        opacity: 1;
        transform: scale(1) rotate(0);
      }
    }

    /* Floating hearts */
    .floating-heart {
      position: fixed;
      bottom: -30px;
      font-size: 20px;
      animation: floatUp 5s linear infinite;
      pointer-events: none;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0);
        opacity: 1;
      }

      100% {
        transform: translateY(-110vh);
        opacity: 0;
      }
    }
  </style>
</head>

<body>

  <!-- Folder -->
  <div class="folder" id="folder" onclick="openLetter()">
    <div class="folder-text">Click to open 💕</div>
  </div>

  <!-- Love Letter -->
  <div class="letter" id="letter">

    <div class="heart">❤️</div>

    <h1>My Love Letter</h1>

    <p>
      My love,
    </p>

    <p>
      I just want you to know how special you are to me.
      Every moment I spend with you means so much, and
      I'm grateful to have you in my life.
    </p>

    <p>
     Thank you for all of your efforts and sacrifices you helped me fix myself at my worst.
    </p>

    <p>
      No matter what happens, I want you to remember that
      you are loved, appreciated, and important to me.
    </p>

    <p>
      I love you more than words can explain. ❤️
    </p>

    <p>
      Forever yours,<br>
      <strong>Your Love 💕</strong>
    </p>

    <button class="close" onclick="closeLetter()">Close 💌</button>

  </div>

  <script>
    function openLetter() {
      document.getElementById("folder").style.display = "none";
      document.getElementById("letter").style.display = "block";

      createHearts();
    }

    function closeLetter() {
      document.getElementById("letter").style.display = "none";
      document.getElementById("folder").style.display = "block";
    }

    function createHearts() {
      for (let i = 0; i < 15; i++) {
        let heart = document.createElement("div");

        heart.className = "floating-heart";
        heart.innerHTML = "❤️";

        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDelay = Math.random() * 3 + "s";

        document.body.appendChild(heart);

        setTimeout(() => {
          heart.remove();
        }, 6000);
      }
    }
  </script>

</body>
</html>
