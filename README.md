<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mairie de Bichancourt – Plateforme citoyenne</title>
  <style>
    :root {
      --bleu-principal: #273c75;
      --bleu-secondaire: #40739e;
      --jaune: #fbc531;
      --gris-clair: #f5f6fa;
      --texte: #2f3640;
    }

    body {
      margin: 0;
      font-family: "Segoe UI", Arial, sans-serif;
      background: var(--gris-clair);
      color: var(--texte);
    }

    header {
      background: white;
      padding: 1rem;
      display: flex;
      align-items: center;
      gap: 1rem;
      border-bottom: 4px solid var(--bleu-principal);
    }

    header img {
      width: 60px;
      height: auto;
    }

    header h1 {
      font-size: 1.2rem;
      margin: 0;
    }

    .hero {
      background: linear-gradient(rgba(39,60,117,0.85), rgba(39,60,117,0.85)),
        url('https://upload.wikimedia.org/wikipedia/commons/6/6e/Bichancourt_%28Aisne%29_%C3%A9glise.jpg');
      background-size: cover;
      background-position: center;
      color: white;
      padding: 2rem 1rem;
      text-align: center;
    }

    .hero h2 {
      margin: 0;
      font-size: 1.4rem;
    }

    nav {
      background: var(--bleu-principal);
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1px;
    }

    .menu-btn {
      background: var(--bleu-principal);
      color: white;
      padding: 1.2rem 0.5rem;
      text-align: center;
      font-size: 0.9rem;
      cursor: pointer;
      transition: background 0.2s ease;
    }

    .menu-btn:hover {
      background: var(--bleu-secondaire);
    }

    section {
      display: none;
      padding: 1rem;
    }

    section.active {
      display: block;
    }

    h3 {
      color: var(--bleu-principal);
      margin-top: 0;
    }

    .card {
      background: white;
      border-radius: 8px;
      padding: 1rem;
      margin-bottom: 1rem;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }

    .sondage-option {
      display: block;
      margin: 0.5rem 0;
      font-size: 0.95rem;
    }

    button.back {
      background: var(--jaune);
      border: none;
      padding: 0.6rem 1.2rem;
      border-radius: 20px;
      cursor: pointer;
      font-weight: bold;
      color: #000;
    }

    footer {
      text-align: center;
      padding: 1rem;
      font-size: 0.8rem;
      color: #666;
    }

    @media (max-width: 600px) {
      nav {
        grid-template-columns: repeat(2, 1fr);
      }
    }
  </style>
</head>
<body>

<header>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6e/Bichancourt_%28Aisne%29_%C3%A9glise.jpg/120px-Bichancourt_%28Aisne%29_%C3%A9glise.jpg" alt="Bichancourt" />
  <h1>Mairie de Bichancourt<br/><small>Plateforme citoyenne</small></h1>
</header>

<div class="hero">
  <h2>Bienvenue sur l'espace citoyen de Bichancourt</h2>
</div>

<nav id="menu">
  <div class="menu-btn" onclick="openSection('sondage')">📊<br/>Sondage</div>
  <div class="menu-btn" onclick="openSection('actualite')">📰<br/>Actualités</div>
  <div class="menu-btn" onclick="openSection('agenda')">📅<br/>Agenda</div>
  <div class="menu-btn" onclick="openSection('benevolat')">🤝<br/>Bénévolat</div>
  <div class="menu-btn" onclick="openSection('idees')">💡<br/>Idées</div>
</nav>

<section id="sondage">
  <h3>Sondage citoyen</h3>
  <div class="card">
    <strong>Que pensez-vous de cette plateforme ?</strong>
    <label class="sondage-option"><input type="radio" name="avis" /> Très bonne</label>
    <label class="sondage-option"><input type="radio" name="avis" /> Bonne</label>
    <label class="sondage-option"><input type="radio" name="avis" /> À améliorer</label>
  </div>
  <button class="back" onclick="goBack()">Retour</button>
</section>

<section id="actualite">
  <h3>Actualités</h3>
  <div class="card">📰 Informations municipales à venir</div>
  <button class="back" onclick="goBack()">Retour</button>
</section>

<section id="agenda">
  <h3>Agenda</h3>
  <div class="card">📅 Événements communaux</div>
  <button class="back" onclick="goBack()">Retour</button>
</section>

<section id="benevolat">
  <h3>Missions bénévolat</h3>
  <div class="card">🤝 Engagement citoyen local</div>
  <button class="back" onclick="goBack()">Retour</button>
</section>

<section id="idees">
  <h3>Boîte à idées</h3>
  <div class="card">💡 Proposez vos idées pour la commune</div>
  <button class="back" onclick="goBack()">Retour</button>
</section>

<footer>
  © Mairie de Bichancourt – Site citoyen accessible par QR code
</footer>

<script>
  function openSection(id) {
    document.getElementById('menu').style.display = 'none';
    document.querySelectorAll('section').forEach(s => s.classList.remove('active'));
    document.getElementById(id).classList.add('active');
  }

  function goBack() {
    document.getElementById('menu').style.display = 'grid';
    document.querySelectorAll('section').forEach(s => s.classList.remove('active'));
  }
</script>

</body>
</html>
