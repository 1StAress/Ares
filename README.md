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
