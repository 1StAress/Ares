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

    body, html {
      height: 100%;
      font-family: 'Segoe UI', sans-serif;
    }

    body {
      background: url('https://i.imgur.com/6RMhx.gif') no-repeat center center/cover;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
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
  </style>
</head>
<body>

  <div class="login-box">
    <h2>Login</h2>
    <div class="input-group">
      <input type="text" placeholder="Email ID">
    </div>
    <div class="input-group">
      <input type="password" placeholder="Password">
    </div>
    <div class="options">
      <label><input type="checkbox"> Remember me</label>
      <a href="#">Forgot Password?</a>
    </div>
    <button class="login-btn">Login</button>
    <div class="register-link">
      Don't have an account? <a href="#">Register</a>
    </div>
  </div>

</body>
</html>
