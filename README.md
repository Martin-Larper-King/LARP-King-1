<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LARPKING</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            color: white;
            text-align: center;
            background-image: url('sfondo.jpg'); /* Cambia con il percorso dell'immagine */
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            display: flex;
            flex-direction: column;
            justify-content: center;
            height: 100vh;
        }

        .overlay {
            background: rgba(0, 0, 0, 0.6);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .container {
            position: relative;
            z-index: 1;
        }

        h1 {
            font-size: 3rem;
            margin: 0 0 20px;
        }

        .countdown {
            font-size: 2rem;
            margin-bottom: 20px;
        }

        .footer {
            margin-top: 20px;
            font-size: 1rem;
            opacity: 0.8;
        }
    </style>
</head>
<body>
    <div class="overlay"></div>
    <div class="container">
        <h1>LARPKING</h1>
        <p class="countdown" id="countdown">Caricamento arcobaleni...</p>
        <p class="footer">Stiamo preparando il gioco... torna il 20 gennaio!</p>
    </div>

    <script>
        // Data di scadenza
        const countdownDate = new Date("2025-01-20T00:00:00").getTime();

        // Aggiornamento del conto alla rovescia
        const updateCountdown = setInterval(() => {
            const now = new Date().getTime();
            const distance = countdownDate - now;

            if (distance > 0) {
                const days = Math.floor(distance / (1000 * 60 * 60 * 24));
                const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((distance % (1000 * 60)) / 1000);

                document.getElementById("countdown").innerHTML = 
                    `${days} giorni, ${hours} ore, ${minutes} minuti, ${seconds} secondi`;
            } else {
                clearInterval(updateCountdown);
                document.getElementById("countdown").innerHTML = "Il sito è pronto!";
            }
        }, 1000);
    </script>
</body>
</html>
