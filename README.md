<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Relajación en Embarazo y Parto</title>
<style>
  body {
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    background: #fff0f6;
    margin: 0; padding: 20px; color: #4a2c3a;
  }
  header {
    text-align: center;
    margin-bottom: 2rem;
  }
  header img {
    max-width: 400px;
    border-radius: 1rem;
    box-shadow: 0 4px 12px rgba(204, 102, 153, 0.3);
  }
  h1 {
    color: #d6336c;
    margin: 0.5rem 0;
  }
  .section {
    background: #ffe6f0;
    border-radius: 1rem;
    padding: 1.25rem 1.5rem;
    margin-bottom: 1.5rem;
    box-shadow: 0 0 10px rgba(214, 102, 140, 0.3);
    cursor: pointer;
    transition: background 0.3s ease, transform 0.3s ease;
  }
  .section:hover {
    background: #f9d1e1;
    transform: scale(1.03);
  }
  .no-cursor {
    cursor: default;
  }
  button {
    background: #d6336c;
    color: #fff;
    border: none;
    border-radius: 0.75rem;
    padding: 0.6rem 1.5rem;
    font-size: 1rem;
    cursor: pointer;
    transition: background 0.3s ease;
    user-select: none;
  }
  button:hover {
    background: #b32456;
  }
  #breath-timer {
    text-align: center;
  }
  #breath-circle {
    width: 120px; height: 120px;
    margin: 1rem auto 0;
    border-radius: 50%;
    background: #f9d1e1;
    border: 6px solid #fff;
    box-shadow: 0 0 12px #d6336c88;
    transition: transform 4s ease-in-out;
  }
  #breath-instruction {
    margin-top: 0.75rem;
    font-weight: 700;
    font-size: 1.1rem;
    min-height: 1.5rem;
  }
  #breath-controls button {
    margin: 1rem 0.5rem 0 0.5rem;
  }
  /* Modal */
  #modal {
    display: none;
    position: fixed; inset: 0;
    background: rgba(0,0,0,0.7);
    z-index: 1000;
    overflow-y: auto;
  }
  #modal[aria-hidden="false"] {
    display: block;
  }
  #modal-content {
    background: #fff;
    max-width: 800px;
    margin: 3rem auto;
    border-radius: 1rem;
    padding: 1rem 1.5rem 2rem;
    position: relative;
    box-shadow: 0 0 25px #c8649f88;
  }
  #modal-content iframe {
    width: 100%; height: 450px;
    border-radius: 0.5rem;
    border: none;
  }
  #modal-close {
    position: absolute;
    top: 0.5rem; right: 1rem;
    font-size: 2rem;
    color: #c8336e;
    background: none;
    border: none;
    cursor: pointer;
  }
  #modal-close:hover {
    color: #a02456;
  }
  #modal-img {
    margin-top: 1rem;
    width: 100%;
    border-radius: 0.75rem;
    box-shadow: 0 2px 8px #c8649f33;
  }
  /* QR */
  #qr {
    text-align: center;
  }
  #qrcode canvas {
    border-radius: 1rem;
    margin-top: 1rem;
  }
  /* Foro */
  #foro {
    background: #fff0f6;
    padding: 1.5rem 1.5rem 2rem;
    border-radius: 1rem;
    box-shadow: 0 0 12px #d6668c33;
  }
  #question-form, .question, .answer-form {
    background: #ffe6f0;
    padding: 1rem 1.25rem;
    border-radius: 1rem;
    margin-bottom: 1rem;
    box-shadow: 0 0 10px #d6668c22;
  }
  input[type="text"], textarea {
    width: 100%;
    padding: 0.5rem 0.75rem;
    font-size: 1rem;
    border: 1.5px solid #d6336c;
    border-radius: 0.75rem;
    font-family: inherit;
    resize: vertical;
    box-sizing: border-box;
  }
  textarea {
    min-height: 3.5rem;
  }
  .question-title {
    font-weight: 700;
    color: #a02a55;
    margin-bottom: 0.25rem;
  }
  .question-text {
    margin-bottom: 0.5rem;
    white-space: pre-wrap;
  }
  .answers {
    margin-top: 0.75rem;
    border-left: 3px solid #d6336c;
    padding-left: 1rem;
  }
  .answer {
    background: #f9d1e1;
    padding: 0.5rem 0.75rem;
    border-radius: 0.75rem;
    margin-bottom: 0.5rem;
    font-size: 0.95rem;
    white-space: pre-wrap;
  }
  .toggle-answers-btn {
    background: none;
    border: none;
    color: #b32456;
    font-weight: 600;
    cursor: pointer;
    padding: 0;
    margin-top: 0.25rem;
    font-size: 0.9rem;
  }
  .toggle-answers-btn:hover {
    text-decoration: underline;
  }
