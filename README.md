!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>San Valentín 💖</title>

<style>
body {
  font-family: Arial, sans-serif;
  background:
    linear-gradient(rgba(0,0,0,0.35), rgba(0,0,0,0.35)),
    url("fondo.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  text-align: center;
  overflow: hidden;
}

.card {
  background: rgba(255, 255, 255, 0.9);
  padding: 40px;
  border-radius: 20px;
  box-shadow: 0 10px 25px rgba(0,0,0,0.3);
  z-index: 2;
}

button {
  font-size: 20px;
  margin: 15px;
  padding: 15px 30px;
  border: none;
  border-radius: 15px;
  cursor: pointer;
}

.yes {
  background: #ff4d6d;
  color: white;
}

.no {
  background: #adb5bd;
  color: white;
}

.roses {
  font-size: 60px;
  margin-top: 20px;
}

/* Corazones */
.heart {
  position: fixed;
  top: -10px;
  font-size: 24px;
  animation: fall linear forwards;
  z-index: 1;
}

@keyframes fall {
  to {
    transform: translateY(110vh);
    opacity: 0;
  }
}
</style>
</head>

<body>
<div class="card" id="content">
  <h1>💖 ¿Quieres ser mi San Valentín, mi princesa? 💖</h1>
  <button class="yes" onclick="yes()">💘 SÍ 💘</button>
  <button class="no" onclick="no()">🙈 NO 🙈</button>
</div>

<script>
function yes() {
  document.getElementById("content").innerHTML = `
    <h1>🥰 Sabía que ibas a decir que sí 🥰</h1>
    <h2>💖 Feliz San Valentín, mi princesa 💖</h2>
    <div class="roses">🌹💐🌹</div>
  `;
  startHearts();
}

function no() {
  document.getElementById("content").innerHTML = `
    <h1>😢 Oh nooo…</h1>
    <h2>💌 Gracias por abrirlo</h2>
  `;
}

function startHearts() {
  setInterval(() => {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "💖";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (2 + Math.random() * 3) + "s";
    document.body.appendChild(heart);

    setTimeout(() => {
      heart.remove();
    }, 5000);
  }, 300);
}
</script>
</body>
</html>
