<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Jeferson ❤️ Ieda </title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="manifest" href="manifest.json">
    <meta name="theme-color" content="#121212">
    <link rel="apple-touch-icon" href="icon-192.png">
    <style>
        body {
            background-color: #121212;
            color: #fff;
            font-family: 'Arial', sans-serif;
            text-align: center;
            padding: 20px;
            transition: background-color 0.5s ease, color 0.5s ease;
        }
        h1 {
            font-size: 2em;
            margin-bottom: 10px;
            transition: all 0.3s ease-in-out;
        }
        .frase {
            font-size: 1.2em;
            margin-bottom: 20px;
            transition: all 0.3s ease-in-out;
        }
        img {
            width: 100%;
            max-width: 300px;
            border-radius: 20px;
            margin-bottom: 20px;
            transition: all 0.5s ease-in-out;
        }
        .contador {
            font-size: 1.5em;
            margin-top: 20px;
            transition: all 0.3s ease-in-out;
        }
        .heart {
            font-size: 3em;
            color: red;
            animation: pulse 1s infinite;
            transition: transform 0.3s ease-in-out;
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.2); }
            100% { transform: scale(1); }
        }
    </style>
    <script>
        if ('serviceWorker' in navigator) {
            navigator.serviceWorker.register('service-worker.js')
                .then(reg => console.log("Service Worker registrado."))
                .catch(err => console.error("Erro ao registrar o Service Worker:", err));
        }
    </script>
</head>
<body>
    <h1>Jeferson & Ieda </h1>
    <img src="foto_casal.jpg" alt="Casal">
    <div class="frase">ESTAREI COM VOCÊ PARA SEMPRE! ❤️</div>
    <div class="heart">❤️</div>
    <div class="contador" id="contador"></div>

    <script>
        const inicio = new Date("2025-03-25T00:00:00");

        function formatarNumero(num) {
            return num.toString().padStart(2, '0');
        }

        function atualizarContador() {
            const agora = new Date();
            const diff = agora - inicio;
            const dias = Math.floor(diff / (1000 * 60 * 60 * 24));
            const horas = Math.floor((diff / (1000 * 60 * 60)) % 24);
            const minutos = Math.floor((diff / (1000 * 60)) % 60);
            const segundos = Math.floor((diff / 1000) % 60);

            document.getElementById("contador").textContent =
                `Juntos há ${dias} dias, ${formatarNumero(horas)}h ${formatarNumero(minutos)}min ${formatarNumero(segundos)}s`;
        }

        setInterval(atualizarContador, 1000);
        atualizarContador();
    </script>
</body>
</html>
