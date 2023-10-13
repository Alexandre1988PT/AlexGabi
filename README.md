<!DOCTYPE html>
<html>
<head>
    <title>Countdown Timer</title>
    <style>
        h1 {
            font-size: 24px; /* Font size for the title */
        }

        #countdown {
            font-size: 48px; /* Font size for the countdown */
        }
    </style>
</head>
<body>
    <header>
        <h1>Falta pouco, meu amor.</h1>
    </header>
    <main>
        <div id="countdown">
            <h2>Alexandre e Eva Gabriela <span>&#10084;</span></h2>
            <div id="timer"></div>
        </div>
    </main>
    
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
                document.getElementById("timer").innerHTML = "The countdown has ended!";
            }
        }

        // Update the countdown every second
        setInterval(updateCountdown, 1000);

        // Call the function to start the countdown
        updateCountdown();
    </script>
</body>
</html>
