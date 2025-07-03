<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Métodos de Relajación en el Embarazo</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: "Segoe UI", sans-serif;
      background: #f5f7fa;
      margin: 0;
      padding: 20px;
      color: #333;
    }
    header {
      text-align: center;
      margin-bottom: 30px;
    }
    h1 {
      color: #4caf50;
    }
    section {
      background: #fff;
      border-radius: 12px;
      padding: 20px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      margin-bottom: 20px;
    }
    h2 {
      color: #4caf50;
    }
    #qr {
      text-align: center;
      margin-top: 30px;
    }
    button {
      background-color: #4caf50;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 16px;
    }
    button:hover {
      background-color: #45a049;
    }
    canvas {
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <header>
    <h1>Métodos de Relajación Durante el Embarazo</h1>
    <p>Aprende a cuidar tu bienestar físico y emocional durante esta etapa especial.</p>
  </header>

  <section>
    <h2>1. Respiración profunda</h2>
    <p>Controlar la respiración ayuda a reducir el estrés, mejorar el sueño y calmar la mente.</p>
  </section>

  <section>
    <h2>2. Meditación guiada</h2>
    <p>Escuchar meditaciones grabadas puede ayudarte a mantener la calma y enfocarte en tu bienestar.</p>
  </section>

  <section>
    <h2>3. Yoga prenatal</h2>
    <p>Movimientos suaves diseñados especialmente para embarazadas que mejoran la postura y reducen dolores.</p>
  </section>

  <section>
    <h2>4. Masajes</h2>
    <p>Un masaje suave alivia tensiones musculares, mejora la circulación y relaja el cuerpo.</p>
  </section>

  <section>
    <h2>5. Escuchar música relajante</h2>
    <p>La música suave puede inducir tranquilidad y generar un ambiente armonioso para ti y tu bebé.</p>
  </section>

  <div id="qr">
    <h2>Comparte esta información</h2>
    <button onclick="generarQR()">Generar Código QR</button>
    <div id="codigoQR"></div>
  </div>

  <!-- Librería QRCode.js -->
  <script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>
  <script>
    function generarQR() {
      const qrDiv = document.getElementById("codigoQR");
      qrDiv.innerHTML = ""; // Limpia si ya existe uno
      const url = window.location.href; // Usa la URL actual
      new QRCode(qrDiv, {
        text: url,
        width: 200,
        height: 200,
        colorDark: "#000000",
        colorLight: "#ffffff",
        correctLevel: QRCode.CorrectLevel.H
      });
    }
  </script>

</body>
</html>
