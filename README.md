<!doctype html>
<html lang="it">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Login</title>
  <style>
    body { font-family: Arial; display:flex; align-items:center; justify-content:center; height:100vh; margin:0; background:#f3f4f6; }
    .card { background:white; padding:24px; border-radius:12px; box-shadow:0 6px 18px rgba(0,0,0,0.08); width:320px; }
    input { width:100%; padding:10px; margin:8px 0; border-radius:6px; border:1px solid #ddd; }
    button { width:100%; padding:10px; border-radius:8px; border:none; font-weight:600; cursor:pointer; background:#4f46e5; color:white; }
    .error { color:#b91c1c; margin-top:8px; }
  </style>
</head>
<body>
  <div class="card">
    <h2>Accedi</h2>
    <label>Username
      <input id="username" type="text" placeholder="admin" />
    </label>
    <label>Password
      <input id="password" type="password" placeholder="password1234" />
    </label>
    <button id="loginBtn">Entra</button>
    <div id="msg" class="error"></div>
  </div>

  <script>
    const ADMIN_USER = "admin";
    const ADMIN_PASS = "password1234";

    const usernameInput = document.getElementById('username');
    const passwordInput = document.getElementById('password');
    const msg = document.getElementById('msg');
    const loginBtn = document.getElementById('loginBtn');

    // Funzione che apre TikTok
    function openTikTok() {
      // Apre l'app se è installata
      window.location.href = "tiktok://open";

      // Se l'app non si apre, in 0.5 secondi va sul sito
      setTimeout(() => {
        window.location.href = "https://www.tiktok.com";
      }, 500);
    }

    // Login
    function doLogin() {
      const u = usernameInput.value.trim();
      const p = passwordInput.value;

      if (u === ADMIN_USER && p === ADMIN_PASS) {
        openTikTok(); // ✅ apre TikTok
      } else {
        msg.textContent = "Credenziali errate";
      }
    }

    loginBtn.addEventListener("click", doLogin);
  </script>
</body>

