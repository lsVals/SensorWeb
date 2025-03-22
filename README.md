<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Iniciar Sesión</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #1e3c72, #2a5298);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .login-container {
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            text-align: center;
            width: 300px;
            backdrop-filter: blur(10px);
        }

        h2 {
            color: white;
            margin-bottom: 20px;
        }

        input {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: none;
            border-radius: 5px;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            outline: none;
        }

        input::placeholder {
            color: rgba(255, 255, 255, 0.7);
        }

        button {
            width: 100%;
            padding: 10px;
            border: none;
            border-radius: 5px;
            background: #00c6ff;
            color: white;
            font-size: 16px;
            cursor: pointer;
            transition: 0.3s;
        }

        button:hover {
            background: #0072ff;
        }

        .error {
            color: #ff4b4b;
            font-size: 14px;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="login-container">
        <h2>Iniciar Sesión</h2>
        <input type="text" id="user" placeholder="Usuario">
        <input type="password" id="pass" placeholder="Contraseña">
        <button onclick="login()">Ingresar</button>
        <p class="error" id="error-message"></p>
    </div>

    <script>
        const THINGSPEAK_URL = "https://thingspeak.com/channels/3NG7LS0F3MQQET0W"; // 🔹 Cambia esto con tu enlace de ThingSpeak
        const USERNAME = "admin"; // 🔹 Cambia esto por el usuario que quieras
        const PASSWORD = "1234";  // 🔹 Cambia esto por la contraseña que quieras

        function login() {
            const user = document.getElementById("user").value;
            const pass = document.getElementById("pass").value;
            const errorMessage = document.getElementById("error-message");

            if (user === USERNAME && pass === PASSWORD) {
                window.location.href = THINGSPEAK_URL; // 🔹 Redirige a ThingSpeak si los datos son correctos
            } else {
                errorMessage.textContent = "Usuario o contraseña incorrectos";
            }
        }
    </script>
</body>
</html>
