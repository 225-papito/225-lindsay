<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Mon ciel étoilé</title>
  <style>
    /* Tout le body prend tout l'écran et est noir */
    body {
      margin: 0;
      padding: 0;
      overflow: hidden;
      background-color: black;
      color: white;
      font-family: Arial, sans-serif;
    }

    /* Les étoiles */
    .star {
      position: absolute;
      width: 2px;
      height: 2px;
      background: white;
      border-radius: 50%;
      opacity: 0.8;
      animation: twinkle 2s infinite alternate;
    }

    /* Animation pour faire clignoter les étoiles */
    @keyframes twinkle {
      from { opacity: 0.3; }
      to { opacity: 1; }
    }

    /* Texte au centre */
    h1 {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
      font-size: 2em;
    }
  </style>
</head>
<body>
  <h1>Bienvenue dans mon ciel étoilé 🌌</h1>

  <script>
    // Nombre d'étoiles
    const starCount = 200;

    for(let i = 0; i < starCount; i++) {
      const star = document.createElement('div');
      star.className = 'star';
      star.style.top = Math.random() * window.innerHeight + 'px';
      star.style.left = Math.random() * window.innerWidth + 'px';
      star.style.width = Math.random() * 3 + 1 + 'px';
      star.style.height = star.style.width;
      star.style.animationDuration = 1 + Math.random() * 2 + 's';
      document.body.appendChild(star);
    }

    // Pour que les étoiles restent bien quand on redimensionne
    window.addEventListener('resize', () => {
      document.querySelectorAll('.star').forEach(star => {
        star.style.top = Math.random() * window.innerHeight + 'px';
        star.style.left = Math.random() * window.innerWidth + 'px';
      });
    });
  </script>
</body>
</html>
