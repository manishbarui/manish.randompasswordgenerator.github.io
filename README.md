<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Use Strong Password Dialog</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #000;
      margin: 0;
      font-family: Arial, sans-serif;
    }

    .dialog {
      background-color: #1c1c1e;
      border-radius: 20px;
      padding: 30px;
      width: 300px;
      text-align: center;
      color: #fff;
    }

    .dialog img {
      width: 30px;
      margin-bottom: 15px;
    }

    .dialog h2 {
      font-size: 20px;
      margin: 0;
      font-weight: normal;
    }

    .dialog p {
      font-size: 14px;
      color: #a1a1a1;
      margin: 10px 0 20px;
    }

    .password-display {
      background-color: #2c2c2e;
      padding: 10px;
      border-radius: 10px;
      font-size: 18px;
      letter-spacing: 1px;
      font-weight: bold;
      color: #fff;
      margin-bottom: 20px;
    }

    .button-group {
      display: flex;
      gap: 10px;
      margin-top: 10px;
    }

    .button-group button {
      flex: 1;
      padding: 10px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      font-size: 16px;
      color: #fff;
      transition: background-color 0.3s;
    }

    .use-password-btn {
      background-color: #4e72f9;
    }

    .use-password-btn:hover {
      background-color: #365bb0;
    }

    .generate-password-btn {
      background-color: #3a3a3c;
    }

    .generate-password-btn:hover {
      background-color: #2a2a2c;
    }
  </style>
</head>
<body>

  <div class="dialog">
    <img src="https://assets.onecompiler.app/42uh2pufm/42xa2um5k/IMG_20241106_082916.png" alt="Moogle Icon">
    <h2>Use strong password?</h2>
    <p>You won’t need to manually create your password. This is an alternative to Google Password Manager for <strong>example@gmail.com</strong>.</p>
    <div class="password-display" id="passwordDisplay">Manish_Barui</div>
    <div class="button-group">
      <button class="generate-password-btn" onclick="generatePassword()">Generate Password</button>
      <button class="use-password-btn" onclick="usePassword()">Use Password</button>
    </div>
  </div>

  <script>
    // Function to simulate using the password
    function usePassword() {
      const password = document.getElementById('passwordDisplay').textContent;
      navigator.clipboard.writeText(password).then(() => {
        alert('Password copied to clipboard!');
      }).catch(err => {
        console.error('Could not copy password: ', err);
      });
    }

    // Function to generate a random strong password
    function generatePassword() {
      const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz1234567890!@#$%^&*()_+-=[]{}|;:,.<>?';
      let password = "";
      for (let i = 0; i < 15; i++) {
        password += characters.charAt(Math.floor(Math.random() * characters.length));
      }
      document.getElementById('passwordDisplay').textContent = password;
    }

    // Generate a password when the page loads
    window.onload = generatePassword;
  </script>

</body>
</html>
