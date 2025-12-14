const tg = window.Telegram.WebApp;
tg.ready();

const boostBtn = document.getElementById('boostBtn');
const statusText = document.getElementById('status');

boostBtn.addEventListener('click', () => {
  statusText.textContent = 'Boost started 🚀';

  tg.HapticFeedback.impactOccurred('medium');

  tg.sendData(JSON.stringify({
    action: 'start_boost',
    timestamp: Date.now()
  }));
});
