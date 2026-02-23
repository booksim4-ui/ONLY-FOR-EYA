<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Aya 🎉</title>
<style>
body {
  margin: 0;
  padding: 0;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #ff4da6, #ff1a75);
  font-family: Arial, sans-serif;
  overflow: hidden;
}

h1 {
  font-size: 60px;
  color: white;
  text-align: center;
  letter-spacing: 3px;
  text-shadow: 
    0 0 10px rgba(255,255,255,0.8),
    0 0 20px rgba(255,255,255,0.6),
    0 0 40px rgba(255,255,255,0.4);
  animation: pulse 1s ease-in-out infinite alternate;
}

@keyframes pulse {
  0% {
    transform: scale(1);
    text-shadow: 0 0 10px rgba(255,255,255,0.6), 0 0 20px rgba(255,255,255,0.4);
  }
  50% {
    transform: scale(1.2);
    text-shadow: 0 0 20px rgba(255,255,255,1), 0 0 40px rgba(255,255,255,0.8);
  }
  100% {
    transform: scale(1);
    text-shadow: 0 0 10px rgba(255,255,255,0.6), 0 0 20px rgba(255,255,255,0.4);
  }
}

.floating {
  position: fixed;
  font-size: 20px;
  pointer-events: none;
  user-select: none;
  z-index: 999;
  transition: transform 0.5s ease, opacity 0.5s ease;
  opacity: 1;
}
</style>
</head>
<body>

<h1 id="mainMsg">🎉 HAPPY BIRTHDAY AYA 🎉</h1>

<script>
const mainMsg = document.getElementById("mainMsg");
const floatingItems = ['💖','✨','🌟','💫','🌹'];

function createFloating() {
  const elem = document.createElement('div');
  elem.classList.add('floating');
  elem.innerHTML = floatingItems[Math.floor(Math.random() * floatingItems.length)];
  elem.style.left = Math.random() * window.innerWidth + 'px';
  elem.style.top = Math.random() * window.innerHeight + 'px';
  elem.style.fontSize = (Math.random()*20+20) + 'px';
  document.body.appendChild(elem);

  setTimeout(() => {
    elem.style.transform = `translateY(-50px) scale(1.5)`;
    elem.style.opacity = '0';
  }, 50);

  setTimeout(() => elem.remove(), 1000);
}

// كل مرة الكتابة تكبر، نطلق floating
mainMsg.addEventListener('animationiteration', () => {
  for(let i=0;i<5;i++){
    createFloating();
  }
});
</script>

</body>
</html>
