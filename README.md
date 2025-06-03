<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Login</title>
  <style>
    /* โค้ด CSS เดิมของคุณ */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body, html {
      height: 100%;
      font-family: 'Segoe UI', sans-serif;
      overflow: hidden; /* ป้องกัน scrollbar หากหัวใจลอยออกนอกจอ */
    }

    body {
      background: url('https://scontent.futp1-2.fna.fbcdn.net/v/t1.15752-9/494573832_9051215981648531_2726047502865951069_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=0024fc&_nc_ohc=CTRHYcy2bsUQ7kNvwGUiv51&_nc_oc=AdkDfFtlYfyBarIue7qHVunLmUwrp70w8CcFdSpVp0LNUjrHC44dsfaGH2Fh4YLML6sX4rktCd-_Xm7DRjbSNnWZ&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.futp1-2.fna&oh=03_Q7cD2QFxdbr1JB2RDeNBUWr1vMav0m_YelgBUpSlsbhNuwgmIg&oe=6865969C') no-repeat center center/cover;
      display: flex;
      justify-content: center;
      align-items: center;
      backdrop-filter: blur(10px);
      padding: 20px;
      position: relative; /* สำคัญ: เพื่อให้ heart particles ลอยอยู่ภายใน body */
    }

    .login-box {
      background: rgba(255, 255, 255, 0.1);
      border: 1px solid rgba(255, 255, 255, 0.3);
      border-radius: 20px;
      backdrop-filter: blur(10px);
      box-shadow: 0 0 30px rgba(0, 0, 0, 0.3);
      padding: 30px;
      width: 100%;
      max-width: 340px;
      color: #fff;
      z-index: 10; /* ให้ login box อยู่ด้านหน้าหัวใจ */
      position: relative; /* สำคัญ: เพื่อให้ z-index ทำงาน */
    }

    .login-box h2 {
      text-align: center;
      margin-bottom: 20px;
      font-size: 24px;
    }

    .input-group {
      margin-bottom: 15px;
    }

    .input-group input {
      width: 100%;
      padding: 12px;
      border-radius: 10px;
      border: none;
      font-size: 16px;
      background: rgba(255, 255, 255, 0.2);
      color: #fff;
    }

    .input-group input::placeholder {
      color: #ddd;
    }

    .options {
      display: flex;
      justify-content: space-between;
      font-size: 12px;
      margin-bottom: 15px;
    }

    .options label {
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .options a {
      color: #ddd;
      text-decoration: none;
    }

    .login-btn {
      width: 100%;
      padding: 12px;
      background: #ffffff;
      border: none;
      border-radius: 25px;
      color: #444;
      font-weight: bold;
      cursor: pointer;
      font-size: 16px;
      transition: all 0.3s ease-in-out; /* เพิ่ม transition สำหรับการเปลี่ยนแปลงรูปร่าง */
      display: flex; /* เพื่อจัดให้อยู่ตรงกลางเมื่อเปลี่ยนเป็นหัวใจ */
      justify-content: center;
      align-items: center;
    }

    .login-btn:hover {
      background: #e0e0e0;
    }

    /* CSS สำหรับปุ่มที่เปลี่ยนเป็นหัวใจ */
    .login-btn.heart-active {
        background: #ff69b4; /* สีหัวใจ */
        color: white; /* สีข้อความ/หัวใจ */
        border-radius: 50%; /* ทำให้เป็นวงกลม */
        width: 50px; /* ขนาดของวงกลม */
        height: 50px; /* ขนาดของวงกลม */
        font-size: 2em; /* ขนาดของสัญลักษณ์หัวใจ */
        box-shadow: 0 0 15px rgba(255, 105, 180, 0.7); /* เงาเรืองแสง */
        animation: pulse 1s infinite alternate; /* เพิ่ม animation การเต้นของหัวใจ */
        display: flex; /* จัดให้อยู่ตรงกลาง */
        justify-content: center;
        align-items: center;
        margin: 0 auto; /* จัดให้อยู่ตรงกลางแนวนอน */
    }

    .login-btn.heart-active span {
        display: block; /* ทำให้สัญลักษณ์หัวใจแสดงผล */
    }

    /* Keyframes สำหรับ animation การเต้นของหัวใจ */
    @keyframes pulse {
        0% { transform: scale(1); }
        100% { transform: scale(1.1); }
    }

    .register-link {
      margin-top: 10px;
      font-size: 12px;
      text-align: center;
    }

    .register-link a {
      color: #fff;
      text-decoration: underline;
    }

    #error-message {
        color: #ffcccc;
        text-align: center;
        margin-top: 10px;
        font-size: 14px;
        display: none;
    }

    /* --- ส่วนของ CSS สำหรับหัวใจลอยได้ --- */
    .heart-container {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;
        z-index: 1; /* ให้อยู่ใต้ login box */
    }
    .heart-particle {
        position: absolute;
        font-size: 20px; /* ขนาดเริ่มต้น */
        color: #ff69b4; /* สีชมพูหัวใจ */
        pointer-events: none; /* ทำให้คลิกทะลุได้ ไม่ขวางการคลิก element อื่นๆ */
        animation: floatUpDown 10s infinite ease-in-out,
                   fadeInOut 10s forwards; /* เพิ่ม animation fade in/out */
        opacity: 0; /* ซ่อนไว้ในตอนแรก */
        text-shadow: 0 0 5px rgba(255, 255, 255, 0.5); /* เพิ่มเงาให้ดูมีมิติ */
        will-change: transform, opacity; /* ช่วยเพิ่มประสิทธิภาพการทำงานของ animation */
    }

    /* Keyframes สำหรับการลอยขึ้น-ลงแบบสุ่ม */
    @keyframes floatUpDown {
        0% { transform: translateY(0) rotate(0deg); }
        25% { transform: translateY(-50px) rotate(5deg); }
        50% { transform: translateY(0) rotate(0deg); }
        75% { transform: translateY(50px) rotate(-5deg); }
        100% { transform: translateY(0) rotate(0deg); }
    }

    /* Keyframes สำหรับการ Fade In และ Fade Out */
    @keyframes fadeInOut {
        0% { opacity: 0; transform: translateY(100vh); } /* เริ่มต้นจากด้านล่างสุดของจอ */
        10% { opacity: 1; transform: translateY(80vh); }
        90% { opacity: 1; }
        100% { opacity: 0; transform: translateY(-20vh); } /* ลอยขึ้นไปและจางหายไป */
    }

  </style>
