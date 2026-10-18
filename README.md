<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For You ❤️</title>
  <style>
    * { box-sizing: border-box; }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: Georgia, "Times New Roman", serif;
      color: #562d3c;
      background:
        radial-gradient(circle at 15% 15%, #fff7ef 0, transparent 28%),
        radial-gradient(circle at 85% 80%, #ffdce5 0, transparent 30%),
        linear-gradient(135deg, #fff1e9, #f9dce6);
      display: grid;
      place-items: center;
      padding: 24px;
      overflow-x: hidden;
    }

    .card {
      width: min(720px, 100%);
      padding: clamp(28px, 7vw, 64px);
      background: rgba(255, 255, 255, 0.84);
      border: 1px solid rgba(255, 255, 255, 0.9);
      border-radius: 28px;
      box-shadow: 0 22px 70px rgba(112, 49, 72, 0.16);
      text-align: center;
      position: relative;
      z-index: 1;
    }

    .eyebrow {
      color: #bc607b;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      font: 700 0.72rem Arial, sans-serif;
    }

    h1 {
      font-size: clamp(2.5rem, 9vw, 5rem);
      line-height: 1;
      margin: 18px 0;
      color: #9d3e60;
    }

    .intro {
      font-size: 1.15rem;
      line-height: 1.8;
      max-width: 540px;
      margin: 0 auto 28px;
    }

    button {
      border: 0;
      border-radius: 999px;
      padding: 14px 24px;
      color: white;
      background: #b7476b;
      font-size: 1rem;
      cursor: pointer;
      box-shadow: 0 8px 20px rgba(183, 71, 107, 0.24);
      transition: transform 0.2s, background 0.2s;
    }

    button:hover {
      transform: translateY(-2px);
      background: #963653;
    }

    .letter {
      display: none;
      text-align: left;
      margin-top: 30px;
      padding: 26px;
      border-radius: 18px;
      background: #fff8f7;
      line-height: 1.85;
      animation: appear 0.7s ease both;
    }

    .letter.show { display: block; }

    .signoff {
      text-align: right;
      color: #9d3e60;
      font-style: italic;
      margin-top: 24px;
    }

    .heart {
      position: fixed;
      bottom: -30px;
      color: rgba(183, 71, 107, 0.35);
      animation: floatUp linear forwards;
      pointer-events: none;
    }

    @keyframes floatUp {
      to { transform: translateY(-110vh) rotate(25deg); opacity: 0; }
    }

    @keyframes appear {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    footer {
      margin-top: 26px;
      color: #a57885;
      font: 0.8rem Arial, sans-serif;
    }
  </style>
</head>
<body>
  <main class="card">
    <div class="eyebrow">A little something for</div>
    <h1>[Her name] ❤️</h1>

    <p class="intro">
      I made this little corner of the internet just for you.
      There’s something I’ve been wanting to tell you…
    </p>

    <button id="openButton">Open your surprise 💌</button>

    <section class="letter" id="letter">
      <p>My love,</p>

      <p>
        I don’t think I’ll ever find words big enough for everything you mean to me,
        but I want to keep trying. Since you came into my life, even ordinary days
        have had a little more light in them.
      </p>

      <p>
        I love your <strong>[a quality you adore about her]</strong>, the way you
        <strong>[a little thing she does that makes you smile]</strong>, and how
        <strong>[something special about being with her]</strong>. You make me feel
        lucky simply by being yourself.
      </p>

      <p>
        One of my favorite memories is <strong>[your favorite memory together]</strong>.
        I still smile when I think about it. I hope we make many more memories like
        that—laughing, exploring, and making even the smallest moments feel special.
      </p>

      <p>
        Thank you for being kind, wonderful, and completely yourself. I’m proud of you,
        I’m cheering for you, and I want you to know that you can count on me. Whatever
        the day brings, I’ll always be glad I get to share a part of life with you.
      </p>

      <p>
        If you ever need a reminder: you are loved, appreciated, and so very special
        to me. I choose you today, and I’ll keep choosing you in all the little ways
        that matter.
      </p>

      <p class="signoff">
        All my love,<br>
        [Your name] ❤️
      </p>
    </section>

    <footer>Made with love, just for you.</footer>
  </main>

  <script>
    const button = document.getElementById("openButton");
    const letter = document.getElementById("letter");

    button.addEventListener("click", () => {
      letter.classList.add("show");
      button.textContent = "I love you ❤️";
      button.disabled = true;
      makeHearts();
    });

    function makeHearts() {
      for (let i = 0; i < 24; i++) {
        setTimeout(() => {
          const heart = document.createElement("span");
          heart.className = "heart";
          heart.textContent = Math.random() > 0.5 ? "♥" : "♡";
          heart.style.left = Math.random() * 100 + "vw";
          heart.style.fontSize = (16 + Math.random() * 26) + "px";
          heart.style.animationDuration = (4 + Math.random() * 4) + "s";
          document.body.appendChild(heart);
          setTimeout(() => heart.remove(), 8000);
        }, i * 120);
      }
    }
  </script>
</body>
</html>
