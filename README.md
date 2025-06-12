<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>💖 Nosso Tempo Juntos 💖</title>
  <style>
    body {
      background: #ffe6f0;
      font-family: 'Segoe UI', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      margin: 0;
      text-align: center;
      padding: 20px;
    }

    h1 {
      color: #d63384;
    }

    #timer {
      font-size: 1.5rem;
      color: #333;
      margin-top: 20px;
    }

    .photo img {
      max-width: 300px;
      border-radius: 20px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.3);
      margin: 20px 10px;
    }

    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      margin-top: 40px;
    }

    .caption {
      font-size: 0.9rem;
      color: #555;
      margin-top: 5px;
    }
  </style>
</head>
<body>

  <h1>💖 Nosso tempo juntos 💖</h1>
  <div id="timer">Calculando...</div>

  <!-- Primeira foto principal -->
  <div class="photo">
    <img src="https://i.postimg.cc/67tWsr12/ft02-nossaft.jpg" alt="Nossa primeira foto" />
    <div class="caption">Nossa melhor foto 💑</div>
  </div>

  <!-- Galeria de mais fotos -->
  <div class="photo">
    <div>
      <img src="https://i.postimg.cc/zymD7ZCk/Whats-App-Image-2025-06-12-at-13-06-31-2.jpg" alt="Foto 2">
      <div class="caption">Nossa primeira viagem 🌅</div>
    </div>
    <div>
      <img src="https://i.postimg.cc/3y1K3kPL/Whats-App-Image-2025-06-12-at-13-16-11.jpg" alt="Foto 3">
      <div class="caption">Aniversário da Valentina 🎂</div>
    </div>
    <div>
      <img src="https://i.postimg.cc/9rwFyF7M/f01-acad.jpg" alt="Foto 4">
      <div class="caption">A gente na academia 💪 </div>
      <div>
      <img src="https://i.postimg.cc/xXKfFxgV/ft03-desenho.jpg" alt="Foto 4">
      <div class="caption">Nós em desenho 💘</div>
      
    </div>
  </div>

  <script>
    const startDate = new Date("2023-01-01T00:00:00");

    function updateTimer() {
      const now = new Date();
      let years = now.getFullYear() - startDate.getFullYear();
      let months = now.getMonth() - startDate.getMonth();
      let days = now.getDate() - startDate.getDate();
      let hours = now.getHours() - startDate.getHours();
      let minutes = now.getMinutes() - startDate.getMinutes();
      let seconds = now.getSeconds() - startDate.getSeconds();

      if (seconds < 0) { seconds += 60; minutes--; }
      if (minutes < 0) { minutes += 60; hours--; }
      if (hours < 0) { hours += 24; days--; }
      if (days < 0) {
        months--;
        const prevMonth = new Date(now.getFullYear(), now.getMonth(), 0);
        days += prevMonth.getDate();
      }
      if (months < 0) {
        months += 12;
        years--;
      }

      document.getElementById("timer").textContent = 
        `${years} anos, ${months} meses, ${days} dias, ` +
        `${hours} horas, ${minutes} minutos, ${seconds} segundos`;
    }

    setInterval(updateTimer, 1000);
    updateTimer();
  </script>
</body>
</html>