</head>
<body>

  <div class="heart-container"></div>

  <div class="login-box">
    <h2>Login</h2>
    <div class="input-group">
      <input type="text" id="dob" placeholder="Date of Birth">
    </div>
    <div class="input-group">
      <input type="password" id="animal" placeholder="Favorite Animal">
    </div>
    <div class="options">
      <label><input type="checkbox"> Remember me</label>
      <a href="#">Forgot Password?</a>
    </div>
    <button class="login-btn" id="loginButton">Login</button>
    <p id="error-message">วันที่เกิดหรือสัตว์เลี้ยงที่คุณชื่นชอบไม่ถูกต้อง</p>
    <div class="register-link">
      Don't have an account? <a href="#">Register</a>
    </div>
  </div>

  <script>
    // ดึง Element ที่ต้องการใช้งานด้วย id
    const dobInput = document.getElementById('dob');
    const animalInput = document.getElementById('animal');
    const loginButton = document.getElementById('loginButton');
    const errorMessage = document.getElementById('error-message');

    // กำหนดค่า "Date of Birth" และ "Favorite Animal" ที่ถูกต้อง
    const correctDob = "13/01/2005";
    const correctAnimal = "cat";

    // เพิ่ม Event Listener ให้กับปุ่ม Login เมื่อมีการคลิก
    loginButton.addEventListener('click', function() {
      const enteredDob = dobInput.value;
      const enteredAnimal = animalInput.value.toLowerCase();

      if (enteredDob === correctDob && enteredAnimal === correctAnimal) {
        // 1. ซ่อนช่อง input และข้อความอื่นๆ ชั่วคราว (optional)
        dobInput.style.display = 'none';
        animalInput.style.display = 'none';
        document.querySelector('.options').style.display = 'none';
        document.querySelector('.register-link').style.display = 'none';
        errorMessage.style.display = 'none';

        // 2. เปลี่ยนปุ่มเป็นหัวใจ
        loginButton.classList.add('heart-active');
        loginButton.innerHTML = '&#x2764;'; // สัญลักษณ์หัวใจ ❤️
        loginButton.disabled = true; // ปิดการใช้งานปุ่มชั่วคราว

        // 3. รอสักครู่ (เช่น 1.5 วินาที) ก่อนเปลี่ยนหน้า
        setTimeout(() => {
          window.location.href = "https://www.youtube.com/watch?v=gKXa9HHmV0c&pp=ygUq4Liq4Lit4LiZ4Lil4Liy4LiB4Lir4Lix4Lin4Lif4Li14Lif4Liy4Lii"; // เปลี่ยนไปหน้า success.html
        }, 1500); // 1500 มิลลิวินาที = 1.5 วินาที
      } else {
        // ถ้าข้อมูลไม่ถูกต้อง ให้แสดงข้อความผิดพลาด
        errorMessage.style.display = 'block';
      }
    });

    dobInput.addEventListener('input', function() {
        errorMessage.style.display = 'none';
    });
    animalInput.addEventListener('input', function() {
        errorMessage.style.display = 'none';
    });

    const heartContainer = document.querySelector('.heart-container');

    function createHeart() {
        const heart = document.createElement('span');
        heart.classList.add('heart-particle');
        heart.innerHTML = '&#x2764;';

        const size = Math.random() * 30 + 15;
        heart.style.fontSize = `${size}px`;

        const startX = Math.random() * window.innerWidth;
        heart.style.left = `${startX}px`;
        heart.style.bottom = `-50px`;

        // สุ่ม duration และ delay ของ animation
        const duration = Math.random() * 8 + 7; 
        const delay = Math.random() * 5; 
        heart.style.animationDuration = `${duration}s`;
        heart.style.animationDelay = `${delay}s`;

        heartContainer.appendChild(heart);

        heart.addEventListener('animationend', () => {
            heart.remove();
        });
    }
    setInterval(createHeart, 500);

  </script>

</body>
</html>
