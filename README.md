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
      overflow-x: hidden;
    }
    header {
      text-align: center;
      margin-bottom: 25px;
      animation: fadeInDown 1s ease forwards;
      opacity: 0;
    }
    header img {
      width: 100%;
      max-width: 400px;
      border-radius: 15px;
      margin-bottom: 15px;
      box-shadow: 0 4px 12px rgba(204, 102, 153, 0.3);
      animation: zoomIn 1s ease forwards;
      opacity: 0;
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
      transition: background-color 0.3s ease, transform 0.3s ease;
      opacity: 0;
      animation: fadeInUp 1s ease forwards;
      animation-delay: 0.3s;
    }
    section:hover {
      background-color: #f9d1e1;
      transform: scale(1.03);
    }
    h2 {
      color: #c8336e;
      margin-top: 0;
    }
    #qr {
      text-align: center;
      margin-top: 35px;
      opacity: 0;
      animation: fadeInUp 1s ease forwards;
      animation-delay: 0.5s;
    }
    button {
      background-color: #d6336c;
      color: white;
      padding: 12px 28px;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      font-size: 17px;
      transition: background-color 0.3s ease, transform 0.2s ease;
      user-select: none;
    }
    button:hover {
      background-color: #b32456;
      transform: scale(1.05);
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
    .modal-content iframe {
      width: 100%;
      height: 450px;
      border-radius: 10px;
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
    .explanation-img {
      max-width: 100%;
      border-radius: 12px;
      margin-top: 12px;
      box-shadow: 0 2px 8px rgba(200, 0, 100, 0.2);
    }
    section.no-modal {
      cursor: default;
    }
    /* Animations */
    @keyframes fadeInDown {
      from {
        opacity: 0;
        transform: translateY(-40px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    @keyframes zoomIn {
      from {
        opacity: 0;
        transform: scale(0.85);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(40px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Música ambiental */
    #music-player {
      position: fixed;
      bottom: 20px;
      left: 20px;
      background: #d6336c;
      border-radius: 12px;
      padding: 10px 15px;
      color: white;
      display: flex;
      align-items: center;
      gap: 10px;
      box-shadow: 0 4px 15px rgba(214, 51, 108, 0.6);
      z-index: 1100;
      font-family: inherit;
    }
    #music-player button {
      background: white;
      color: #d6336c;
      border-radius: 50%;
      border: none;
      width: 32px;
      height: 32px;
      cursor: pointer;
      font-weight: bold;
      font-size: 18px;
      padding: 0;
      line-height: 1;
      transition: background-color 0.3s ease;
    }
    #music-player button:hover {
      background-color: #f4f4f4;
    }
    #music-player label {
      font-size: 14px;
      user-select: none;
    }
    #music-player input[type="range"] {
      width: 100px;
      cursor: pointer;
    }

    /* Temporizador respiración */
    #breath-timer {
      background: #d6336c;
      color: white;
      border-radius: 15px;
      padding: 15px 25px;
      max-width: 400px;
      margin: 0 auto 30px auto;
      text-align: center;
      box-shadow: 0 0 15px rgba(214, 51, 108, 0.7);
      user-select: none;
    }
    #breath-circle {
      width: 120px;
      height: 120px;
      margin: 10px auto 0 auto;
      border-radius: 50%;
      background: #f9d1e1;
      border: 6px solid white;
      box-shadow: 0 0 12px rgba(214, 51, 108, 0.8);
      animation: breath-pulse 4s ease-in-out infinite;
    }
    #breath-instruction {
      font-weight: bold;
      font-size: 18px;
      margin-top: 12px;
      height: 24px;
    }
    #breath-start-btn {
      background-color: white;
      color: #d6336c;
      font-weight: bold;
      margin-top: 18px;
      padding: 10px 22px;
      border-radius: 12px;
      cursor: pointer;
      border: none;
      transition: background-color 0.3s ease;
      font-size: 16px;
    }
    #breath-start-btn:hover {
      background-color: #f9d1e1;
    }
    @keyframes breath-pulse {
      0%, 100% { transform: scale(1); box-shadow: 0 0 12px rgba(214, 51, 108, 0.8); }
      50% { transform: scale(1.3); box-shadow: 0 0 24px rgba(214, 51, 108, 1); }
    }

    /* Chatbot */
    #chatbot {
      position: fixed;
      bottom: 80px;
      right: 20px;
      width: 320px;
      max-width: 90vw;
      background: white;
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(200, 0, 100, 0.4);
      font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
      display: flex;
      flex-direction: column;
      user-select: none;
      z-index: 1200;
      overflow: hidden;
    }
    #chatbot-header {
      background: #d6336c;
      color: white;
      padding: 12px 20px;
      font-weight: bold;
      cursor: pointer;
      user-select: none;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    #chatbot-messages {
      padding: 15px 20px;
      flex-grow: 1;
      overflow-y: auto;
      max-height: 300px;
      background: #fff0f6;
    }
    .chatbot-message {
      margin-bottom: 12px;
      font-size: 14px;
      line-height: 1.3;
    }
    .chatbot-message.user {
      text-align: right;
      color: #d6336c;
      font-weight: 600;
    }
    .chatbot-message.bot {
      text-align: left;
      color: #4a2c3a;
    }
    #chatbot-input-container {
      display: flex;
      border-top: 1px solid #d6336c;
      background: #ffe6f0;
    }
    #chatbot-input {
      flex-grow: 1;
      border: none;
      padding: 10px 15px;
      font-size: 14px;
      border-radius: 0 0 0 15px;
      outline: none;
      font-family: inherit;
    }
    #chatbot-send-btn {
      background: #d6336c;
      border: none;
      color: white;
      padding: 0 18px;
      font-size: 18px;
      cursor: pointer;
      border-radius: 0 0 15px 0;
      transition: background-color 0.3s ease;
    }
    #chatbot-send-btn:hover {
      background-color: #b32456;
    }
    /* Chatbot toggle button */
    #chatbot-toggle {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #d6336c;
      color: white;
      width: 50px;
      height: 50px;
      border-radius: 50%;
      font-size: 30px;
      line-height: 50px;
      text-align: center;
      cursor: pointer;
      box-shadow: 0 0 15px rgba(214, 51, 108, 0.8);
      user-select: none;
      z-index: 1300;
      transition: background-color 0.3s ease;
    }
    #chatbot-toggle:hover {
      background-color: #b32456;
    }
  </style>
