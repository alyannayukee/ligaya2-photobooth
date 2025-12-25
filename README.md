<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ligaya Photobooth</title>

<link href="https://fonts.googleapis.com/css2?family=VT323&display=swap" rel="stylesheet">
<link rel="stylesheet" href="style.css">
</head>

<body>
<div id="kiosk">

  <!-- ADMIN BUTTON -->
  <button id="adminBtn">⚙</button>

  <!-- START SCREEN -->
  <section class="screen active" id="startScreen">
    <h1 class="logo">Ligaya</h1>
    <p class="subtitle">mga alaala</p>
    <button onclick="goToPay()">START</button>
  </section>

  <!-- PAY SCREEN -->
  <section class="screen" id="payScreen">
    <h2>Pay ₱40</h2>
    <p>Please pay before continuing</p>
    <button onclick="confirmPayment()">CONFIRM PAYMENT</button>
  </section>

  <!-- CAPTURE SCREEN -->
  <section class="screen" id="captureScreen">
    <div class="receipt">
      <div class="header">
        <h1 class="logo small">Ligaya</h1>
        <p class="subtitle">mga alaala</p>
        <p id="dateTime"></p>
      </div>

      <div class="camera-frame">
        <video id="video" autoplay></video>
        <canvas id="canvas"></canvas>
        <div id="countdown"></div>
      </div>

      <div class="barcode"></div>
    </div>
  </section>

  <!-- PREVIEW SCREEN -->
  <section class="screen" id="previewScreen">
    <img id="previewImg">
    <p>Would you like to re-capture?</p>
    <button onclick="recapture()">RECAPTURE (ONCE)</button>
    <button onclick="goToOutput()">NEXT</button>
  </section>

  <!-- OUTPUT SCREEN -->
  <section class="screen" id="outputScreen">
    <button onclick="printPhoto()">PRINT</button>
    <div id="qr"></div>
  </section>

</div>

<!-- ADMIN PANEL -->
<div id="adminPanel">
  <input type="password" id="adminPass" placeholder="Password">
  <button onclick="unlockAdmin()">ENTER</button>
  <div id="adminControls">
    <label>Vintage Level</label>
    <input type="range" min="0" max="100">
  </div>
</div>

<audio id="beep" src="sounds/beep.mp3"></audio>
<audio id="shutter" src="sounds/shutter.mp3"></audio>

<script src="https://cdn.jsdelivr.net/npm/qrcodejs/qrcode.min.js"></script>
<script src="app.js"></script>
</body>
</html>
