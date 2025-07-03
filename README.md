<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Métodos de Relajación en el Embarazo</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    body {
      font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
      background: #fff0f6;
      margin: 0;
      padding: 20px;
      color: #4a2c3a;
    }
    header {
      text-align: center;
      margin-bottom: 25px;
    }
    header img {
      width: 100%;
      max-width: 400px;
      border-radius: 15px;
      margin-bottom: 15px;
      box-shadow: 0 4px 12px rgba(204, 102, 153, 0.3);
    }
    h1 {
      color: #d6336c;
      margin-bottom: 5px;
    }
    p.subtitle {
      font-size: 1.1rem;
      color: #a05a79;
      margin-top: 0;
      margin-bottom: 30px;
    }
    section {
      background: #ffe6f0;
      border-radius: 15px;
      padding: 18px 25px;
      box-shadow: 0 0 10px rgba(214, 102, 140, 0.3);
      margin-bottom: 18px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    section:hover {
      background-color: #f9d1e1;
    }
    h2 {
      color: #c8336e;
      margin-top: 0;
    }
    #qr {
      text-align: center;
      margin-top: 35px;
    }
    button {
      background-color: #d6336c;
      color: white;
      padding: 12px 28px;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      font-size: 17px;
      transition: background-color 0.3s ease;
    }
    button:hover {
      background-color: #b32456;
    }
    canvas {
      margin-top: 22px;
      border-radius: 15px;
      box-shadow: 0 4px 10px rgba(214, 102, 140, 0.4);
    }
    /* Modal styles */
    .modal {
      display: none; 
      position: fixed; 
      z-index: 1000; 
      padding-top: 60px; 
      left: 0;
      top: 0;
      width: 100%; 
      height: 100%; 
      overflow: auto; 
      background-color: rgba(0,0,0,0.7); 
    }
    .modal-content {
      margin: auto;
      background: white;
      padding: 15px;
      border-radius: 12px;
      max-width: 800px;
      box-shadow: 0 0 25px rgba(200, 0, 100, 0.5);
      position: relative;
    }
    .modal-content video {
      width: 100%;
      height: 450px;
      border-radius: 10px;
      background: black;
    }
    .close-btn {
      color: #c8336e;
      position: absolute;
      top: 10px;
      right: 20px;
      font-size: 28px;
      font-weight: bold;
      cursor: pointer;
      user-select: none;
      transition: color 0.3s ease;
    }
    .close-btn:hover {
      color: #a02456;
    }
    /* Para las imágenes dentro de sección */
    .explanation-img {
      max-width: 100%;
      border-radius: 12px;
      margin-top: 12px;
      box-shadow: 0 2px 8px rgba(200, 0, 100, 0.2);
    }
  </style>
</head>
<body>

  <header>
    <img src="https://images.unsplash.com/photo-1503676260728-1c00da094a0b?auto=format&fit=crop&w=600&q=80" alt="Mujer embarazada" />
    <h1>Métodos de Relajación Durante el Embarazo</h1>
    <p class="subtitle">Cuida tu bienestar físico y emocional con cariño y calma.</p>
  </header>

  <!-- Respiración Profunda con texto e imagen, sin modal -->
  <section id="respiracion">
    <h2>1. Respiración profunda</h2>
    <p>Controlar la respiración ayuda a reducir el estrés, mejorar el sueño y calmar la mente. Prueba esta técnica:</p>
    <ul>
      <li>Siéntate o acuéstate cómodamente.</li>
      <li>Inhala lenta y profundamente por la nariz contando hasta 4.</li>
      <li>Retén el aire durante 4 segundos.</li>
      <li>Exhala lentamente por la boca contando hasta 6.</li>
      <li>Repite este ciclo varias veces hasta sentir relajación.</li>
    </ul>
    <img class="explanation-img" src="https://cdn.pixabay.com/photo/2018/07/07/10/23/breathing-3521230_1280.png" alt="Ejemplo respiración profunda" />
  </section>

  <!-- Meditación guiada con video modal -->
  <section data-video="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.webm">
    <h2>2. Meditación guiada</h2>
    <p>Escuchar meditaciones grabadas puede ayudarte a mantener la calma y enfocarte en tu bienestar.</p>
  </section>

  <!-- Yoga prenatal con video modal -->
  <section data-video="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.webm">
    <h2>3. Yoga prenatal</h2>
    <p>Movimientos suaves diseñados especialmente para embarazadas que mejoran la postura y reducen dolores.</p>
  </section>

  <!-- Masajes con texto e imagen, sin modal -->
  <section id="masajes">
    <h2>4. Masajes</h2>
    <p>Un masaje suave alivia tensiones musculares, mejora la circulación y relaja el cuerpo. Aquí unos tips básicos:</p>
    <ul>
      <li>Usa movimientos lentos y presiones suaves.</li>
      <li>Evita presionar el abdomen directamente.</li>
      <li>Concéntrate en la espalda baja, hombros y piernas.</li>
      <li>Utiliza aceites naturales o cremas para facilitar el masaje.</li>
      <li>Consulta siempre con un especialista si tienes dudas.</li>
    </ul>
    <img class="explanation-img" src="https://cdn.pixabay.com/photo/2017/02/04/23/02/massage-2037549_1280.jpg" alt="Masaje relajante embarazo" />
  </section>

  <!-- Música relajante con video modal -->
  <section data-video="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.webm">
    <h2>5. Escuchar música relajante</h2>
    <p>La música suave puede inducir tranquilidad y generar un ambiente armonioso para ti y tu bebé.</p>
  </section>

  <div id="qr">
    <h2>Comparte esta información</h2>
    <button onclick="generarQR()">Generar Código QR</button>
    <div id="codigoQR"></div>
  </div>

  <!-- Modal -->
  <div id="modal" class="modal">
    <div class="modal-content">
      <span class="close-btn" id="closeBtn">&times;</span>
      <video id="videoPlayer" controls></video>
    </div>
  </div>

  <!-- Librería QRCode.js -->
  <script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>
  <script>
    // Generar QR
    function generarQR() {
      const qrDiv = document.getElementById("codigoQR");
      qrDiv.innerHTML = "";
      const url = window.location.href;
      new QRCode(qrDiv, {
        text: url,
        width: 220,
        height: 220,
        colorDark: "#c8336e",
        colorLight: "#fff0f6",
        correctLevel: QRCode.CorrectLevel.H
      });
    }

    // Modal video
    const modal = document.getElementById("modal");
    const videoPlayer = document.getElementById("videoPlayer");
    const closeBtn = document.getElementById("closeBtn");

    document.querySelectorAll("section[data-video]").forEach(section => {
      section.addEventListener("click", () => {
        const videoUrl = section.getAttribute("data-video");
        videoPlayer.src = videoUrl;
        videoPlayer.play();
        modal.style.display = "block";
      });
    });

    closeBtn.addEventListener("click", () => {
      modal.style.display = "none";
      videoPlayer.pause();
      videoPlayer.src = "";
    });

    window.addEventListener("click", (e) => {
      if (e.target === modal) {
        modal.style.display = "none";
        videoPlayer.pause();
        videoPlayer.src = "";
      }
    });
  </script>

</body>
</html>







