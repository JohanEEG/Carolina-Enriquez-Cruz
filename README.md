<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Métodos de Relajación en el Embarazo y Parto</title>
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
      transform-origin: center center;
    }
    #breath-instruction {
      font-weight: bold;
      font-size: 18px;
      margin-top: 12px;
      height: 24px;
    }
    #breath-start-btn, #breath-stop-btn {
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
      user-select: none;
      margin-right: 10px;
    }
    #breath-start-btn:hover, #breath-stop-btn:hover {
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
      display: none; /* inicia oculto */
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

    /* NUEVA SECCIÓN: métodos de relajación parto */
    #relax-parto {
      background: #ffe6f0;
      border-radius: 15px;
      padding: 25px 30px;
      box-shadow: 0 0 12px rgba(214, 102, 140, 0.3);
      margin: 25px auto 40px auto;
      max-width: 900px;
      font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
      color: #5a2a3a;
      animation: fadeInUp 1s ease forwards;
    }
    #relax-parto h2 {
      color: #c8336e;
      margin-bottom: 15px;
      text-align: center;
      font-weight: 700;
      letter-spacing: 1.1px;
    }
    #relax-parto h3 {
      color: #a42d5d;
      margin-top: 20px;
      margin-bottom: 8px;
      font-weight: 600;
    }
    #relax-parto p {
      font-size: 1rem;
      line-height: 1.5;
      margin-bottom: 12px;
    }
    #relax-parto img.method-img {
      width: 100%;
      max-width: 320px;
      border-radius: 12px;
      margin: 10px 0 20px 0;
      box-shadow: 0 4px 14px rgba(214, 51, 108, 0.3);
      display: block;
    }
    #relax-parto .method-block {
      margin-bottom: 30px;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 18px;
    }
    #relax-parto .method-text {
      flex: 1 1 55%;
    }
    #relax-parto .method-img-container {
      flex: 1 1 40%;
      text-align: center;
    }
    /* Responsive */
    @media (max-width: 650px) {
      #relax-parto .method-block {
        flex-direction: column;
      }
      #relax-parto .method-img-container,
      #relax-parto .method-text {
        flex: 1 1 100%;
      }
      #relax-parto img.method-img {
        max-width: 100%;
        margin: 12px auto 24px auto;
      }
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
  <section class="no-modal" style="cursor: default; opacity: 1; animation-delay: 0s;">
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
  <section data-video="https://www.youtube.com/embed/inpok4MKVLM" style="opacity: 1; animation-delay: 0.3s;">
    <h2>2. Meditación guiada</h2>
    <p>Escuchar meditaciones grabadas puede ayudarte a mantener la calma y enfocarte en tu bienestar.</p>
  </section>

  <!-- Yoga prenatal video modal -->
  <section data-video="https://www.youtube.com/embed/v7AYKMP6rOE" style="opacity: 1; animation-delay: 0.6s;">
    <h2>3. Yoga prenatal</h2>
    <p>Movimientos suaves diseñados especialmente para embarazadas que mejoran la postura y reducen dolores.</p>
  </section>

  <!-- Masajes texto e imagen -->
  <section class="no-modal" style="cursor: default; opacity: 1; animation-delay: 0.9s;">
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
  <section data-video="https://www.youtube.com/embed/2OEL4P1Rz04" style="opacity: 1; animation-delay: 1.2s;">
    <h2>5. Escuchar música relajante</h2>
    <p>La música suave puede inducir tranquilidad y generar un ambiente armonioso para ti y tu bebé.</p>
  </section>

  <!-- Temporizador respiración guiada -->
  <div id="breath-timer" style="opacity: 1; animation-delay: 1.5s;">
    <div id="breath-instruction">Pulsa "Iniciar" para comenzar</div>
    <div id="breath-circle"></div>
    <button id="breath-start-btn">Iniciar</button>
    <button id="breath-stop-btn" disabled>Detener</button>
  </div>

  <div id="qr" style="opacity: 1; animation-delay: 1.8s;">
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

  <!-- Chatbot -->
  <div id="chatbot">
    <div id="chatbot-header">
      Asistente de Relajación
      <span id="chatbot-close" title="Cerrar">&times;</span>
    </div>
    <div id="chatbot-messages"></div>
    <div id="chatbot-input-container">
      <input type="text" id="chatbot-input" placeholder="Escribe tu pregunta..." autocomplete="off" />
      <button id="chatbot-send-btn" title="Enviar">▶</button>
    </div>
  </div>

  <div id="chatbot-toggle" title="Abrir chat">💬</div>

  <!-- NUEVA SECCIÓN: Métodos de relajación durante el parto -->
  <section id="relax-parto" style="opacity: 1; animation-delay: 2s;">
    <h2>Métodos de Relajación Durante el Parto</h2>

    <div class="method-block">
      <div class="method-text">
        <h3>Relajación muscular progresiva</h3>
        <p>Consiste en tensar y relajar distintos grupos musculares para aliviar la tensión acumulada.</p>
      </div>
      <div class="method-img-container">
        <img src="https://i.imgur.com/6hQFTmk.jpg" alt="Relajación muscular progresiva" class="method-img" />
      </div>
    </div>

    <div class="method-block">
      <div class="method-text">
        <h3>Visualización guiada</h3>
        <p>Imagina un lugar tranquilo y seguro para ayudarte a mantener la calma y manejar el dolor.</p>
      </div>
      <div class="method-img-container">
        <img src="https://i.imgur.com/rUoZZ38.jpg" alt="Visualización guiada" class="method-img" />
      </div>
    </div>

    <div class="method-block">
      <div class="method-text">
        <h3>Masajes durante el parto</h3>
        <p>Un masaje suave en la espalda, hombros o pies puede reducir la ansiedad y mejorar la experiencia.</p>
      </div>
      <div class="method-img-container">
        <img src="https://i.imgur.com/oo0JZX0.jpg" alt="Masajes durante el parto" class="method-img" />
      </div>
    </div>

    <div class="method-block">
      <div class="method-text">
        <h3>Respiración controlada</h3>
        <p>Aprender técnicas respiratorias específicas para mantener el ritmo y evitar el agotamiento.</p>
      </div>
      <div class="method-img-container">
        <img src="https://i.imgur.com/1rJIT3j.jpg" alt="Respiración controlada en parto" class="method-img" />
      </div>
    </div>

  </section>

  <script>
    // Manejo del modal para videos
    const sections = document.querySelectorAll("section[data-video]");
    const modal = document.getElementById("modal");
    const videoFrame = document.getElementById("videoFrame");
    const closeBtn = document.getElementById("closeBtn");

    sections.forEach(sec => {
      sec.addEventListener("click", () => {
        videoFrame.src = sec.getAttribute("data-video") + "?autoplay=1";
        modal.style.display = "block";
      });
    });

    closeBtn.addEventListener("click", () => {
      modal.style.display = "none";
      videoFrame.src = "";
    });

    window.addEventListener("click", (e) => {
      if (e.target == modal) {
        modal.style.display = "none";
        videoFrame.src = "";
      }
    });

    // QR Code generator
    function generarQR() {
      const qrContainer = document.getElementById("codigoQR");
      qrContainer.innerHTML = "";
      const url = encodeURIComponent(window.location.href);
      const qrApi = `https://api.qrserver.com/v1/create-qr-code/?size=180x180&data=${url}`;
      const img = document.createElement("img");
      img.src = qrApi;
      img.alt = "Código QR para compartir la página";
      img.style.borderRadius = "12px";
      qrContainer.appendChild(img);
    }

    // Temporizador respiración guiada
    const breathCircle = document.getElementById("breath-circle");
    const breathInstruction = document.getElementById("breath-instruction");
    const startBtn = document.getElementById("breath-start-btn");
    const stopBtn = document.getElementById("breath-stop-btn");

    let breathInterval = null;
    let step = 0;

    const instructions = [
      { text: "Inhala profundamente", duration: 4000 },
      { text: "Mantén el aire", duration: 4000 },
      { text: "Exhala lentamente", duration: 6000 },
      { text: "Mantén los pulmones vacíos", duration: 4000 }
    ];

    function startBreathing() {
      if (breathInterval) return;
      step = 0;
      breathInstruction.textContent = instructions[step].text;
      breathCircle.style.animation = "breath-pulse 4s ease-in-out infinite";
      startBtn.disabled = true;
      stopBtn.disabled = false;

      breathInterval = setInterval(() => {
        step = (step + 1) % instructions.length;
        breathInstruction.textContent = instructions[step].text;
      }, instructions[step].duration);

      // To sync the timer interval with variable durations
      // we use recursive timeouts instead of fixed setInterval, but to keep it simple:
      // We'll clear and restart the interval with the next duration at each step:
      function cycle() {
        breathInstruction.textContent = instructions[step].text;
        breathInterval = setTimeout(() => {
          step = (step + 1) % instructions.length;
          cycle();
        }, instructions[step].duration);
      }
      cycle();
    }

    function stopBreathing() {
      if (!breathInterval) return;
      clearTimeout(breathInterval);
      breathInterval = null;
      breathInstruction.textContent = 'Pulsa "Iniciar" para comenzar';
      breathCircle.style.animation = "none";
      startBtn.disabled = false;
      stopBtn.disabled = true;
    }

    startBtn.addEventListener("click", startBreathing);
    stopBtn.addEventListener("click", stopBreathing);

    // Chatbot funcionalidad
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
    });

    chatbotClose.addEventListener("click", () => {
      chatbot.style.display = "none";
      chatbotToggle.style.display = "block";
    });

    function appendMessage(msg, sender) {
      const div = document.createElement("div");
      div.classList.add("chatbot-message", sender);
      div.textContent = msg;
      chatbotMessages.appendChild(div);
      chatbotMessages.scrollTop = chatbotMessages.scrollHeight;
    }

    const respuestasGenericas = [
      "Gracias por tu mensaje, estoy aquí para ayudarte.",
      "Eso suena interesante, ¿puedes contarme más?",
      "Recuerda respirar profundamente para relajarte.",
      "¿Quieres que te sugiera un método de relajación?",
      "Estoy aprendiendo, ¿qué técnica te gustaría probar hoy?",
      "No olvides que la calma es tu aliada durante el embarazo.",
      "Si tienes dudas específicas, dime y trataré de ayudarte.",
    ];

    function obtenerRespuesta(userText) {
      const text = userText.toLowerCase();

      if (text.includes("respiración")) {
        return "La respiración profunda puede ayudarte a calmarte. ¿Quieres que te guíe con un temporizador?";
      }
      if (text.includes("masaje")) {
        return "Los masajes suaves alivian tensiones. Recuerda evitar el abdomen directamente.";
      }
      if (text.includes("meditación")) {
        return "La meditación guiada puede ser muy efectiva para tu bienestar emocional.";
      }
      if (text.includes("yoga")) {
        return "El yoga prenatal fortalece tu cuerpo y mente. ¿Quieres un video para empezar?";
      }
      if (text.includes("parto")) {
        return "Durante el parto, técnicas como la respiración controlada y masajes son de gran ayuda.";
      }
      // Respuesta aleatoria si no coincide con nada
      return respuestasGenericas[Math.floor(Math.random() * respuestasGenericas.length)];
    }

    function enviarMensaje() {
      const texto = chatbotInput.value.trim();
      if (texto === "") return;
      appendMessage(texto, "user");
      chatbotInput.value = "";
      setTimeout(() => {
        const respuesta = obtenerRespuesta(texto);
        appendMessage(respuesta, "bot");
      }, 700);
    }

    chatbotSendBtn.addEventListener("click", enviarMensaje);

    chatbotInput.addEventListener("keydown", (e) => {
      if (e.key === "Enter") {
        enviarMensaje();
      }
    });

  </script>

</body>
</html>














