let inputState = {
  up: false,
  down: false,
  left: false,
  right: false,
  kick: false
};

// Detectar teclas presionadas
document.addEventListener('keydown', function (e) {
  switch (e.key) {
    case 'ArrowUp':
      inputState.up = true;
      break;
    case 'ArrowDown':
      inputState.down = true;
      break;
    case 'ArrowLeft':
      inputState.left = true;
      break;
    case 'ArrowRight':
      inputState.right = true;
      break;
    case ' ':
      inputState.kick = true;
      break;
  }
  updateInput();
});

// Detectar teclas soltadas
document.addEventListener('keyup', function (e) {
  switch (e.key) {
    case 'ArrowUp':
      inputState.up = false;
      break;
    case 'ArrowDown':
      inputState.down = false;
      break;
    case 'ArrowLeft':
      inputState.left = false;
      break;
    case 'ArrowRight':
      inputState.right = false;
      break;
    case ' ':
      inputState.kick = false;
      break;
  }
  updateInput();
});

// Función para enviar al juego los movimientos
function updateInput() {
  let dirX = 0;
  let dirY = 0;
  if (inputState.left) dirX -= 1;
  if (inputState.right) dirX += 1;
  if (inputState.up) dirY -= 1;
  if (inputState.down) dirY += 1;
  
  let angle = Math.atan2(dirY, dirX);
  let magnitude = (dirX !== 0 || dirY !== 0) ? 1 : 0;
  
  let keys = 0;
  if (magnitude > 0) {
    if (inputState.kick) keys = 5; // mover + kick
    else keys = 1; // solo mover
  } else if (inputState.kick) {
    keys = 4; // solo kick
  }

  if (window.room && room.setKeyState) {
    room.setKeyState(keys, true);
  }
}
