<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Técnicas de Respiración en Labor de Parto</title>
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
    #foro {
  background: #fff0f6;
  padding: 25px;
  border-radius: 15px;
  box-shadow: 0 0 12px rgba(214, 102, 140, 0.3);
  margin-bottom: 60px;
}
#foro form, .question, .answer-form {
  background: #ffe6f0;
  padding: 15px 20px;
  border-radius: 12px;
  box-shadow: 0 0 10px rgba(214, 102, 140, 0.2);
  margin-bottom: 20px;
}
#foro input[type="text"], #foro textarea {
  width: 100%;
  padding: 10px 12px;
  border-radius: 8px;
  border: 1.5px solid #d6336c;
  font-size: 14px;
  box-sizing: border-box;
  resize: vertical;
  font-family: inherit;
}
#foro button {
  background-color: #d6336c;
  color: white;
  border: none;
  padding: 10px 22px;
  border-radius: 12px;
  font-size: 15px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  user-select: none;
  margin-top: 10px;
}
#foro button:hover {
  background-color: #b32456;
}
.question-title {
  font-weight: 700;
  font-size: 18px;
  margin-bottom: 6px;
  color: #a02a55;
}
.question-text {
  font-size: 15px;
  margin-bottom: 8px;
  white-space: pre-wrap;
}
.answers {
  margin-top: 12px;
  padding-left: 12px;
  border-left: 3px solid #d6336c;
}
.answer {
  background: #f9d1e1;
  border-radius: 10px;
  padding: 8px 12px;
  margin-bottom: 8px;
  font-size: 14px;
  color: #4a2c3a;
  white-space: pre-wrap;
}
.toggle-answers-btn {
  background: transparent;
  border: none;
  color: #b32456;
  font-weight: 600;
  cursor: pointer;
  padding: 0;
  margin-top: 6px;
  user-select: none;
  font-size: 14px;
}
.toggle-answers-btn:hover {
  text-decoration: underline;
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
      transition: transform 4s ease-in-out;
      transform-origin: center center;
    }
    #breath-instruction {
      font-weight: bold;
      font-size: 18px;
      margin-top: 12px;
      height: 28px;
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

    
    /* NUEVA SECCIÓN: métodos de relajación parto sin imágenes, textos más desarrollados */
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
      margin-bottom: 20px;
      text-align: justify;
    }
  </style>
</head>
<body>

  <header>
    <h1>Técnicas de Respiración en Labor de Parto</h1>
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

  <!-- NUEVA SECCIÓN: Métodos de relajación durante el parto sin imágenes -->
  <section id="relax-parto" style="opacity: 1; animation-delay: 2s;">
    <h2>Métodos de Relajación Durante el Parto</h2>

    <h3>Relajación muscular progresiva</h3>
    <p>Esta técnica consiste en tensar y luego relajar grupos específicos de músculos de forma consciente, permitiendo aliviar la tensión acumulada en el cuerpo. Durante el parto, puede ayudar a manejar el dolor y la ansiedad, facilitando un estado de calma y control. Es recomendable practicarla en momentos previos para familiarizarse con la sensación.</p>

    <h3>Visualización guiada</h3>
    <p>La visualización guiada implica imaginar escenarios o lugares tranquilos y seguros, lo cual puede ser una poderosa herramienta para centrar la mente y reducir el estrés durante las contracciones. Esta práctica ayuda a desviar la atención del dolor y fortalecer una actitud positiva frente al proceso del parto.</p>

    <h3>Masajes durante el parto</h3>
    <p>Los masajes suaves y focalizados en áreas como la espalda baja, los hombros o los pies pueden aliviar tensiones musculares y disminuir la percepción del dolor. Además, el contacto físico genera una sensación de seguridad y apoyo emocional, fundamentales para un parto más confortable.</p>

    <h3>Respiración controlada</h3>
    <p>Las técnicas de respiración controlada, que incluyen inspiraciones y exhalaciones pausadas, ayudan a mantener un ritmo constante durante las contracciones, evitando el agotamiento. Respirar adecuadamente incrementa el oxígeno disponible para la madre y el bebé, facilitando el proceso de parto y promoviendo la relajación.</p>
  <section id="foro" style="margin-top: 40px;">
  <h2>Foro de Preguntas y Respuestas</h2>

  <form id="question-form">
    <label for="question-title-input">Título de la pregunta</label>
    <input type="text" id="question-title-input" placeholder="Escribe el título de tu pregunta" required maxlength="100" />

    <label for="question-text-input" style="margin-top: 12px;">Detalle / descripción</label>
    <textarea id="question-text-input" placeholder="Describe tu pregunta con más detalle" required maxlength="500"></textarea>

    <button type="submit">Publicar Pregunta</button>
  </form>

  <div id="questions-container">
    <!-- Preguntas se mostrarán aquí -->
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

    // Temporizador respiración guiada con tiempos exactos y animación suave
    const breathCircle = document.getElementById("breath-circle");
    const breathInstruction = document.getElementById("breath-instruction");
    const startBtn = document.getElementById("breath-start-btn");
    const stopBtn = document.getElementById("breath-stop-btn");

    const breathSteps = [
      { text: "Inhala profundamente", duration: 4000, scale: 1.3 },
      { text: "Mantén el aire", duration: 4000, scale: 1.3 },
      { text: "Exhala lentamente", duration: 6000, scale: 0.7 },
      { text: "Mantén los pulmones vacíos", duration: 4000, scale: 0.7 },
    ];

    let breathTimeout = null;
    let breathIndex = 0;
    let running = false;

    function breathCycle() {
      if (!running) return;

      const step = breathSteps[breathIndex];
      breathInstruction.textContent = step.text;

      // Animar círculo según la fase (inhala y mantiene expandido, exhala y mantiene contraído)
      breathCircle.style.transition = `transform ${step.duration}ms ease-in-out`;
      breathCircle.style.transform = `scale(${step.scale})`;

      breathTimeout = setTimeout(() => {
        breathIndex = (breathIndex + 1) % breathSteps.length;
        breathCycle();
      }, step.duration);
    }

    function startBreathing() {
      if (running) return;
      running = true;
      breathIndex = 0;
      startBtn.disabled = true;
      stopBtn.disabled = false;
      breathInstruction.textContent = breathSteps[breathIndex].text;
      breathCircle.style.transform = `scale(${breathSteps[breathIndex].scale})`;
      breathCircle.style.transition = `transform ${breathSteps[breathIndex].duration}ms ease-in-out`;
      breathTimeout = setTimeout(() => {
        breathIndex = (breathIndex + 1) % breathSteps.length;
        breathCycle();
      }, breathSteps[breathIndex].duration);
    }

    function stopBreathing() {
      if (!running) return;
      running = false;
      clearTimeout(breathTimeout);
      breathInstruction.textContent = 'Pulsa "Iniciar" para comenzar';
      breathCircle.style.transition = "transform 0.5s ease";
      breathCircle.style.transform = "scale(1)";
      startBtn.disabled = false;
      stopBtn.disabled = true;
    }

    startBtn.addEventListener("click", startBreathing);
    stopBtn.addEventListener("click", stopBreathing);
    let foroData = JSON.parse(localStorage.getItem('foroPreguntas')) || [];
