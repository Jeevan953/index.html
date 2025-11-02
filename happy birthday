<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Happy Birthday!</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Quicksand:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Quicksand', sans-serif;
      background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
      overflow-x: hidden;
    }
    .birthday-card {
      background: white;
      border-radius: 20px;
      box-shadow: 0 15px 30px rgba(0,0,0,0.1);
      overflow: hidden;
      max-width: 600px;
      width: 100%;
      position: relative;
    }
    .card-header {
      background: linear-gradient(45deg, #ff6b6b, #ff8e8e);
      color: white;
      padding: 30px 20px;
      text-align: center;
    }
    .card-header h1 {
      font-family: 'Pacifico', cursive;
      font-size: 2.8rem;
      margin-bottom: 10px;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
    }
    .card-body { padding: 30px; text-align: center; }
    .birthday-message { font-size: 1.2rem; line-height: 1.6; margin-bottom: 25px; color: #555; }
    .balloons { display:flex; justify-content:center; gap:15px; margin:20px 0; }
    .balloon { width:50px; height:60px; border-radius:50%; position:relative; animation:float 3s ease-in-out infinite; }
    .balloon:before { content:""; position:absolute; bottom:-10px; left:50%; transform:translateX(-50%); width:2px; height:30px; background:rgba(0,0,0,0.2); }
    .balloon:nth-child(1){ background:#ff6b6b; animation-delay:0s }
    .balloon:nth-child(2){ background:#4ecdc4; animation-delay:0.5s }
    .balloon:nth-child(3){ background:#ffd166; animation-delay:1s }
    .balloon:nth-child(4){ background:#06d6a0; animation-delay:1.5s }
    .balloon:nth-child(5){ background:#118ab2; animation-delay:2s }
    @keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-15px)} }

    .cake { margin:20px auto; width:120px; height:60px; background:#f8c291; border-radius:10px 10px 0 0; position:relative; }
    .cake:before { content:""; position:absolute; top:-20px; left:10px; width:100px; height:20px; background:#e55039; border-radius:10px; }
    .candle { position:absolute; top:-40px; left:50%; transform:translateX(-50%); width:8px; height:25px; background:#fff; border-radius:4px; }
    .flame { position:absolute; top:-15px; left:50%; transform:translateX(-50%); width:12px; height:15px; background:#ff9f43; border-radius:50% 50% 20% 20%; animation:flicker 1.5s infinite alternate; }
    @keyframes flicker { 0%,100%{opacity:1; transform:translateX(-50%) scale(1)} 50%{opacity:0.8; transform:translateX(-50%) scale(0.95)} }

    .btn-birthday { background:linear-gradient(45deg,#ff6b6b,#ff8e8e); border:none; color:white; padding:12px 30px; border-radius:50px; font-weight:600; font-size:1.1rem; transition:all .3s; box-shadow:0 5px 15px rgba(255,107,107,0.4); }
    .btn-birthday:hover { transform:translateY(-3px); box-shadow:0 8px 20px rgba(255,107,107,0.6); }

    /* Confetti container should sit above the page */
    #confetti-container {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 9999;
      overflow: hidden;
    }

    /* Confetti piece visible by default (no hidden opacity) */
    .confetti-piece {
      position: absolute;
      width: 10px;
      height: 14px;
      opacity: 1;
      will-change: transform, opacity;
      border-radius: 2px;
    }

    /* animation: fall, with horizontal drift built-in using translateX */
    @keyframes confetti-fall {
      0% {
        transform: translateY(-30vh) translateX(0) rotate(0deg);
        opacity: 1;
      }
      30% {
        opacity: 1;
      }
      100% {
        transform: translateY(110vh) translateX(var(--drift)) rotate(720deg);
        opacity: 0;
      }
    }

    /* Toast notification */
    .toast-container {
      position: fixed;
      top: 20px;
      right: 20px;
      z-index: 10000; /* keep below confetti */
    }
    .custom-toast {
      background: linear-gradient(45deg, #fc5c7d, #6a82fb);
      color: white;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    }

    .card-footer { padding:20px; text-align:center; background:#f8f9fa; border-top:1px solid #eee; }
    .signature { font-family:'Pacifico', cursive; font-size:1.3rem; color:#ff6b6b; }
  </style>
</head>
<body>
  <div class="birthday-card">
    <div class="card-header">
      <h1>Happy Birthday!</h1>
      <p class="mb-0">Wishing you a day filled with happiness and a year filled with joy!</p>
    </div>

    <div class="card-body">
      <div class="balloons">
        <div class="balloon"></div>
        <div class="balloon"></div>
        <div class="balloon"></div>
        <div class="balloon"></div>
        <div class="balloon"></div>
      </div>

      <div class="cake">
        <div class="candle"><div class="flame"></div></div>
      </div>

      <p class="birthday-message">
        On your special day, I wish you success and endless joy.
        Thank you for being such a great friend. May this birthday be
        the beginning of a year filled with good luck, health, and happiness.
      </p>

      <button class="btn btn-birthday" id="celebrateBtn">
        <i class="fas fa-birthday-cake me-2"></i> Celebrate!
      </button>
    </div>

    <div class="card-footer">
      <p class="mb-0">With lots of love,</p>
      <p class="signature">Your Friend</p>
    </div>
  </div>

  <!-- Confetti container -->
  <div id="confetti-container"></div>

  <!-- Toast notification -->
  <div class="toast-container">
    <div id="birthdayToast" class="toast custom-toast" role="alert" aria-live="assertive" aria-atomic="true" data-bs-delay="4000">
      <div class="toast-header">
        <strong class="me-auto"><i class="fas fa-birthday-cake me-2"></i>Happy Birthday!</strong>
        <button type="button" class="btn-close btn-close-white" data-bs-dismiss="toast" aria-label="Close"></button>
      </div>
      <div class="toast-body">Wishing you a fantastic day filled with joy and celebration!</div>
    </div>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
  <script>
    document.addEventListener('DOMContentLoaded', () => {
      const celebrateBtn = document.getElementById('celebrateBtn');
      const confettiContainer = document.getElementById('confetti-container');
      const birthdayToastEl = document.getElementById('birthdayToast');
      const birthdayToast = new bootstrap.Toast(birthdayToastEl);

      celebrateBtn.addEventListener('click', () => {
        createConfettiBurst();
        birthdayToast.show();
        speak();
      });

      function createConfettiBurst() {
        // remove old pieces
        confettiContainer.innerHTML = '';

        // create many pieces
        const count = 100;
        const colors = ['#ff6b6b', '#4ecdc4', '#ffd166', '#06d6a0', '#118ab2', '#ff9f43'];

        for (let i = 0; i < count; i++) {
          const piece = document.createElement('div');
          piece.className = 'confetti-piece';

          // size
          const w = Math.floor(Math.random() * 10) + 6;
          piece.style.width = w + 'px';
          piece.style.height = Math.floor(w * 1.3) + 'px';

          // color
          piece.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];

          // start position: random X across viewport, Y slightly above top so it falls into view
          const startX = Math.random() * 100; // percent
          piece.style.left = startX + 'vw';
          piece.style.top = (Math.random() * -20) - 10 + 'vh'; // -10vh .. -30vh

          // horizontal drift: random small value (-30vw .. +30vw)
          const drift = (Math.random() * 60 - 30) + 'vw';
          piece.style.setProperty('--drift', drift);

          // random delay and duration
          const duration = Math.floor(Math.random() * 2500) + 4000; // 4s..6.5s
          const delay = Math.floor(Math.random() * 400); // 0..400ms

          // apply animation (single-run, forwards so it disappears at end)
          piece.style.animation = `confetti-fall ${duration}ms cubic-bezier(.18,.84,.44,1) ${delay}ms forwards`;

          // small rotation offset
          piece.style.transform = `rotate(${Math.floor(Math.random() * 360)}deg)`;

          // z-index to appear above most UI
          piece.style.zIndex = 9999;

          confettiContainer.appendChild(piece);

          // cleanup after animation + small buffer
          setTimeout(() => {
            if (piece && piece.parentElement) piece.remove();
          }, duration + delay + 500);
        }
      }

      function speak() {
        if ('speechSynthesis' in window) {
          const msg = new SpeechSynthesisUtterance('Happy birthday to you!');
          msg.rate = 0.95;
          window.speechSynthesis.cancel();
          window.speechSynthesis.speak(msg);
        } else {
          console.log('Speech not supported');
        }
      }
    });
  </script>
</body>
</html>
