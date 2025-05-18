<!DOCTYPE html>
<html lang="th">
<head>
  <div class="container-lg px-3 my-5 markdown-body">
    : : before
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>คิดถึงอ้วนที่สุดเลย 💖</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: 'Kanit', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      background-image: url('https://scontent.cdninstagram.com/v/t51.75761-15/496347416_17938158459001850_8112075224366874179_n.png?...');
      background-size: cover;
      background-position: center;
      position: relative;
      color: #fff;
      text-align: center;
    }

    body::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.4);
      z-index: 0;
    }

    .card {
      position: relative;
      z-index: 1;
      background: rgba(255, 255, 255, 0.15);
      border-radius: 20px;
      padding: 30px;
      width: 90%;
      max-width: 400px;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
      backdrop-filter: blur(6px);
    }

    h1 {
      font-size: 2rem;
      margin-bottom: 15px;
    }

    p {
      font-size: 1rem;
      line-height: 1.6;
    }

    .heart {
      font-size: 2.5rem;
      animation: beat 1s infinite;
    }

    .image-button {
      margin-top: 20px;
      cursor: pointer;
      width: 100px;
      border-radius: 20px;
      transition: transform 0.2s;
    }

    .image-button:hover {
      transform: scale(1.05);
    }

    .popup {
      margin-top: 15px;
      display: none;
      font-size: 1rem;
      background: rgba(255, 255, 255, 0.2);
      border-radius: 10px;
      padding: 10px;
      animation: fadeIn 0.5s ease forwards;
    }

    @keyframes beat {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.2); }
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <div class="card">
    <div class="heart">❤️</div>
    <h1>คิดถึงอ้วนที่สุดเลย</h1>
    <p>
      พี่ไม่มีไรทำนั่งเล่นเขียนโค้ดอยู่<br />
      กินข้าวเยอะมั้ย??
      <br />
      อ้วนทำไรอยู่??
    </p>
    
    <img
      src="https://scontent.cdninstagram.com/v/t51.75761-15/496347416_17938158459001850_8112075224366874179_n.png?_nc_cat=106&ccb=7-5&_nc_sid=ecb677&_nc_ohc=obhP5yk6QaIQ7kNvwGvlJ_X&_nc_oc=AdkN-OumNdS4yP5TW5V1OIJCh9xUPBwciYM_-LpQj02M7yc9xjNOQopjeIalu608ZlXXrp2nUKRW4_Ovg_GRy-yP&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.cdninstagram.com&_nc_gid=kygOasa-YzaZ9XavwtDShg&oh=00_AfIQmIqFb3q39ncDXzZHsBuaDbBKVHQVSXZi9gBX0PG8wQ&oe=682F741E"
      alt="รูปอ้วน"
      class="image-button"
      onclick="showMessage()"
    />
    
    <div class="popup" id="popupMessage">
      พี่ไปบ้านเพื่อนนะะะะะ
     
    </div>

    <div class="heart">❤️</div>
  </div>

  <script>
    function showMessage() {
      const popup = document.getElementById("popupMessage");
      popup.style.display = "block";
    }
  </script>
</body>
</html>
