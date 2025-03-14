# website-hasilkan-uang
hasilkan uang
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Super Mario Game</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #87ceeb;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    #game-container {
      position: relative;
    }

    canvas {
      background-color: #87ceeb;
    }
  </style>
</head>
<body>
  <div id="game-container">
    <canvas id="gameCanvas"></canvas>
  </div>
  <script>
    const canvas = document.getElementById('gameCanvas');
    const ctx = canvas.getContext('2d');

    canvas.width = 800;
    canvas.height = 400;

    let mario = {
      x: 50,
      y: 300,
      width: 50,
      height: 70,
      speed: 5,
      dx: 0,
      dy: 0,
    };

    const gravity = 0.5;
    let isJumping = false;

    function drawMario() {
      ctx.fillStyle = 'red';
      ctx.fillRect(mario.x, mario.y, mario.width, mario.height);
    }

    function updateMario() {
      mario.x += mario.dx;
      mario.y += mario.dy;

      if (mario.y + mario.height < canvas.height) {
        mario.dy += gravity;
      } else {
        mario.dy = 0;
        mario.y = canvas.height - mario.height;
        isJumping = false;
      }
    }

    function moveRight() {
      mario.dx = mario.speed;
    }

    function moveLeft() {
      mario.dx = -mario.speed;
    }

    function jump() {
      if (!isJumping) {
        mario.dy = -10;
        isJumping = true;
      }
    }

    function stopMoving() {
      mario.dx = 0;
    }

    function clear() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
    }

    function update() {
      clear();
      drawMario();
      updateMario();
      requestAnimationFrame(update);
    }

    document.addEventListener('keydown', (e) => {
      if (e.key === 'ArrowRight') moveRight();
      if (e.key === 'ArrowLeft') moveLeft();
      if (e.key === ' ' || e.key === 'ArrowUp') jump();
    });

    document.addEventListener('keyup', (e) => {
      if (e.key === 'ArrowRight' || e.key === 'ArrowLeft') stopMoving();
    });

    update();
  </script>
</body>
</html>
