<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mairie de Bichancourt – Plateforme citoyenne</title>
  <style>
    body {
      margin: 0;
      font-family: "Segoe UI", Arial, sans-serif;
      color: #ffffff;
      min-height: 100vh;
      background: linear-gradient(rgba(0,0,0,0.55), rgba(0,0,0,0.55)),
                  url('https://upload.wikimedia.org/wikipedia/commons/6/6e/Bichancourt_%28Aisne%29_%C3%A9glise.jpg');
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
    }

    header {
      background: rgba(44, 62, 80, 0.85);
      padding: 1.2rem;
      text-align: center;
    }

    header h1 {
      margin: 0;
      font-size: 1.6rem;
    }

    header p {
      margin: 0.3rem 0 0;
      font-size: 0.9rem;
      opacity: 0.9;
    }

    nav {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1rem;
      padding: 1rem;
    }

    .menu-btn {
      background: rgba(255, 255, 255, 0.9);
      color: #2c3e50;
      border-radius: 14px;
      padding: 1.8rem 1rem;
      text-align: center;
      box-shadow: 0 6px 15px rgba(0,0,0,0.25);
      cursor: pointer;
      transition: transform 0.15s ease, box-shadow 0.15s ease, background 0.15s ease;
      font-weight: 600;
    }

    .menu-btn:hover {
      transform: translateY(-4px);
      box-shadow: 0 10px 22px rgba(0,0,0,0.35);
      background: #ecf0f1;
    }

    section {
      display: none;
      padding: 1rem;
    }

    section.active {
      display: block;
    }

    h2 {
      margin-top: 0;
      color: #f1c40f;
    }

    .card {
      background: rgba(0, 0, 0, 0.65);
      padding: 1rem;
      border-radius: 12px;
      margin-bottom: 1rem;
      box-shadow: 0 4px 12px rgba(0,0,0,0.4);
    }

    .sondage-option {
      display: block;
      margin: 0.6rem 0;
      cursor: pointer;
    }

    .sondage-option input {
      margin-right: 0.6rem;
      transform: scale(1.2);
    }

    button.back {
      margin-top: 1rem;
      background: #f1c40f;
      color: #2c3e50;
      border: none;
      padding: 0.7rem 1.2rem;
      border-radius: 8px;
      cursor: pointer;
      font-weight: bold;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
    }

    button.back:hover {
      background: #f39c12;
    }
  </style>
</head>
<body>

  <header>
    <h1>Mairie de Bichancourt</h1>
    <p>Plateforme citoyenne – accès par QR code</p>
  </header>

  <!-- MENU PRINCIPAL -->
  <nav id="menu">
    <div class="menu-btn" onclick="openSection('sondage')">📊<br/>Sondage</div>
    <div class="menu-btn" onclick="openSection('actualite')">📰<br/>Actualité</div>
    <div class="menu-btn" onclick="openSection('agenda')">📅<br/>Agenda</div>
    <div class="menu-btn" onclick="openSection('benevolat')">🤝<br/>Bénévolat</div>
    <div class="menu-btn" onclick="openSection('idees')">💡<br/>Idées</div>
  </nav>

  <!-- SECTIONS -->
  <section id="sondage">
    <h2>Sondage citoyen</h2>
    <div class="card">
      <strong>Que pensez-vous de cette plateforme ?</strong>
      <label class="sondage-option"><input type="radio" name="avis" /> Très bonne</label>
      <label class="sondage-option"><input type="radio" name="avis" /> Bonne</label>
      <label class="sondage-option"><input type="radio" name="avis" /> À améliorer</label>
    </div>
    <button class="back" onclick="goBack()">Retour au menu</button>
  </section>

  <section id="actualite">
    <h2>Actualités</h2>
    <div class="card">📰 Informations municipales à venir</div>
    <button class="back" onclick="goBack()">Retour au menu</button>
  </section>

  <section id="agenda">
    <h2>Agenda communal</h2>
    <div class="card">📅 Événements de la commune</div>
    <button class="back" onclick="goBack()">Retour au menu</button>
  </section>

  <section id="benevolat">
    <h2>Missions bénévolat</h2>
    <div class="card">🤝 Missions locales à proposer</div>
    <button class="back" onclick="goBack()">Retour au menu</button>
  </section>

  <section id="idees">
    <h2>Boîte à idées</h2>
    <div class="card">💡 Vos idées pour Bichancourt</div>
    <button class="back" onclick="goBack()">Retour au menu</button>
  </section>

  <script>
    function openSection(id) {
      document.getElementById('menu').style.display = 'none';
      document.querySelectorAll('section').forEach(sec => sec.classList.remove('active'));
      document.getElementById(id).classList.add('active');
    }

    function goBack() {
      document.getElementById('menu').style.display = 'grid';
      document.querySelectorAll('section').forEach(sec => sec.classList.remove('active'));
    }
  </script>

</body>
</html>
