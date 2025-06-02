<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- สำคัญสำหรับมือถือ -->
  <title>Login</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #ffe6f0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      height: 100vh;
      overflow: hidden;
      position: relative;
    }

    .container {
      position: relative;
      z-index: 1;
      text-align: center;
      padding: 60px 20px;
    }

    h1 {
      font-size: 32px;
      color: #d63384;
      margin-bottom: 40px;
    }

    input {
      display: block;
      margin: 15px auto;
      padding: 12px;
      width: 100%;
      max-width: 300px;
      font-size: 16px;
      border: 2px solid #d63384;
      border-radius: 10px;
      box-sizing: border-box;
    }

    button {
      margin-top: 20px;
      padding: 12px 30px;
      font-size: 18px;
      background-color: #ff66a3;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      width: 100%;
      max-width: 300px;
    }

    .heart {
      position: absolute;
      color: #ff99cc;
      animation: floatUp linear infinite;
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
  <input type="text" placeholder="Date of Birth">
  <input type="text" placeholder="Favorite Animal">
  <button>Sign In</button>
</div>

<script>
  function createHeart() {
    const heart = document.createElement('div');
    heart.classList.add('heart');
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