</head>
<body>

  <header>
    <img src="https://images.unsplash.com/photo-1503676260728-1c00da094a0b?auto=format&fit=crop&w=600&q=80" alt="Mujer embarazada" />
    <h1>Métodos de Relajación Durante el Embarazo</h1>
    <p class="subtitle">Cuida tu bienestar físico y emocional con cariño y calma.</p>
  </header>

  <!-- Respiración Profunda texto e imagen -->
  <section class="no-modal">
    <h2>1. Respiración profunda</h2>
    <p>Controlar la respiración ayuda a reducir el estrés, mejorar el sueño y calmar la mente. Prueba esta técnica:</p>
    <ul>
      <li>Siéntate o acuéstate cómodamente.</li>
      <li>Inhala lenta y profundamente por la nariz contando hasta 4.</li>
      <li>Retén el aire durante 4 segundos.</li>
      <li>Exhala lentamente por la boca contando hasta 6.</li>
      <li>Repite este ciclo varias veces hasta sentir relajación.</li>
    </ul>
    <img class="explanation-img" src="https://i.imgur.com/i2HG9x4.png" alt="Ejemplo visual de respiración profunda" />
  </section>

  <!-- Meditación guiada video modal -->
  <section data-video="https://www.youtube.com/embed/inpok4MKVLM">
    <h2>2. Meditación guiada</h2>
    <p>Escuchar meditaciones grabadas puede ayudarte a mantener la calma y enfocarte en tu bienestar.</p>
  </section>

  <!-- Yoga prenatal video modal -->
  <section data-video="https://www.youtube.com/embed/v7AYKMP6rOE">
    <h2>3. Yoga prenatal</h2>
    <p>Movimientos suaves diseñados especialmente para embarazadas que mejoran la postura y reducen dolores.</p>
  </section>

  <!-- Masajes texto e imagen -->
  <section class="no-modal">
    <h2>4. Masajes</h2>
    <p>Un masaje suave alivia tensiones musculares, mejora la circulación y relaja el cuerpo. Aquí unos tips básicos:</p>
    <ul>
      <li>Usa movimientos lentos y presiones suaves.</li>
      <li>Evita presionar el abdomen directamente.</li>
      <li>Concéntrate en la espalda baja, hombros y piernas.</li>
      <li>Utiliza aceites naturales o cremas para facilitar el masaje.</li>
      <li>Consulta siempre con un especialista si tienes dudas.</li>
    </ul>
    <img class="explanation-img" src="https://i.imgur.com/Nu52KCr.png" alt="Ejemplo visual de masaje relajante durante el embarazo" />
  </section>

  <!-- Música relajante video modal -->
  <section data-video="https://www.youtube.com/embed/2OEL4P1Rz04">
    <h2>5. Escuchar música relajante</h2>
    <p>La música suave puede inducir tranquilidad y generar un ambiente armonioso para ti y tu bebé.</p>
  </section>

  <!-- Temporizador respiración guiada -->
  <div id="breath-timer">
    <div id="breath-instruction">Pulsa "Iniciar" para comenzar</div>
    <div id="breath-circle"></div>
    <button id="breath-start-btn">Iniciar</button>
  </div>

  <div id="qr">
    <h2>Comparte esta información</h2>
    <button onclick="generarQR()">Generar Código QR</button>
    <div id="codigoQR"></div>
  </div>

  <!-- Modal -->
  <div id="modal" class="modal">
    <div class="modal-content">
      <span class="close-btn" id="closeBtn">&times;</span>
      <iframe id="videoFrame" src="" frameborder="0" allowfullscreen></iframe>
    </div>
  </div>

  <!-- Música ambiental -->
  <div id="music-player">
    <button id="music-toggle" title="Reproducir/Pausar">&#9658;</button>
    <label for="volume-control">Volumen</label>
    <input type="range" id="volume-control" min="0" max="1" step="0.05" value="0.3" />
  </div>

  <!-- Chatbot -->
  <div id="chatbot" style="display:none;">
    <div id="chatbot-header">
      Asistente de Relajación
      <span id="chatbot-close" title="Cerrar" style="cursor:pointer;">&times;</span>
    </div>
    <div id="chatbot-messages"></div>
    <div id="chatbot-input-container">
      <input type="text" id="chatbot-input" placeholder="Escribe tu pregunta..." autocomplete="off" />
      <button id="chatbot-send-btn">&#9658;</button>
    </div>
  </div>
  <div id="chatbot-toggle" title="Abrir asistente">&#128172;</div>

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
    const videoFrame = document.getElementById("videoFrame");
    const closeBtn = document.getElementById("closeBtn");

    document.querySelectorAll("section[data-video]").forEach(section => {
      section.style.animationDelay = "0.5s"; // para que animen luego del header
      section.addEventListener("click", () => {
        const videoUrl = section.getAttribute("data-video");
        videoFrame.src = videoUrl + "?autoplay=1&rel=0";
        modal.style.display = "block";
      });
    });

    closeBtn.addEventListener("click", () => {
      modal.style.display = "none";
      videoFrame.src = "";
    });

    window.addEventListener("click", (e) => {
      if (e.target === modal) {
        modal.style.display = "none";
        videoFrame.src = "";
      }
    });

    // Música ambiental
    const audio = new Audio("https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3");
    audio.loop = true;
    audio.volume = 0.3;

    const musicToggleBtn = document.getElementById("music-toggle");
    const volumeControl = document.getElementById("volume-control");

    musicToggleBtn.addEventListener("click", () => {
      if (audio.paused) {
        audio.play();
        musicToggleBtn.innerHTML = "&#10074;&#10074;"; // pausa icono
      } else {
        audio.pause();
        musicToggleBtn.innerHTML = "&#9658;"; // play icono
      }
    });

    volumeControl.addEventListener("input", () => {
      audio.volume = volumeControl.value;
    });

    // Temporizador de respiración guiada
    const breathStartBtn = document.getElementById("breath-start-btn");
    const breathInstruction = document.getElementById("breath-instruction");
    const breathCircle = document.getElementById("breath-circle");

    let breathInterval;
    let phaseIndex = 0;
    // fases: Inhalar (4s), Retener (4s), Exhalar (6s)
    const phases = [
      { text: "Inhala profundamente...", duration: 4000 },
      { text: "Sostén el aire...", duration: 4000 },
      { text: "Exhala lentamente...", duration: 6000 }
    ];

    function startBreathCycle() {
      phaseIndex = 0;
      breathStartBtn.disabled = true;
      updateBreathPhase();
      breathInterval = setInterval(() => {
        phaseIndex++;
        if (phaseIndex >= phases.length) {
          phaseIndex = 0;
        }
        updateBreathPhase();
      }, phases[phaseIndex].duration);
    }

    function updateBreathPhase() {
      const phase = phases[phaseIndex];
      breathInstruction.textContent = phase.text;
      breathCircle.style.animationDuration = (phase.duration / 1000) + "s";

      if (phaseIndex === 0) { // inhalar: crecer círculo
        breathCircle.style.animationName = "breath-pulse";
      } else if (phaseIndex === 1) { // retener: círculo estable
        breathCircle.style.animationName = "none";
        breathCircle.style.transform = "scale(1.3)";
      } else if (phaseIndex === 2) { // exhalar: encoger círculo
        breathCircle.style.animationName = "breath-exhale";
      }
    }

    // Animación para exhalar (encoger)
    const styleSheet = document.styleSheets[0];
    styleSheet.insertRule(`@keyframes breath-exhale {
      0% { transform: scale(1.3); box-shadow: 0 0 24px rgba(214, 51, 108, 1); }
      100% { transform: scale(1); box-shadow: 0 0 12px rgba(214, 51, 108, 0.8); }
    }`, styleSheet.cssRules.length);

    breathStartBtn.addEventListener("click", () => {
      if (breathInterval) {
        clearInterval(breathInterval);
        breathInterval = null;
        breathStartBtn.textContent = "Iniciar";
        breathInstruction.textContent = "Pulsa \"Iniciar\" para comenzar";
        breathCircle.style.animationName = "none";
        breathCircle.style.transform = "scale(1)";
        breathStartBtn.disabled = false;
      } else {
        startBreathCycle();
        breathStartBtn.textContent = "Detener";
      }
    });

    // Chatbot
    const chatbotToggle = document.getElementById("chatbot-toggle");
    const chatbot = document.getElementById("chatbot");
    const chatbotClose = document.getElementById("chatbot-close");
    const chatbotMessages = document.getElementById("chatbot-messages");
    const chatbotInput = document.getElementById("chatbot-input");
    const chatbotSendBtn = document.getElementById("chatbot-send-btn");

    chatbotToggle.addEventListener("click", () => {
      chatbot.style.display = "flex";
      chatbotToggle.style.display = "none";
      chatbotInput.focus();
      addBotMessage("Hola, soy tu asistente de relajación. ¿En qué puedo ayudarte? Puedes preguntar sobre respiración, meditación, yoga, masajes, música o tiempos de respiración.");
    });

    chatbotClose.addEventListener("click", () => {
      chatbot.style.display = "none";
      chatbotToggle.style.display = "block";
      chatbotMessages.innerHTML = "";
    });

    function addUserMessage(msg) {
      const div = document.createElement("div");
      div.classList.add("chatbot-message", "user");
      div.textContent = msg;
      chatbotMessages.appendChild(div);
      chatbotMessages.scrollTop = chatbotMessages.scrollHeight;
    }

    function addBotMessage(msg) {
      const div = document.createElement("div");
      div.classList.add("chatbot-message", "bot");
      div.textContent = msg;
      chatbotMessages.appendChild(div);
      chatbotMessages.scrollTop = chatbotMessages.scrollHeight;
    }

    function getBotResponse(input) {
      input = input.toLowerCase();
      if (input.includes("respiración") || input.includes("respirar")) {
        return "Para la respiración profunda, inhala contando 4 segundos, retén el aire 4 segundos y exhala lentamente contando 6 segundos.";
      }
      if (input.includes("meditación")) {
        return "La meditación guiada ayuda a calmar la mente. Puedes probar los videos que tenemos en la página para empezar.";
      }
      if (input.includes("yoga")) {
        return "El yoga prenatal mejora la postura y reduce dolores. Recuerda hacer movimientos suaves y consultar con tu especialista.";
      }
      if (input.includes("masaje") || input.includes("masajes")) {
        return "Los masajes relajantes se hacen con movimientos lentos y suaves, evitando presionar el abdomen directamente.";
      }
      if (input.includes("música")) {
        return "Escuchar música relajante puede crear un ambiente armonioso. Usa el reproductor en la esquina inferior izquierda para controlar la música.";
      }
      if (input.includes("tiempo") || input.includes("duración")) {
        return "La respiración profunda sigue un ciclo: inhalar 4 segundos, retener 4 segundos y exhalar 6 segundos.";
      }
      return "Lo siento, no entiendo tu pregunta. Por favor, intenta con otra o pregunta sobre relajación, respiración, yoga, masaje o música.";
    }

    function handleChat() {
      const userInput = chatbotInput.value.trim();
      if (!userInput) return;
      addUserMessage(userInput);
      chatbotInput.value = "";
      setTimeout(() => {
        const response = getBotResponse(userInput);
        addBotMessage(response);
      }, 600);
    }

    chatbotSendBtn.addEventListener("click", handleChat);
    chatbotInput.addEventListener("keydown", e => {
      if (e.key === "Enter") {
        handleChat();
      }
    });

  </script>
</body>
</html>










