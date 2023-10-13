<!DOCTYPE html>
<html>
<head>
    <title>Contagem Regressiva</title>
    <style>
        h1 {
            font-size: 24px;
        }

        #countdown {
            font-size: 48px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Falta pouco, meu Amor.</h1>
    </header>
    <main>
        <div id="countdown">
            <h2>Alexandre e Eva Gabriela <span>&#10084;</span></h2>
            <div id="timer"></div>
        </div>
    </main>
    <footer>
        <p>&copy; 2023 Seu Nome</p>
    </footer>

    <script>
        function updateCountdown() {
            const targetDate = new Date("2024-01-11T01:00:00Z").getTime();
            const now = new Date().getTime();
            const timeLeft = targetDate - now;

            if (timeLeft > 0) {
                const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
                const hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

                document.getElementById("timer").innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;
            } else {
                document.getElementById("timer").innerHTML = "A contagem regressiva terminou!";
            }
        }

        setInterval(updateCountdown, 1000);
        updateCountdown();
    </script>
</body>
</html>
