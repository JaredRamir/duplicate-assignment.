<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Duplicate Assignment - Jared Ramirez</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="container">
    <aside class="sidebar">
      <h2>Jared Ramirez</h2>
      <p>This is my Duplicate Assignment</p>
    </aside>

    <main class="main-content">
      <section class="links">
        <h1>Animated Links Section</h1>
        <a href="https://www.openai.com" target="_blank" class="animated-link">Visit OpenAI</a>
        <a href="https://developer.mozilla.org" target="_blank" class="animated-link">Visit MDN</a>
      </section>

      <section class="canvas-section">
        <h2>Canvas Animation</h2>
        <canvas id="myCanvas" width="400" height="200"></canvas>
      </section>
    </main>
  </div>
  <script src="script.js"></script>
</body>
</html>


const canvas = document.getElementById('myCanvas');
const ctx = canvas.getContext('2d');

let x = 50;
let y = 100;
let dx = 3;

function draw() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  ctx.beginPath();
  ctx.arc(x, y, 20, 0, Math.PI * 2);
  ctx.fillStyle = "#0077ff";
  ctx.fill();
  ctx.closePath();

  x += dx;
  if (x > canvas.width - 20 || x < 20) {
    dx = -dx;
  }

  requestAnimationFrame(draw);
}
draw();




body {
  font-family: "Poppins", sans-serif;
  margin: 0;
  background-color: #f4f4f9;
  color: #333;
}

.container {
  display: flex;
  flex-wrap: wrap;
  min-height: 100vh;
}

.sidebar {
  flex: 1 1 25%;
  background-color: #222;
  color: white;
  padding: 2rem;
}

.main-content {
  flex: 1 1 75%;
  padding: 2rem;
  background-color: #fff;
}

/* Animated Links */
.animated-link {
  display: inline-block;
  margin: 1rem;
  padding: 0.5rem 1rem;
  text-decoration: none;
  color: #fff;
  background: #0077ff;
  border-radius: 8px;
  transition: transform 0.3s ease, background 0.3s ease;
}

.animated-link:hover {
  transform: scale(1.1);
  background: #0055aa;
}

/* Canvas Section */
.canvas-section {
  margin-top: 2rem;
}

/* Responsive */
@media (max-width: 800px) {
  .container {
    flex-direction: column;
  }
}
