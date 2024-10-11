<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Odliczanie do 8 Lipca</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
        }
        .countdown-container {
            text-align: center;
        }
        .countdown {
            font-size: 3rem;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="countdown-container">
        <h1>Odliczanie do 8 Lipca</h1>
        <div class="countdown" id="countdown"></div>
    </div>

    <script>
        function updateCountdown() {
            const targetDate = new Date("July 8, " + (new Date().getFullYear() + 1) + " 00:00:00").getTime();
            const now = new Date().getTime();
            const timeRemaining = targetDate - now;

            const days = Math.floor(timeRemaining / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeRemaining % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeRemaining % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeRemaining % (1000 * 60)) / 1000);

            document.getElementById("countdown").innerHTML = 
                `${days} dni ${hours} godzin ${minutes} minut ${seconds} sekund`;

            if (timeRemaining < 0) {
                document.getElementById("countdown").innerHTML = "Odliczanie zakończone!";
            }
        }

        setInterval(updateCountdown, 1000);
    </script>
</body>
</html>
