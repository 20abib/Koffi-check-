# Koffi-check-
Application <!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Bienvenue à vous Flambeaux et Lumière</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0; padding: 0;
      background-color: #121212;
      color: #fff;
    }
    header {
      background: #4CAF50;
      padding: 15px;
      text-align: center;
    }
    nav {
      background: #2E7D32;
      padding: 10px;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
    nav button {
      margin: 5px;
      padding: 10px 20px;
      background: #66BB6A;
      border: none;
      color: white;
      font-weight: bold;
      border-radius: 5px;
    }
    section {
      padding: 20px;
      display: none;
    }
    .active {
      display: block;
    }
  </style>
</head>
<body>

<header>
  <h1>🔥 Bienvenue à vous Flambeaux et Lumière 🔥</h1>
  <p>Être un flambeau qui éclaire, une lumière qui brille pour Christ</p>
</header>

<nav>
  <button onclick="showSection('verset')">Verset du jour</button>
  <button onclick="showSection('priere')">Prière</button>
  <button onclick="showSection('quiz')">Quiz biblique</button>
  <button onclick="showSection('chants')">Chants</button>
  <button onclick="showSection('calendrier')">Calendrier</button>
  <button onclick="showSection('formation')">Formation</button>
  <button onclick="showSection('temoignage')">Témoignage</button>
</nav>

<section id="verset" class="active">
  <h2>📖 Verset du jour</h2>
  <p><em>"Vous êtes la lumière du monde." - Matthieu 5:14</em></p>
</section>

<section id="priere">
  <h2>🙏 Prière du jour</h2>
  <p>Seigneur, fais de moi un instrument de ta paix. Là où est la haine, que je mette l’amour. Là où est le doute, que je mette la foi. Amen.</p>
</section><section id="quiz">
  <h2>🧠 Quiz biblique</h2>
  <div id="question"></div>
  <div id="options"></div>
  <p id="score">Score : 0</p>
</section>

<section id="chants">
  <h2>🎶 Chants Flambeau</h2>
  <ul>
    <li><strong>Chant 1 : Marche avec Jésus</strong><br>
      🎵 Marche avec Jésus, ne regarde pas en arrière,<br>
      Tiens ferme ta foi, il est ton bon berger.
    </li><br>
    <li><strong>Chant 2 : Lumière du monde</strong><br>
      🎵 Tu es la lumière du monde, une ville sur la colline,<br>
      Brille de la gloire de Dieu !
    </li>
  </ul>
</section><section id="calendrier">
  <h2>📅 Calendrier des activités</h2>
  <ul>
    <li><strong>Samedi :</strong> Réunion de groupe à 15h</li>
    <li><strong>Dimanche :</strong> Culte avec animation jeunesse</li>
    <li><strong>Mercredi :</strong> Étude biblique sur Zoom à 20h</li>
    <li><strong>Mensuel :</strong> Camp ou sortie missionnaire</li>
  </ul>
</section>

<section id="formation">
  <h2>📖 Formation biblique</h2>
  <h3>Thème : Le salut en Jésus-Christ</h3>
  <p><strong>1. Qu’est-ce que le salut ?</strong><br>
    Le salut est le pardon de nos péchés par la foi en Jésus-Christ. Il nous donne la vie éternelle.
  </p>
  <p><strong>2. Pourquoi avons-nous besoin d’être sauvés ?</strong><br>
    Car tous ont péché et sont privés de la gloire de Dieu (Romains 3:23).
  </p>
  <p><strong>3. Comment recevoir le salut ?</strong><br>
    En confessant nos péchés, croyant en Jésus et le recevant comme Sauveur et Seigneur.
  </p>
</section>

<section id="temoignage">
  <h2>🛐 Coin Témoignage & Méditation</h2>
  <p><em>Témoignage :</em> “J’étais perdu, mais Jésus m’a trouvé. Depuis que je l’ai accepté, ma vie a changé. Il m’a libéré de la peur.” – Flambeau Junior</p>
  <p><strong>Méditation :</strong><br>
    <em>"Confie-toi en l’Éternel de tout ton cœur, et ne t’appuie pas sur ta sagesse." – Proverbes 3:5</em>
  </p>
</section>

<script>
  function showSection(id) {
    document.querySelectorAll("section").forEach(s => s.classList.remove("active"));
    document.getElementById(id).classList.add("active");
  }

  // Quiz Biblique
  const questions = [
    {
      q: "Quel est le premier livre de la Bible ?",
      options: ["Exode", "Genèse", "Psaumes", "Évangile"],
      answer: "Genèse"
    },
    {
      q: "Qui a construit l’arche ?",
      options: ["Moïse", "Abraham", "Noé", "David"],
      answer: "Noé"
    },
    {
      q: "Combien de jours Dieu a-t-il mis pour créer le monde ?",
      options: ["3", "5", "6", "7"],
      answer: "6"
    }
  ];

  let current = 0, score = 0;

  function loadQuestion() {
    if (current < questions.length) {
      const q = questions[current];
      document.getElementById("question").innerHTML = "<h3>" + q.q + "</h3>";
      let btns = "";
      q.options.forEach(opt => {
        btns += `<button onclick="checkAnswer('${opt}')">${opt}</button><br>`;
      });
      document.getElementById("options").innerHTML = btns;
    } else {
      document.getElementById("question").innerHTML = "<h3>Quiz terminé !</h3>";
      document.getElementById("options").innerHTML = "<p>Score final : " + score + " / " + questions.length + "</p>";
    }
  }

  function checkAnswer(opt) {
    if (opt === questions[current].answer) score++;
    current++;
    document.getElementById("score").innerText = "Score : " + score;
    loadQuestion();
  }

  loadQuestion();
</script>

</body>
</html>
