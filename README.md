<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Portafolio - Andres Poma</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', sans-serif;
  transition: all 0.3s ease;
}

/* MODO OSCURO (default) */
body {
  background: radial-gradient(circle at top, #0a0a0a, #000);
  color: #eee;
  overflow-x: hidden;
}

/* MODO CLARO */
body.light {
  background: #f5f5f5;
  color: #111;
}
/* FIX MODO CLARO TEXTOS */
body.light {
  color: #111;
}

body.light p,
body.light h1,
body.light h2,
body.light h3 {
  color: #111;
}

body.light .card {
  background: #ffffff;
  color: #111;
  border: 1px solid rgba(0,0,0,0.1);
}

body.light .tab {
  background: #e0e0e0;
  color: #111;
}

body.light .tab.active {
  background: red;
  color: white;
}

body.light .bar {
  background: #ccc;
}

body.light .sidebar {
  color: #111;
}

body.light .bio {
  color: #444;
}

body.light .socials a {
  color: red;
}

body.light .socials a:hover {
  color: #000;
}

/* CURSOR GLOW */
.cursor {
  position: fixed;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: red;
  pointer-events: none;
  filter: blur(10px);
  opacity: 0.6;
  z-index: 9999;
}

/* CONTAINER */
.container {
  display: flex;
  min-height: 100vh;
}

/* SIDEBAR */
.sidebar {
  width: 280px;
  background: rgba(15,15,15,0.9);
  backdrop-filter: blur(10px);
  padding: 30px;
  text-align: center;
  border-right: 1px solid rgba(255,0,0,0.3);
  animation: slideIn 1s ease;
}

body.light .sidebar {
  background: #fff;
}

@keyframes slideIn {
  from { transform: translateX(-100%); opacity: 0; }
  to { transform: translateX(0); opacity: 1; }
}

.sidebar img {
  width: 130px;
  border-radius: 50%;
  border: 3px solid #ff0000;
  box-shadow: 0 0 20px #ff0000;
  margin-bottom: 15px;
  animation: float 3s ease-in-out infinite;
}

@keyframes float {
  0%,100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

.role { color: #ff4d4d; margin-bottom: 10px; }

.bio { font-size: 0.9rem; color: #bbb; margin-bottom: 20px; }

/* ICONOS REDES */
.socials {
  display: flex;
  justify-content: center;
  gap: 15px;
}

.socials a {
  font-size: 22px;
  color: #ff4d4d;
}

.socials a:hover {
  transform: scale(1.3);
  color: white;
}

/* BOTON SWITCH */
.toggle {
  margin-top: 20px;
  padding: 8px 15px;
  border: none;
  border-radius: 20px;
  background: red;
  color: white;
  cursor: pointer;
}

/* MAIN */
.content {
  flex: 1;
  padding: 40px;
  animation: fadeIn 1s ease;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

/* TABS */
.tabs { margin-bottom: 30px; }

.tab {
  background: #1a1a1a;
  border: none;
  padding: 10px 20px;
  color: white;
  margin-right: 10px;
  border-radius: 20px;
  cursor: pointer;
}

.tab.active {
  background: #ff0000;
  box-shadow: 0 0 15px #ff0000;
  transform: scale(1.1);
}

/* SECTIONS */
.section { display: none; opacity: 0; }

h3 { font-size: 30px; }
p { font-size: 20px; }

.section.active {
  display: block;
  animation: fadeSection 0.5s forwards;
}

@keyframes fadeSection {
  to { opacity: 1; }
}

/* CARDS */
.card {
  background: linear-gradient(145deg, #111, #1a1a1a);
  padding: 25px;
  border-radius: 15px;
  margin-bottom: 20px;
  border: 1px solid rgba(255,0,0,0.2);
  box-shadow: 0 0 15px rgba(255,0,0,0.2);
}

.card:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow: 0 0 25px rgba(255,0,0,0.6);
}

/* PROYECTOS */
.projects {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px,1fr));
  gap: 20px;
}

/* SKILLS */
.skill { margin: 15px 0; }

.bar {
  background: #222;
  border-radius: 10px;
  overflow: hidden;
}

.bar span {
  display: block;
  height: 10px;
  background: linear-gradient(90deg, red, orange);
  width: 0;
  animation: fillBar 2s forwards;
}

@keyframes fillBar {
  to { width: var(--width); }
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .container { flex-direction: column; }
  .sidebar { width: 100%; }
}
/* LOADER */
#loader {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #000;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 99999;
  flex-direction: column;
}

.loader-content {
  text-align: center;
  color: white;
  animation: fadeIn 1s ease;
}

.loader-title {
  font-size: 28px;
  margin-bottom: 20px;
  letter-spacing: 2px;
  color: red;
  animation: pulse 1.5s infinite;
}

@keyframes pulse {
  0% { opacity: 0.5; }
  50% { opacity: 1; }
  100% { opacity: 0.5; }
}

/* BARRA */
.loader-bar {
  width: 250px;
  height: 8px;
  background: #222;
  border-radius: 10px;
  overflow: hidden;
  margin: 15px auto;
}

.loader-bar span {
  display: block;
  height: 100%;
  width: 0;
  background: linear-gradient(90deg, red, orange);
  animation: loading 2.5s ease forwards;
}

@keyframes loading {
  to { width: 100%; }
}

.loader-text {
  font-size: 14px;
  color: #aaa;
  margin-top: 10px;
}
/* SWITCH REDISEÑADO PRO */
.theme-switch {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 60px;
  height: 30px;
  margin: 25px auto;
}

.theme-switch input {
  display: none;
}

.slider {
  position: absolute;
  cursor: pointer;
  background: #222;
  border-radius: 30px;
  width: 100%;
  height: 100%;
  transition: 0.4s;
  box-shadow: inset 0 0 5px rgba(0,0,0,0.5);
}

/* CIRCULO */
.slider::before {
  content: "🌙";
  position: absolute;
  height: 24px;
  width: 24px;
  left: 3px;
  top: 3px;
  background: #fff;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
  transition: 0.4s;
}

/* ACTIVO */
input:checked + .slider {
  background: linear-gradient(90deg, #ff7b00, #ffd000);
}

input:checked + .slider::before {
  transform: translateX(30px);
  content: "☀️";
}

/* EFECTO HOVER */
.slider:hover {
  box-shadow: 0 0 10px red;
}
.socials a {
  font-size: 24px;
  color: #ff4d4d;
  transition: 0.3s;
}

.socials a:hover {
  color: white;
  transform: scale(1.3) rotate(5deg);
}
/* BOTON PROYECTO PRO */
.btn-proyecto {
  display: inline-block;
  margin-top: 15px;
  padding: 10px 18px;
  background: linear-gradient(90deg, red, orange);
  color: white;
  text-decoration: none;
  border-radius: 25px;
  font-size: 14px;
  font-weight: bold;
  transition: 0.3s;
  box-shadow: 0 0 10px rgba(255,0,0,0.4);
}

/* HOVER */
.btn-proyecto:hover {
  transform: scale(1.1);
  box-shadow: 0 0 20px rgba(255,0,0,0.8);
}

/* CLICK */
.btn-proyecto:active {
  transform: scale(0.95);
}
.proyecto {
  text-align: center;
  padding: 40px;
  max-width: 800px;
  margin: auto;
}

.proyecto h2 {
  font-size: 2rem;
  margin-bottom: 15px;
}

.proyecto p {
  font-size: 1.1rem;
  margin-bottom: 25px;
  color: #555;
}

.media img,
.media iframe {
  width: 100%;
  border-radius: 15px;
  margin-bottom: 25px;
}

/* Botón pro */
.btn-jugar {
  display: inline-block;
  padding: 12px 25px;
  background: #ff4655;
  color: white;
  text-decoration: none;
  border-radius: 10px;
  font-weight: bold;
  transition: 0.3s;
}

.btn-jugar:hover {
  background: #e03b48;
  transform: scale(1.05);
}
.media video {
  width: 100%;
  border-radius: 10px;
}
</style>
</head><link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<body>
    <div id="loader">
  <div class="loader-content">
    <h1 class="loader-title">Cargando...</h1>
    
    <div class="loader-bar">
      <span></span>
    </div>

    <p class="loader-text">Inicializando portafolio</p>
  </div>
</div>

<div class="cursor"></div>

<div class="container">

<aside class="sidebar">
<img src="Snapchat-1943810114_edit_377950236983296.jpg">
<h1>Andres Poma Quispe</h1>
<br>

<p class="role">Estudiante de Desarrollo de Software</p>
<br>

<p class="bio">
Soy una persona apasionada por la tecnología y el desarrollo, siempre en constante aprendizaje. Me gusta crear proyectos funcionales y bien diseñados, combinando programación, bases de datos y creatividad. Disfruto resolver problemas y mejorar cada trabajo para seguir creciendo profesionalmente.
</p>
<br>
<div class="socials">
  <a href="https://www.tiktok.com/@andrespomaquispe97?_r=1&_t=ZS-94mbZoD1xgX" target="_blank">
    <i class="fab fa-tiktok"></i>
  </a>

  <a href="https://youtube.com/@andrespomaquispe6166?si=ZZTUjqzKtn5WrUBv" target="_blank">
    <i class="fab fa-youtube"></i>
  </a>

  <a href="https://www.instagram.com/andrw_pq_422/" target="_blank">
    <i class="fab fa-instagram"></i>
  </a>
</div>
<br>
<label class="theme-switch">
  <input type="checkbox" id="theme-toggle">
  <span class="slider"></span>
</label>
</aside>

<main class="content">

<nav class="tabs">
<button class="tab active" data-seccion="about">Sobre mí</button>
<button class="tab" data-seccion="proyectos">Proyectos</button>
<button class="tab" data-seccion="skills">Skills</button>
</nav>

<section id="about" class="section active">
<div class="card">
<h3>Sobre mí</h3>
<br>
<p>Soy alguien a quien le gusta aprender haciendo. Me meto de lleno en lo que estoy desarrollando, probando, equivocándome y mejorando hasta que todo funcione como debería. Me interesa mucho entender el “por qué” de las cosas, no solo quedarme con lo básico, y eso me ha ayudado a avanzar poco a poco en programación, bases de datos y desarrollo web. Cuando trabajo en un proyecto, no solo me enfoco en que funcione, también me importa que se vea ordenado, claro y bien presentado. Soy de los que ajusta detalles hasta quedar conforme, porque creo que eso marca la diferencia. También me gusta experimentar con nuevas ideas o herramientas para no quedarme en lo mismo. En general, me considero constante y con ganas de seguir creciendo. Todavía estoy en proceso de formación, pero tengo claro que quiero seguir mejorando mis habilidades y construir proyectos cada vez más completos que reflejen todo lo que voy aprendiendo.</p>
</div>
</section>

<section id="proyectos" class="section">
  <div class="projects">

    <div class="card">
  <h3>Proyecto Gaming</h3>
  <br>
  <p>
    Desarrollé un juego en Roblox Studio inspirado en GTA, donde los jugadores pueden moverse libremente por la ciudad, explorar, interactuar con el entorno y enfrentar diferentes desafíos. El juego combina acción y libertad, permitiendo vivir una experiencia dinámica con mecánicas de progreso y elementos de aventura
  </p>
<br>
  <div class="media">
    <video controls autoplay muted loop>
      <source src="Sin título 1-highlight.mp4" type="video/mp4">
      Tu navegador no soporta videos.
    </video>
  </div>
<br>
  <a href="https://www.roblox.com/games/TU_ID" target="_blank" class="btn-jugar">
    Jugar ahora 🎮
  </a>
</div>

    <div class="card">
      <h3>Proyecto 2D</h3>
      <br>
      <p>Hice un juego en Greenfoot llamado “Galaga de Temu”, donde manejo una nave en el espacio y tengo que enfrentar enemigos hasta ganar o perder la partida.</p>
<br>
      <div class="media">
        <img src="Captura de pantalla 2026-03-07 234314.png" alt="Vista del juego">
      </div>

      <a href="https://www.greenfoot.org/scenarios/36136" target="_blank" class="btn-jugar">
        Ver proyecto 🚀
      </a>
    </div>

  </div>
</section>
<section id="skills" class="section">

<h2>Frontend</h2>
<div class="skill"><p>HTML</p><div class="bar"><span style="--width:95%"></span></div></div>
<div class="skill"><p>CSS</p><div class="bar"><span style="--width:90%"></span></div></div>
<div class="skill"><p>JavaScript</p><div class="bar"><span style="--width:85%"></span></div></div>

<h2>Backend</h2>
<div class="skill"><p>Python</p><div class="bar"><span style="--width:80%"></span></div></div>
<div class="skill"><p>PHP</p><div class="bar"><span style="--width:70%"></span></div></div>
<h2>Otros</h2> <div class="skill"><p>Resolucion de Problemas</p><div class="bar"><span style="--width:85%"></span></div>
</div> <div class="skill"><p>Creatividad</p><div class="bar"><span style="--width:75%"></span></div></div>
 <div class="skill"><p>Speed of work</p><div class="bar"><span style="--width:80%"></span></div></div> 
<div class="skill"><p>Gaming</p><div class="bar"><span style="--width:100%"></span></div></div>

</section>

</main>
</div>

<script>

/* TABS */
const tabs = document.querySelectorAll(".tab");
const sections = document.querySelectorAll(".section");

tabs.forEach(tab => {
  tab.addEventListener("click", () => {
    tabs.forEach(t => t.classList.remove("active"));
    sections.forEach(s => s.classList.remove("active"));

    tab.classList.add("active");
    document.getElementById(tab.dataset.seccion).classList.add("active");
  });
});

// BOTON SWITCH (FIX)
const toggle = document.getElementById("theme-toggle");

// GUARDAR PREFERENCIA
if (localStorage.getItem("theme") === "light") {
  document.body.classList.add("light");
  toggle.checked = true;
}

toggle.addEventListener("change", () => {
  if (toggle.checked) {
    document.body.classList.add("light");
    localStorage.setItem("theme", "light");
  } else {
    document.body.classList.remove("light");
    localStorage.setItem("theme", "dark");
  }
});

/* CURSOR GLOW */
const cursor = document.querySelector(".cursor");

document.addEventListener("mousemove", e => {
  cursor.style.top = e.clientY + "px";
  cursor.style.left = e.clientX + "px";
});
/* LOADER CONTROL */
window.addEventListener("load", () => {
  const loader = document.getElementById("loader");

  setTimeout(() => {
    loader.style.opacity = "0";
    loader.style.transition = "opacity 0.5s ease";

    setTimeout(() => {
      loader.style.display = "none";
    }, 500);

  }, 2500); // duración del loader
});
</script>

</body>
</html>
