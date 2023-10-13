<!DOCTYPE html>
<html>
<head>
    <title>Countdown Timer</title>
</head>
<body>
    <h1>Countdown to January 11, 2024, 01:00 UTC</h1>
    <div id="countdown"></div>

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

                document.getElementById("countdown").innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;
            } else {
                document.getElementById("countdown").innerHTML = "The countdown has ended!";
            }
        }

        // Update the countdown every second
        setInterval(updateCountdown, 1000);

        // Call the function to start the countdown
        updateCountdown();
    </script>
</body>
</html>
