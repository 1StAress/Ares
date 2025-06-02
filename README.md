<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Login</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #ffe6f0; /* พื้นหลังสีชมพูอ่อน */
      font-family: 'Comic Sans MS', cursive, sans-serif;
      height: 100vh;
      overflow: hidden;
      position: relative;
    }

    .container {
      position: relative;
      z-index: 1;
      text-align: center;
      padding-top: 100px;
    }

    h1 {
      font-size: 48px;
      color: #d63384;
    }

    input {
      display: block;
      margin: 20px auto;
      padding: 10px;
      width: 250px;
      font-size: 18px;
      border: 2px solid #d63384;
      border-radius: 10px;
    }

    button {
      padding: 10px 30px;
      font-size: 20px;
      background-color: #ff66a3;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
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
  // สร้างหัวใจลอยขึ้น
  function createHeart() {
    const heart = document.createElement('div');
    heart.classList.add('heart');
    heart.innerHTML = '❤️';
    heart.style.left = Math.random() * 100 + 'vw';
    heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
    heart.style.animationDuration = (Math.random() * 5 + 5) + 's';
    document.body.appendChild(heart);

    // ลบหัวใจเมื่อจบ animation
    setTimeout(() => {
      heart.remove();
    }, 10000);
  }

  setInterval(createHeart, 500); // สร้างหัวใจทุก 0.5 วิ
</script>

</body>
</html>
