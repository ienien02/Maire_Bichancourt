<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Plateforme Citoyenne</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      background: #f5f6fa;
      color: #333;
    }
    header {
      background: #2c3e50;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    nav {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1rem;
      padding: 1rem;
    }
    .menu-btn {
      background: white;
      border-radius: 10px;
      padding: 1.5rem 1rem;
      text-align: center;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
      cursor: pointer;
      transition: transform 0.1s ease, box-shadow 0.1s ease;
    }
    .menu-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    }
    .menu-btn h2 {
      margin: 0;
      font-size: 1.1rem;
    }
    section {
      display: none;
      padding: 1rem;
    }
    section.active {
      display: block;
    }
    button.back {
      margin-top: 1rem;
      background: #2c3e50;
      color: white;
      border: none;
      padding: 0.6rem 1rem;
      border-radius: 6px;
      cursor: pointer;
    }
    .card {
      background: white;
      padding: 1rem;
      border-radius: 8px;
      margin-bottom: 1rem;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }
  </style>
</head>
<body>

  <header>
    <h1>Plateforme participative</h1>
    <p>Accessible via QR code</p>
  </header>

  <!-- MENU PRINCIPAL -->
  <nav id="menu">
    <div class="menu-btn" onclick="openSection('sondage')">
      <h2>📊 Sondage</h2>
    </div>
    <div class="menu-btn" onclick="openSection('actualite')">
      <h2>📰 Actualité</h2>
    </div>
    <div class="menu-btn" onclick="openSection('agenda')">
      <h2>📅 Agenda</h2>
    </div>
    <div class="menu-btn" onclick="openSection('benevolat')">
      <h2>🤝 Missions bénévolat</h2>
    </div>
    <div class="menu-btn" onclick="openSection('idees')">
      <h2>💡 Idées</h2>
    </div>
  </nav>

  <!-- SECTIONS -->
  <section id="sondage">
    <h2>Sondage</h2>
    <div class="card">Question du moment :<br/><strong>Que pensez-vous de ce projet ?</strong></div>
    <div class="card">⬜ Très bon<br/>⬜ Bon<br/>⬜ À améliorer</div>
    <button class="back" onclick="goBack()">Retour au menu</button>
  </section>

  <section id="actualite">
    <h2>Actualité</h2>
    <div class="card">📰 Publication 1 – Brève information</div>
    <div class="card">📰 Publication 2 – Mise à jour importante</div>
    <button class="back" onclick="goBack()">Retour au menu</button>
  </section>

  <section id="agenda">
    <h2>Agenda</h2>
    <div class="card">📅 15 juin – Réunion publique</div>
    <div class="card">📅 30 juin – Événement associatif</div>
    <button class="back" onclick="goBack()">Retour au menu</button>
  </section>

  <section id="benevolat">
    <h2>Missions bénévolat</h2>
    <div class="card">🤝 Aide événementielle – 1 journée</div>
    <div class="card">🤝 Distribution de flyers – 2h</div>
    <button class="back" onclick="goBack()">Retour au menu</button>
  </section>

  <section id="idees">
    <h2>Boîte à idées</h2>
    <div class="card">💡 Proposez vos idées pour améliorer le projet</div>
    <div class="card">(Formulaire à intégrer)</div>
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