</style>
</head>
<body>

<header>
  <img src="https://images.unsplash.com/photo-1503676260728-1c00da094a0b?auto=format&fit=crop&w=600&q=80" alt="Mujer embarazada" />
  <h1>Relajación en Embarazo y Parto</h1>
  <p>Cuida tu bienestar físico y emocional con cariño y calma.</p>
</header>

<section id="breath-timer" class="section no-cursor" aria-label="Temporizador de respiración guiada">
  <h2>Respiración Guiada</h2>
  <div id="breath-circle" aria-live="polite" aria-atomic="true" aria-relevant="text"></div>
  <div id="breath-instruction" aria-live="assertive" aria-atomic="true" style="min-height:1.5rem;">Presiona Iniciar</div>
  <div id="breath-controls">
    <button id="breath-start-btn" aria-label="Iniciar respiración guiada">Iniciar</button>
    <button id="breath-stop-btn" aria-label="Detener respiración guiada" style="display:none;">Detener</button>
  </div>
</section>

<section id="videos" class="section" tabindex="0" role="button" aria-label="Abrir videos de técnicas de relajación">
  <h2>Videos de Técnicas de Relajación</h2>
  <p>Haz clic para abrir el video tutorial.</p>
</section>

<div id="modal" role="dialog" aria-modal="true" aria-hidden="true" aria-labelledby="modal-title">
  <div id="modal-content">
    <button id="modal-close" aria-label="Cerrar modal">&times;</button>
    <h2 id="modal-title"></h2>
    <iframe src="" allowfullscreen title="Video de técnica de relajación"></iframe>
    <img id="modal-img" alt="" />
  </div>
</div>

<div id="qr" class="section no-cursor" aria-label="Generador de código QR">
  <button id="generate-qr-btn" aria-label="Generar código QR de la página">Generar Código QR</button>
  <div id="qrcode"></div>
</div>

<section id="foro" aria-label="Foro de preguntas y respuestas">
  <h2>Foro: Preguntas y Respuestas</h2>
  <form id="question-form" aria-label="Formulario para agregar pregunta">
    <input type="text" id="question-input" placeholder="Escribe tu pregunta..." required aria-required="true" />
    <button type="submit" aria-label="Enviar pregunta">Enviar Pregunta</button>
  </form>
  <div id="questions-list" aria-live="polite" aria-atomic="true"></div>
</section>

