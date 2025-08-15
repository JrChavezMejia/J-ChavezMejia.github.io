<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Administración I - CUNOC | CCEE - Sección B | Dr. José Rodolfo Chávez Mejía</title>
  <style>
    :root {
      --primary-color: #4e73df;
      --secondary-color: #1cc88a;
      --dark-color: #333;
      --medium-color: #555;
      --light-color: #f0f4f8;
      --white: #fff;
      --shadow: 0 4px 8px rgba(0,0,0,0.1);
      --border-radius: 8px;
      --transition: all 0.3s ease;
    }
    
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    
    body {
      background: var(--light-color);
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      line-height: 1.6;
      color: var(--dark-color);
      padding: 0 10px;
      min-height: 100vh;
    }
    
    .container {
      width: 100%;
      max-width: 1100px;
      margin: 20px auto;
      padding: 0 15px;
    }
    
    header {
      text-align: center;
      margin-bottom: 30px;
    }
    
    header h1 {
      font-size: 1.8rem;
      color: var(--dark-color);
      margin-bottom: 10px;
      line-height: 1.3;
    }
    
    header h2 {
      font-size: 1.3rem;
      color: var(--primary-color);
      margin-bottom: 5px;
    }
    
    header p {
      color: var(--medium-color);
      font-size: 1rem;
    }
    
    .section-title {
      color: var(--dark-color);
      margin-bottom: 20px;
      text-align: center;
    }
    
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 25px;
      margin-bottom: 40px;
    }
    
    .card {
      width: 100%;
      height: 160px;
      perspective: 1000px;
      cursor: pointer;
    }
    
    .card-inner {
      position: relative;
      width: 100%;
      height: 100%;
      transition: transform 0.6s ease;
      transform-style: preserve-3d;
    }
    
    .card.flipped .card-inner {
      transform: rotateY(180deg);
    }
    
    .card-face {
      position: absolute;
      width: 100%;
      height: 100%;
      backface-visibility: hidden;
      border-radius: var(--border-radius);
      box-shadow: var(--shadow);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 15px;
      text-align: center;
      transition: var(--transition);
    }
    
    .card-face.front {
      background: var(--primary-color);
      color: var(--white);
      font-weight: 500;
    }
    
    .card-face.back {
      background: var(--secondary-color);
      color: var(--white);
      transform: rotateY(180deg);
      font-size: 0.95rem;
    }
    
    .card-face.back a {
      margin-top: 10px;
      color: var(--white);
      text-decoration: underline;
      font-size: 0.85rem;
      transition: var(--transition);
    }
    
    .card-face.back a:hover {
      opacity: 0.9;
    }
    
    .content-section {
      background: var(--white);
      border-radius: var(--border-radius);
      padding: 25px;
      margin-bottom: 30px;
      box-shadow: var(--shadow);
    }
    
    .resources-list {
      list-style: none;
    }
    
    .resources-list li {
      margin: 12px 0;
      padding-left: 20px;
      position: relative;
    }
    
    .resources-list li::before {
      content: "→";
      position: absolute;
      left: 0;
      color: var(--primary-color);
    }
    
    .resources-list a {
      color: var(--primary-color);
      text-decoration: none;
      transition: var(--transition);
    }
    
    .resources-list a:hover {
      text-decoration: underline;
      color: #2e59d9;
    }
    
    .quiz-container {
      position: relative;
    }
    
    #question {
      font-size: 1.1rem;
      margin-bottom: 20px;
      color: var(--medium-color);
      text-align: center;
    }
    
    .option-button {
      display: block;
      width: 100%;
      max-width: 500px;
      margin: 10px auto;
      padding: 12px;
      background: var(--primary-color);
      color: var(--white);
      border: none;
      border-radius: var(--border-radius);
      cursor: pointer;
      font-size: 1rem;
      transition: var(--transition);
    }
    
    .option-button:hover {
      background: #2e59d9;
      transform: translateY(-2px);
    }
    
    #feedback {
      margin: 15px 0;
      min-height: 1.5em;
      font-weight: 500;
      text-align: center;
    }
    
    .button {
      padding: 10px 20px;
      background: var(--secondary-color);
      color: var(--white);
      border: none;
      border-radius: var(--border-radius);
      cursor: pointer;
      transition: var(--transition);
      font-size: 1rem;
      display: block;
      margin: 15px auto 0;
    }
    
    .button:hover {
      background: #17a673;
      transform: translateY(-2px);
    }
    
    footer {
      text-align: center;
      font-size: 0.85rem;
      color: var(--medium-color);
      border-top: 1px solid #ddd;
      padding-top: 15px;
      margin-top: 30px;
    }
    
    @media (max-width: 768px) {
      header h1 {
        font-size: 1.5rem;
      }
      
      .grid {
        grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
        gap: 15px;
      }
      
      .card {
        height: 140px;
      }
    }
    
    @media (max-width: 480px) {
      .container {
        padding: 0 10px;
      }
      
      header h1 {
        font-size: 1.3rem;
      }
      
      .content-section {
        padding: 20px 15px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1>Administración I - CUNOC</h1>
      <h2>División de CCEE - Sección B</h2>
      <p>Dr. José Rodolfo Chávez Mejía</p>
      <p>Unidad 1: Definición | Objetivos | Importancia | Características | Niveles | Habilidades | Valores Institucionales | Relaciones con Ciencias Sociales</p>
    </header>

    <!-- Flashcards -->
    <h2 class="section-title">Conceptos Clave</h2>
    <div class="grid">
      <div class="card" onclick="this.classList.toggle('flipped')">
        <div class="card-inner">
          <div class="card-face front">Definición</div>
          <div class="card-face back">
            Proceso mediante el cual se planifican, organizan, dirigen y controlan los recursos para alcanzar objetivos organizacionales.
            <a href="https://scholar.google.es/scholar?q=Definici%C3%B3n+administraci%C3%B3n+Chiavenato" target="_blank" rel="noopener noreferrer">Chiavenato - Definición</a>
          </div>
        </div>
      </div>
      
      <div class="card" onclick="this.classList.toggle('flipped')">
        <div class="card-inner">
          <div class="card-face front">Objetivos</div>
          <div class="card-face back">
            Metas específicas que orientan las acciones y recursos de una organización.
            <a href="https://scholar.google.es/scholar?q=Objetivos+administraci%C3%B3n+Koontz+Weihrich" target="_blank" rel="noopener noreferrer">Koontz & Weihrich - Objetivos</a>
          </div>
        </div>
      </div>
      
      <div class="card" onclick="this.classList.toggle('flipped')">
        <div class="card-inner">
          <div class="card-face front">Importancia</div>
          <div class="card-face back">
            Permite optimizar recursos, mejorar eficiencia y lograr los fines organizacionales.
            <a href="https://scholar.google.es/scholar?q=Importancia+administraci%C3%B3n+Stoner" target="_blank" rel="noopener noreferrer">Stoner - Importancia</a>
          </div>
        </div>
      </div>
      
      <div class="card" onclick="this.classList.toggle('flipped')">
        <div class="card-inner">
          <div class="card-face front">Características</div>
          <div class="card-face back">
            Racionalidad, universalidad, flexibilidad, eficacia y eficiencia.
            <a href="https://scholar.google.es/scholar?q=Caracter%C3%ADsticas+administraci%C3%B3n+Griffin" target="_blank" rel="noopener noreferrer">Griffin - Características</a>
          </div>
        </div>
      </div>
      
      <div class="card" onclick="this.classList.toggle('flipped')">
        <div class="card-inner">
          <div class="card-face front">Niveles</div>
          <div class="card-face back">
            Alta dirección, mandos medios y nivel operativo, cada uno con funciones diferenciadas.
            <a href="https://scholar.google.es/scholar?q=Niveles+administraci%C3%B3n+Robbins" target="_blank" rel="noopener noreferrer">Robbins - Niveles</a>
          </div>
        </div>
      </div>
      
      <div class="card" onclick="this.classList.toggle('flipped')">
        <div class="card-inner">
          <div class="card-face front">Habilidades</div>
          <div class="card-face back">
            Técnicas, humanas y conceptuales, según el nivel administrativo.
            <a href="https://scholar.google.es/scholar?q=Habilidades+administrativas+Katz" target="_blank" rel="noopener noreferrer">Katz - Habilidades</a>
          </div>
        </div>
      </div>
      
      <div class="card" onclick="this.classList.toggle('flipped')">
        <div class="card-inner">
          <div class="card-face front">Valores Institucionales</div>
          <div class="card-face back">
            Principios éticos que guían el comportamiento organizacional (honestidad, responsabilidad, respeto, etc.).
            <a href="https://scholar.google.es/scholar?q=Valores+institucionales+administraci%C3%B3n" target="_blank" rel="noopener noreferrer">Referencias sobre Valores</a>
          </div>
        </div>
      </div>
      
      <div class="card" onclick="this.classList.toggle('flipped')">
        <div class="card-inner">
          <div class="card-face front">Relaciones con Ciencias Sociales</div>
          <div class="card-face back">
            La administración se relaciona con psicología, sociología, economía, derecho y antropología, entre otras.
            <a href="https://scholar.google.es/scholar?q=Relaciones+administraci%C3%B3n+ciencias+sociales" target="_blank" rel="noopener noreferrer">Estudios interdisciplinarios</a>
          </div>
        </div>
      </div>
    </div>

    <!-- Recursos Adicionales -->
    <div class="content-section">
      <h2 class="section-title">Recursos Adicionales</h2>
      <ul class="resources-list">
        <li><a href="https://www.google.com/books/edition/Administraci%C3%B3n" target="_blank" rel="noopener noreferrer">Libros de Administración en Google Books</a></li>
        <li><a href="https://www.jstor.org/action/doBasicSearch?Query=administraci%C3%B3n" target="_blank" rel="noopener noreferrer">Artículos académicos en JSTOR</a></li>
        <li><a href="https://www.scielo.org.mx/" target="_blank" rel="noopener noreferrer">Revistas científicas en SciELO</a></li>
        <li><a href="https://www.redalyc.org/" target="_blank" rel="noopener noreferrer">Red de Revistas Científicas de América Latina</a></li>
      </ul>
    </div>

    <!-- Quiz -->
    <div class="content-section quiz-container">
      <h2 class="section-title">Evaluación de Conceptos</h2>
      <div id="question"></div>
      <button class="option-button" data-option="0"></button>
      <button class="option-button" data-option="1"></button>
      <button class="option-button" data-option="2"></button>
      <button class="option-button" data-option="3"></button>
      <div id="feedback"></div>
      <button id="next" class="button">Siguiente Pregunta</button>
      <div id="score" style="text-align: center; margin-top: 15px;"></div>
    </div>

    <footer>
      <p>© 2023 Administración I - CUNOC | Material didáctico para la Sección B</p>
      <p>Dr. José Rodolfo Chávez Mejía</p>
    </footer>
  </div>

  <script>
    // Variables para el quiz
    let currentQuestion = 0;
    let score = 0;
    const questions = [
      {
        question: "¿Cuál es el primer paso del proceso administrativo según la mayoría de autores?",
        options: ["Planificación", "Organización", "Dirección", "Control"],
        answer: 0,
        concept: "Definición"
      },
      {
        question: "¿Qué tipo de habilidades son más importantes para los gerentes de nivel alto?",
        options: ["Habilidades técnicas", "Habilidades humanas", "Habilidades conceptuales", "Habilidades operativas"],
        answer: 2,
        concept: "Habilidades"
      },
      {
        question: "¿Cuál de estas NO es una característica de la administración?",
        options: ["Universalidad", "Flexibilidad", "Eficiencia", "Centralización"],
        answer: 3,
        concept: "Características"
      },
      {
        question: "¿Cuál de estos es un valor institucional fundamental en administración?",
        options: ["Honestidad", "Rigidez", "Individualismo", "Improvisación"],
        answer: 0,
        concept: "Valores Institucionales"
      },
      {
        question: "¿Con cuál de estas ciencias sociales se relaciona más directamente la administración?",
        options: ["Astronomía", "Geología", "Psicología", "Física cuántica"],
        answer: 2,
        concept: "Relaciones con Ciencias Sociales"
      },
      {
        question: "¿Qué nivel administrativo se enfoca en la implementación de tareas específicas?",
        options: ["Alta dirección", "Mando medio", "Nivel operativo", "Nivel estratégico"],
        answer: 2,
        concept: "Niveles"
      },
      {
        question: "¿Cuál es el principal objetivo de la administración?",
        options: ["Maximizar ganancias", "Alcanzar objetivos organizacionales", "Reducir costos", "Aumentar la productividad"],
        answer: 1,
        concept: "Objetivos"
      }
    ];

    // Elementos del DOM
    const questionElement = document.getElementById('question');
    const feedbackElement = document.getElementById('feedback');
    const nextButton = document.getElementById('next');
    const scoreElement = document.getElementById('score');
    const optionButtons = document.querySelectorAll('.option-button');

    // Mostrar la pregunta actual
    function showQuestion() {
      const question = questions[currentQuestion];
      questionElement.textContent = question.question;
      
      optionButtons.forEach((button, index) => {
        button.textContent = question.options[index];
        button.style.backgroundColor = '';
        button.disabled = false;
      });
      
      feedbackElement.textContent = '';
      nextButton.style.display = 'none';
    }

    // Verificar la respuesta seleccionada
    optionButtons.forEach(button => {
      button.addEventListener('click', function() {
        const selectedOption = parseInt(this.getAttribute('data-option'));
        const question = questions[currentQuestion];
        
        optionButtons.forEach(btn => {
          btn.disabled = true;
        });
        
        if (selectedOption === question.answer) {
          this.style.backgroundColor = '#1cc88a';
          feedbackElement.textContent = `¡Correcto! (Concepto: ${question.concept})`;
          feedbackElement.style.color = '#1cc88a';
          score++;
        } else {
          this.style.backgroundColor = '#e74a3b';
          optionButtons[question.answer].style.backgroundColor = '#1cc88a';
          feedbackElement.textContent = `Incorrecto. La respuesta correcta es: ${question.options[question.answer]} (Concepto: ${question.concept})`;
          feedbackElement.style.color = '#e74a3b';
        }
        
        scoreElement.textContent = `Puntuación: ${score} de ${currentQuestion + 1}`;
        nextButton.style.display = 'block';
      });
    });

    // Avanzar a la siguiente pregunta
    nextButton.addEventListener('click', function() {
      currentQuestion++;
      if (currentQuestion < questions.length) {
        showQuestion();
      } else {
        const percentage = Math.round((score / questions.length) * 100);
        questionElement.textContent = `¡Cuestionario completado! Tu puntuación final es: ${score} de ${questions.length} (${percentage}%)`;
        questionElement.style.fontWeight = 'bold';
        questionElement.style.color = percentage >= 70 ? '#1cc88a' : percentage >= 50 ? '#f6c23e' : '#e74a3b';
        
        optionButtons.forEach(button => {
          button.style.display = 'none';
        });
        this.style.display = 'none';
        feedbackElement.textContent = '';
        scoreElement.textContent = '';
      }
    });

    // Iniciar el quiz
    showQuestion();
  </script>
</body>
</html>
