<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Login</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: #ffe6f0;
      font-family: Arial, sans-serif;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      position: relative;
    }

    .container {
      background-color: rgba(255, 255, 255, 0);
      text-align: center;
      z-index: 1;
      width: 90%;
      max-width: 320px;
    }

    h1 {
      font-size: 28px;
      color: #d63384;
      margin-bottom: 25px;
    }

    input {
      display: block;
      width: 100%;
      margin: 10px 0;
      padding: 12px;
      font-size: 16px;
      border: 2px solid #d63384;
      border-radius: 10px;
    }

    button {
      width: 100%;
      padding: 12px;
      font-size: 18px;
      background-color: #ff66a3;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      margin-top: 10px;
    }

    .heart {
      position: absolute;
      color: #ff99cc;
      animation: floatUp linear infinite;
      user-select: none;
      z-index: 0;
    }

    @keyframes floatUp {
      from {
        transform: translateY(100vh);
        opacity: 1;
      }
      to {
        transform: translateY(-10vh);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>Login</h1>
    <input type="text" placeholder="Date of Birth" />
    <input type="text" placeholder="Favorite Animal" />
    <button>Sign In</button>
  </div>

  <script>
    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.innerHTML = '❤️';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.fontSize = (Math.random() * 16 + 10) + 'px';
      heart.style.animationDuration = (Math.random() * 5 + 5) + 's';
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 10000);
    }

    setInterval(createHeart, 500);
  </script>

</body>
</html>