<script src="https://cdn.jsdelivr.net/npm/qrcode/build/qrcode.min.js"></script>
<script>
  // Modal Videos
  const videosSection = document.getElementById('videos');
  const modal = document.getElementById('modal');
  const modalTitle = modal.querySelector('#modal-title');
  const modalIframe = modal.querySelector('iframe');
  const modalImg = modal.querySelector('#modal-img');
  const modalCloseBtn = modal.querySelector('#modal-close');

  const videos = [
    {
      title: "Técnica de Respiración Profunda",
      url: "https://www.youtube.com/embed/3TxZrDyz4SQ",
      imgAlt: "Explicación respiración profunda",
      imgSrc: "https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=800&q=60"
    },
    {
      title: "Masajes Prenatales",
      url: "https://www.youtube.com/embed/2qEvIEkfzsk",
      imgAlt: "Masaje relajante para embarazadas",
      imgSrc: "https://images.unsplash.com/photo-1533473359331-0135ef1b58bf?auto=format&fit=crop&w=800&q=60"
    },
    {
      title: "Yoga para Embarazadas",
      url: "https://www.youtube.com/embed/v7AYKMP6rOE",
      imgAlt: "Yoga prenatal para relajación y fuerza",
      imgSrc: "https://images.unsplash.com/photo-1518611012118-f1d1f1ff58c0?auto=format&fit=crop&w=800&q=60"
    }
  ];

  videosSection.addEventListener('click', () => openModal(videos[0]));
  videosSection.addEventListener('keydown', e => { if(e.key==='Enter' || e.key===' ') { e.preventDefault(); openModal(videos[0]); } });

  function openModal(video) {
    modalTitle.textContent = video.title;
    modalIframe.src = video.url + '?autoplay=1&rel=0';
    modalImg.src = video.imgSrc;
    modalImg.alt = video.imgAlt;
    modal.setAttribute('aria-hidden', 'false');
    document.body.style.overflow = 'hidden';
    modalCloseBtn.focus();
  }
  function closeModal() {
    modal.setAttribute('aria-hidden', 'true');
    modalIframe.src = '';
    document.body.style.overflow = '';
    videosSection.focus();
  }

  modalCloseBtn.addEventListener('click', closeModal);
  modal.addEventListener('click', e => { if(e.target === modal) closeModal(); });
  document.addEventListener('keydown', e => { if(e.key === "Escape" && modal.getAttribute('aria-hidden') === 'false') closeModal(); });

  // Respiración Guiada
  const breathCircle = document.getElementById('breath-circle');
  const breathInstruction = document.getElementById('breath-instruction');
  const breathStartBtn = document.getElementById('breath-start-btn');
  const breathStopBtn = document.getElementById('breath-stop-btn');

  const breathSteps = [
    { text: "Inhala profundo", scale: 1.4, duration: 4000 },
    { text: "Mantén el aire", scale: 1.4, duration: 4000 },
    { text: "Exhala despacio", scale: 0.7, duration: 4000 },
    { text: "Mantén sin aire", scale: 0.7, duration: 4000 }
  ];

  let breathTimerId = null, breathStep = 0;

  function runBreathCycle() {
    const step = breathSteps[breathStep];
    breathInstruction.textContent = step.text;
    breathCircle.style.transform = `scale(${step.scale})`;
    breathTimerId = setTimeout(() => {
      breathStep = (breathStep + 1) % breathSteps.length;
      runBreathCycle();
    }, step.duration);
  }

  breathStartBtn.onclick = () => {
    breathStartBtn.style.display = 'none';
    breathStopBtn.style.display = 'inline-block';
    breathStep = 0;
    runBreathCycle();
  };
  breathStopBtn.onclick = () => {
    clearTimeout(breathTimerId);
    breathInstruction.textContent = 'Presiona Iniciar';
    breathCircle.style.transform = 'scale(1)';
    breathStartBtn.style.display = 'inline-block';
    breathStopBtn.style.display = 'none';
  };

  // Código QR
  const generateQrBtn = document.getElementById('generate-qr-btn');
  const qrcodeContainer = document.getElementById('qrcode');

  generateQrBtn.onclick = () => {
    qrcodeContainer.innerHTML = '';
    QRCode.toCanvas(qrcodeContainer, window.location.href, {
      width: 160, margin: 2,
      color: { dark: '#d6336c', light: '#fff0f6' }
    }, err => err && console.error(err));
  };

  // Foro
  const questionForm = document.getElementById('question-form');
  const questionInput = document.getElementById('question-input');
  const questionsList = document.getElementById('questions-list');

  let questionsData = JSON.parse(localStorage.getItem('questionsData') || '[]');

  function saveQuestions() {
    localStorage.setItem('questionsData', JSON.stringify(questionsData));
  }

  function renderQuestions() {
    questionsList.innerHTML = '';
    if (!questionsData.length) {
      questionsList.innerHTML = '<p>No hay preguntas todavía. Sé el primero en preguntar.</p>';
      return;
    }
    questionsData.forEach((q, i) => {
      const qDiv = document.createElement('div');
      qDiv.className = 'question';
      qDiv.setAttribute('tabindex', '0');

      const answersHTML = q.answers.length
        ? q.answers.map(a => `<div class="answer">${a}</div>`).join('')
        : '<p>No hay respuestas aún.</p>';

      qDiv.innerHTML = `
        <div class="question-title">Pregunta: ${q.text}</div>
        <button class="toggle-answers-btn" aria-expanded="false" aria-controls="answers-${i}">Mostrar respuestas (${q.answers.length})</button>
        <div class="answers" id="answers-${i}" hidden>${answersHTML}
          <form class="answer-form" aria-label="Responder pregunta">
            <textarea rows="2" required placeholder="Escribe tu respuesta..."></textarea>
            <button type="submit">Responder</button>
          </form>
        </div>`;

      const toggleBtn = qDiv.querySelector('.toggle-answers-btn');
      const answersDiv = qDiv.querySelector('.answers');
      const answerForm = qDiv.querySelector('.answer-form');
      const textarea = answerForm.querySelector('textarea');

      toggleBtn.onclick = () => {
        const expanded = toggleBtn.getAttribute('aria-expanded') === 'true';
        toggleBtn.setAttribute('aria-expanded', String(!expanded));
        answersDiv.hidden = expanded;
        toggleBtn.textContent = expanded
          ? `Mostrar respuestas (${q.answers.length})`
          : `Ocultar respuestas (${q.answers.length})`;
      };

      answerForm.onsubmit = e => {
        e.preventDefault();
        const ans = textarea.value.trim();
        if (!ans) return;
        q.answers.push(ans);
        saveQuestions();
        renderQuestions();
      };

      questionsList.appendChild(qDiv);
    });
  }

  questionForm.onsubmit = e => {
    e.preventDefault();
    const qText = questionInput.value.trim();
    if (!qText) return;
    questionsData.push({ text: qText, answers: [] });
    saveQuestions();
    questionInput.value = '';
    renderQuestions();
  };

  renderQuestions();
</script>

</body>
</html>

















