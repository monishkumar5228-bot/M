<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width,initial-scale=1.0">
  <title>Student Portfolio</title>

  <!-- General Styles -->
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; font-family: Arial, sans-serif; }
    body { line-height: 1.6; background: #f9f9f9; color: #333; }

    header { background: #333; color: #fff; padding: 1rem; text-align: center; }
    nav { display: flex; justify-content: center; background: #444; flex-wrap: wrap; }
    nav a { color: white; padding: 1rem; text-decoration: none; }
    nav a:hover { background: #666; }

    section { padding: 40px 20px; }
    h2 { margin-bottom: 15px; text-align: center; }

    /* Hero */
    .hero { text-align: center; background: #e2e2e2; padding: 50px 20px; }
    .hero h1 span { color: #e63946; }

    /* About */
    .about-content { display: flex; gap: 20px; align-items: center; justify-content: center; flex-wrap: wrap; }
    .about-content img { width: 200px; border-radius: 10px; }

    /* Projects */
    .project-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; }
    .project-card { background: #fff; padding: 20px; border-radius: 10px; box-shadow: 0 0 5px rgba(0,0,0,0.1); text-align: center; }

    /* Contact */
    form { max-width: 500px; margin: auto; display: flex; flex-direction: column; gap: 10px; }
    input, textarea, button { padding: 10px; border: 1px solid #ccc; border-radius: 5px; }
    button { background: #333; color: white; cursor: pointer; }
    button:hover { background: #555; }

    /* Blog */
    .post { background: white; padding: 15px; margin-bottom: 20px; border-radius: 8px; box-shadow: 0 0 5px rgba(0,0,0,0.1); }

    /* Quiz */
    .quiz-container { background: white; padding: 20px; border-radius: 10px; width: 90%; max-width: 500px; margin: auto; box-shadow: 0 0 10px rgba(0,0,0,0.2); }
    .quiz-container ul { list-style: none; margin-bottom: 20px; }
    .quiz-container li { margin: 10px 0; }
    .quiz-container button { background: #333; color: white; padding: 10px 15px; border: none; border-radius: 5px; cursor: pointer; }
    .quiz-container button:hover { background: #555; }
    .result { font-size: 18px; font-weight: bold; text-align: center; }

    /* Footer */
    footer { text-align: center; background: #333; color: white; padding: 1rem; margin-top: 1rem; }
  </style>
</head>
<body>

  <!-- Header -->
  <header>
    <h1>My Portfolio Website</h1>
    <p>Welcome to my combined projects!</p>
  </header>

  <!-- Navigation -->
  <nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#quiz">Quiz</a>
    <a href="#blog">Blog</a>
    <a href="#responsive">Responsive Page</a>
    <a href="#contact">Contact</a>
  </nav>

  <!-- Hero -->
  <section id="home" class="hero">
    <h1>Hello, I'm <span>MONISHKUMAR</span></h1>
    <p>I am the veti officer</p>
    <a href="#projects"><button>View My Work</button></a>
  </section>

  <!-- About -->
  <section id="about">
    <h2>About Me</h2>
    <div class="about-content">
      <img src="IMG_20250621_081450.jpg" alt="Profile Photo">
      <p>I am a student enthusiastic about technology and design. I love building interactive, user-friendly web applications and exploring new tools in the tech world.</p>
    </div>
  </section>

  <!-- Projects -->
  <section id="projects">
    <h2>My Projects</h2>
    <div class="project-grid">
      <div class="project-card"><h3>Responsive Website</h3><p>A simple responsive layout.</p></div>
      <div class="project-card"><h3>Quiz App</h3><p>JavaScript-based quiz app.</p></div>
      <div class="project-card"><h3>Personal Blog</h3><p>Blogging system using local storage.</p></div>
    </div>
  </section>

  <!-- Quiz App -->
  <section id="quiz">
    <h2>Quiz App</h2>
    <div class="quiz-container" id="quizBox">
      <h2 id="question">Question text</h2>
      <ul>
        <li><label><input type="radio" name="answer" class="answer" id="a"> <span id="a_text">Answer A</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="b"> <span id="b_text">Answer B</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="c"> <span id="c_text">Answer C</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="d"> <span id="d_text">Answer D</span></label></li>
      </ul>
      <button id="submit">Submit</button>
      <div class="result" id="result"></div>
    </div>
  </section>

  <!-- Blog -->
  <section id="blog">
    <h2>My Blog</h2>
    <div class="container" id="postsContainer"></div>
  </section>

  <!-- Responsive Website Section -->
  <section id="responsive">
    <h2>Responsive Page Example</h2>
    <div class="container">
      <div class="content">
        <h3>Main Content</h3>
        <p>This is the main content area. Resize the window to see the responsive effect.</p>
      </div>
      <div class="sidebar">
        <h3>Sidebar</h3>
        <p>This is a sidebar with some extra information or links.</p>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <h2>Contact Me</h2>
    <form id="contact-form">
      <input type="text" id="name" name="user_name" placeholder="Your Name" required>
      <input type="email" id="email" name="user_email" placeholder="Your Email" required>
      <textarea id="message" name="message" placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
    <p id="form-status"></p>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; 2025 MR__ YOGA | All rights reserved</p>
  </footer>

  <!-- Scripts -->
  <script>
    // Quiz App Script
    const quizData = [
      { question: "Which CSS property is used to change the background color?", a: "bgcolor", b: "background", c: "color", d: "background-color", correct: "d" },
      { question: "Which property changes font size?", a: "font-style", b: "text-size", c: "font-size", d: "font", correct: "c" },
      { question: "Which hides an element completely?", a: "hidden", b: "opacity: 0;", c: "display: none;", d: "visibility: hidden;", correct: "c" },
      { question: "Which is used for database?", a: "PHP", b: "MySQL", c: "HTML", d: "CSS", correct: "b" }
    ];
    const quizBox = document.getElementById("quizBox");
    const answerEls = document.querySelectorAll(".answer");
    const questionEl = document.getElementById("question");
    const a_text = document.getElementById("a_text");
    const b_text = document.getElementById("b_text");
    const c_text = document.getElementById("c_text");
    const d_text = document.getElementById("d_text");
    const submitBtn = document.getElementById("submit");
    const resultEl = document.getElementById("result");
    let currentQuiz = 0, score = 0;

    function loadQuiz() {
      deselectAnswers();
      const currentQuizData = quizData[currentQuiz];
      questionEl.innerText = currentQuizData.question;
      a_text.innerText = currentQuizData.a;
      b_text.innerText = currentQuizData.b;
      c_text.innerText = currentQuizData.c;
      d_text.innerText = currentQuizData.d;
    }
    function getSelected() {
      let answer;
      answerEls.forEach((el) => { if (el.checked) answer = el.id; });
      return answer;
    }
    function deselectAnswers() { answerEls.forEach((el) => el.checked = false); }
    submitBtn.addEventListener("click", () => {
      const answer = getSelected();
      if (answer) {
        if (answer === quizData[currentQuiz].correct) score++;
        currentQuiz++;
        if (currentQuiz < quizData.length) loadQuiz();
        else {
          quizBox.innerHTML = `<h2 class="result">You scored ${score}/${quizData.length}</h2><button onclick="location.reload()">Restart</button>`;
        }
      }
    });
    loadQuiz();

    // Blog Script
    function loadPosts() {
      const postsContainer = document.getElementById("postsContainer");
      const posts = JSON.parse(localStorage.getItem("blogPosts")) || [
        { title: "First Blog Post", content: "This is an example blog post.", date: new Date() }
      ];
      postsContainer.innerHTML = "";
      posts.reverse().forEach(post => {
        const postEl = document.createElement("div");
        postEl.classList.add("post");
        postEl.innerHTML = `<h3>${post.title}</h3><small>${new Date(post.date).toLocaleString()}</small><p>${post.content}</p>`;
        postsContainer.appendChild(postEl);
      });
    }
    loadPosts();
  </script>
</body>
</html>