const questionForm = document.getElementById('question-form');
const questionsContainer = document.getElementById('questions-container');

function guardarDatos() {
  localStorage.setItem('foroPreguntas', JSON.stringify(foroData));
}
function crearPreguntaElement(pregunta) {
  const container = document.createElement('div');
  container.classList.add('question');
  const title = document.createElement('div');
  title.classList.add('question-title');
  title.textContent = pregunta.title;
  container.appendChild(title);

  const text = document.createElement('div');
  text.classList.add('question-text');
  text.textContent = pregunta.text;
  container.appendChild(text);

  const toggleBtn = document.createElement('button');
  toggleBtn.classList.add('toggle-answers-btn');
  toggleBtn.textContent = `Mostrar respuestas (${pregunta.answers.length})`;
  container.appendChild(toggleBtn);

  const answersDiv = document.createElement('div');
  answersDiv.classList.add('answers');
  answersDiv.style.display = 'none';

  pregunta.answers.forEach((respuesta) => {
    const ans = document.createElement('div');
    ans.classList.add('answer');
    ans.textContent = respuesta;
    answersDiv.appendChild(ans);
  });
  container.appendChild(answersDiv);

  const answerForm = document.createElement('form');
  answerForm.classList.add('answer-form');
  answerForm.style.display = 'none';

  const answerTextarea = document.createElement('textarea');
  answerTextarea.setAttribute('placeholder', 'Escribe tu respuesta aquí');
  answerTextarea.required = true;
  answerTextarea.maxLength = 300;
  answerForm.appendChild(answerTextarea);

  const answerSubmitBtn = document.createElement('button');
  answerSubmitBtn.type = 'submit';
  answerSubmitBtn.textContent = 'Responder';
  answerForm.appendChild(answerSubmitBtn);

  container.appendChild(answerForm);

  toggleBtn.addEventListener('click', () => {
    if (answersDiv.style.display === 'none') {
      answersDiv.style.display = 'block';
      answerForm.style.display = 'block';
      toggleBtn.textContent = `Ocultar respuestas (${pregunta.answers.length})`;
    } else {
      answersDiv.style.display = 'none';
      answerForm.style.display = 'none';
      toggleBtn.textContent = `Mostrar respuestas (${pregunta.answers.length})`;
    }
  });

  answerForm.addEventListener('submit', e => {
    e.preventDefault();
    const nuevaRespuesta = answerTextarea.value.trim();
    if (!nuevaRespuesta) return;
    const index = foroData.findIndex(q => q.id === pregunta.id);
    if (index >= 0) {
      foroData[index].answers.push(nuevaRespuesta);
      guardarDatos();
      const ans = document.createElement('div');
      ans.classList.add('answer');
      ans.textContent = nuevaRespuesta;
      answersDiv.appendChild(ans);
      answerTextarea.value = '';
      toggleBtn.textContent = `Ocultar respuestas (${foroData[index].answers.length})`;
    }
  });

  return container;
}

function renderizarPreguntas() {
  questionsContainer.innerHTML = '';
  if (foroData.length === 0) {
    questionsContainer.textContent = 'No hay preguntas todavía. Sé el primero en publicar una.';
    return;
  }
  foroData.forEach(pregunta => {
    const preguntaElem = crearPreguntaElement(pregunta);
    questionsContainer.appendChild(preguntaElem);
  });
}

questionForm.addEventListener('submit', e => {
  e.preventDefault();
  const titulo = document.getElementById('question-title-input').value.trim();
  const texto = document.getElementById('question-text-input').value.trim();
  if (!titulo || !texto) return;
  const nuevaPregunta = {
    id: Date.now(),
    title: titulo,
    text: texto,
    answers: []
  };
  foroData.unshift(nuevaPregunta);
  guardarDatos();
  renderizarPreguntas();
  questionForm.reset();
});

renderizarPreguntas();


    
  </script>
</body>
</html>
















