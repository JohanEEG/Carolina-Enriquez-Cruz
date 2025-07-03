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
  <section id="relax-parto" style="opacity: 1; animation-delay: 2.1s;">
    <h2>Métodos de Relajación Durante el Parto</h2>
    
    <div class="method-block">
      <div class="method-text">
        <h3>1. Respiración controlada</h3>
        <p>Respirar lenta y profundamente ayuda a oxigenar mejor tu cuerpo y a mantener la calma. Se recomienda usar técnicas como la respiración abdominal o respiración rítmica, inspirando por la nariz y exhalando por la boca de forma pausada.</p>
      </div>
      <div class="method-img-container">
        <img class="method-img" src="https://i.imgur.com/5QrDsY1.png" alt="Mujer realizando respiración controlada" />
      </div>
    </div>

    <div class="method-block">
      <div class="method-text">
        <h3>2. Visualización y enfoque mental</h3>
        <p>Imagina un lugar tranquilo y seguro o visualiza cómo cada contracción acerca a tu bebé a tus brazos. Este enfoque mental positivo puede disminuir la sensación de dolor y mejorar tu bienestar emocional.</p>
      </div>
      <div class="method-img-container">
        <img class="method-img" src="https://i.imgur.com/jPztpYu.png" alt="Mujer en meditación visualización" />
      </div>
    </div>

    <div class="method-block">
      <div class="method-text">
        <h3>3. Masajes y presión</h3>
        <p>El masaje suave en la zona lumbar o presión firme en puntos específicos puede aliviar tensiones y el dolor durante las contracciones. Tu acompañante o personal de salud puede ayudarte con estas técnicas.</p>
      </div>
      <div class="method-img-container">
        <img class="method-img" src="https://i.imgur.com/GIURnsW.png" alt="Masaje lumbar para aliviar dolor" />
      </div>
    </div>

    <div class="method-block">
      <div class="method-text">
        <h3>4. Movimiento y postura</h3>
        <p>Adoptar posiciones cómodas, como caminar, balancearte en una pelota de parto, o cambiar de postura regularmente puede facilitar el avance del trabajo de parto y disminuir molestias.</p>
      </div>
      <div class="method-img-container">
        <img class="method-img" src="https://i.imgur.com/VDZvTfH.png" alt="Mujer embarazada usando pelota de parto" />
      </div>
    </div>

    <div class="method-block">
      <div class="method-text">
        <h3>5. Técnicas de relajación muscular progresiva</h3>
        <p>Consiste en tensar y luego relajar grupos musculares específicos para liberar la tensión corporal. Esta técnica ayuda a disminuir la rigidez y promover una sensación general de calma.</p>
      </div>
      <div class="method-img-container">
        <img class="method-img" src="https://i.imgur.com/ky9dP7I.png" alt="Ejemplo relajación muscular progresiva" />
      </div>
    </div>

    <div class="method-block">
      <div class="method-text">
        <h3>6. Uso de música y ambiente calmado</h3>
        <p>Escuchar música suave o sonidos de la naturaleza crea un ambiente relajante que puede ayudar a reducir el estrés y el dolor.</p>
      </div>
      <div class="method-img-container">
        <img class="method-img" src="https://i.imgur.com/Z1TxZWb.png" alt="Ambiente relajante con música" />
      </div>
    </div>

    <div class="method-block">
      <div class="method-text">
        <h3>7. Apoyo emocional y presencia de un acompañante</h3>
        <p>Sentirse acompañada y apoyada durante el parto es clave para mantener la tranquilidad. La presencia de una persona de confianza brinda seguridad y ayuda a manejar el proceso con mayor confianza.</p>
      </div>
      <div class="method-img-container">
        <img class="method-img" src="https://i.imgur.com/7FyV3qn.png" alt="Apoyo emocional durante el parto" />
      </div>
    </div>
    
    <p style="text-align:center; font-style: italic; margin-top: 30px;">
      Recuerda que cada mujer es única. Consulta siempre con tu médico o partera para adaptar estas técnicas a tus necesidades y condiciones personales.
    </p>
  </section>

  <script src="https://cdn.jsdelivr.net/npm/qrcode/build/qrcode.min.js"></script>
  <script>
    // Modal video
    const modal = document.getElementById("modal");
    const videoFrame = document.getElementById("videoFrame");
    const closeBtn = document.getElementById("closeBtn");
    const sections = document.querySelectorAll("section[data-video]");
    sections.forEach(section => {
      section.addEventListener("click", () => {
        const videoUrl = section.getAttribute("data-video");
        videoFrame.src = videoUrl + "?autoplay=1";
        modal.style.display = "block";
      });
    });
    closeBtn.addEventListener("click", () => {
      videoFrame.src = "";
      modal.style.display = "none";
    });
    window.addEventListener("click", e => {
      if (e.target == modal) {
        videoFrame.src = "";
        modal.style.display = "none";
      }
    });

    // QR code generation
    function generarQR() {
      const url = window.location.href;
      const qrContainer = document.getElementById("codigoQR");
      qrContainer.innerHTML = "";
      QRCode.toCanvas(url, { width: 160 }, (error, canvas) => {
        if (error) {
          alert("Error generando código QR");
          return;
        }
        qrContainer.appendChild(canvas);
      });
    }

    // Temporizador respiración guiada
    const breathInstruction = document.getElementById("breath-instruction");
    const breathCircle = document.getElementById("breath-circle");
    const breathStartBtn = document.getElementById("breath-start-btn");
    const breathStopBtn = document.getElementById("breath-stop-btn");

    let breathInterval = null;
    let breathStep = 0;
    const breathSteps = [
      { text: "Inhala lentamente", duration: 4000 },
      { text: "Mantén el aire", duration: 4000 },
      { text: "Exhala lentamente", duration: 6000 },
      { text: "Mantén los pulmones vacíos", duration: 4000 }
    ];

    function animateBreath(step) {
      if (step === 0) {
        breathCircle.style.transform = "scale(1.3)";
        breathCircle.style.boxShadow = "0 0 24px rgba(214, 51, 108, 1)";
      } else if (step === 2) {
        breathCircle.style.transform = "scale(1)";
        breathCircle.style.boxShadow = "0 0 12px rgba(214, 51, 108, 0.8)";
      }
    }

    function startBreathTimer() {
      if (breathInterval) return; // Ya está corriendo

      breathStep = 0;
      breathInstruction.textContent = breathSteps[breathStep].text;
      animateBreath(breathStep);
      breathInterval = setInterval(() => {
        breathStep = (breathStep + 1) % breathSteps.length;
        breathInstruction.textContent = breathSteps[breathStep].text;
        animateBreath(breathStep);
      }, breathSteps[breathStep].duration);

      breathStartBtn.disabled = true;
      breathStopBtn.disabled = false;
    }

    function stopBreathTimer() {
      clearInterval(breathInterval);
      breathInterval = null;
      breathInstruction.textContent = "Pulsa \"Iniciar\" para comenzar";
      breathCircle.style.transform = "scale(1)";
      breathCircle.style.boxShadow = "0 0 12px rgba(214, 51, 108, 0.8)";
      breathStartBtn.disabled = false;
      breathStopBtn.disabled = true;
    }

    breathStartBtn.addEventListener("click", () => {
      startBreathTimer();
    });
    breathStopBtn.addEventListener("click", () => {
      stopBreathTimer();
    });

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

    // Respuestas básicas
    const respuestas = {
      "hola": "¡Hola! ¿En qué puedo ayudarte con la relajación durante el embarazo o parto?",
      "respiración": "La respiración profunda y controlada es clave para relajarte. Puedes probar la técnica de inhalar contando hasta 4, mantener, y exhalar lentamente.",
      "masaje": "Los masajes suaves en la espalda baja y hombros ayudan a aliviar tensiones. Recuerda siempre ser cuidadosa y consultar con un especialista.",
      "yoga": "El yoga prenatal mejora la postura y reduce molestias. Existen muchas rutinas suaves y específicas para embarazadas.",
      "parto": "Durante el parto, técnicas como la respiración controlada, visualización y movimiento pueden ayudarte a manejar el dolor y mantener la calma.",
      "gracias": "¡De nada! Estoy aquí para ayudarte cuando quieras.",
      "adiós": "¡Hasta luego! Te deseo mucha calma y bienestar."
    };

    function responderUsuario(input) {
      const texto = input.toLowerCase().trim();
      // Buscar palabra clave en respuestas
      for (const clave in respuestas) {
        if (texto.includes(clave)) {
          return respuestas[clave];
        }
      }
      return "Lo siento, no entendí eso. Puedes preguntarme sobre respiración, masaje, yoga o parto.";
    }

    function agregarMensaje(text, tipo) {
      const div = document.createElement("div");
      div.classList.add("chatbot-message", tipo);
      div.textContent = text;
      chatbotMessages.appendChild(div);
      chatbotMessages.scrollTop = chatbotMessages.scrollHeight;
    }

    function enviarMensaje() {
      const textoUsuario = chatbotInput.value.trim();
      if (!textoUsuario) return;
      agregarMensaje(textoUsuario, "user");
      chatbotInput.value = "";
      setTimeout(() => {
        const respuestaBot = responderUsuario(textoUsuario);
        agregarMensaje(respuestaBot, "bot");
      }, 600);
    }

    chatbotSendBtn.addEventListener("click", enviarMensaje);
    chatbotInput.addEventListener("keypress", e => {
      if (e.key === "Enter") {
        enviarMensaje();
      }
    });
  </script>
</body>
</html>













