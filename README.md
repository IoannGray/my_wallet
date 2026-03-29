<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Signet</title>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Inter:wght@400&display=swap" rel="stylesheet">

    <style>
        :root {
            --bg-color: #1a1a1a; /* Матовый графит */
            --gold-color: #c5a059; /* Старое золото */
            --card-bg: #222222;
            --text-color: #a1a1a1; /* Серый для лейблов */
        }
        body {
            background-color: var(--bg-color);
            color: #ffffff;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            justify-content: center; /* Центрируем всё по вертикали */
        }
        
        /* Исправляем заголовок, убираем дефолтное название GitHub */
        .header { 
            font-family: 'Playfair Display', serif;
            font-size: 20px; 
            letter-spacing: 5px; 
            color: var(--gold-color);
            text-transform: uppercase;
            border-bottom: 1px solid var(--gold-color);
            padding-bottom: 5px;
            margin-bottom: 50px;
        }

        .card {
            background: var(--card-bg);
            width: 90%;
            max-width: 320px;
            padding: 40px 10px;
            text-align: center;
            border: 1px solid rgba(197, 160, 89, 0.3);
            box-shadow: 0 15px 35px rgba(0,0,0,0.6);
            position: relative;
        }

        .balance-label { 
            color: #8e8e93; 
            font-size: 11px; 
            text-transform: uppercase; 
            letter-spacing: 2px; 
            margin-bottom: 15px; 
        }

        /* Исправляем шрифт баланса.serif принудительно */
        .balance-value { 
            font-family: 'Playfair Display', serif !important;
            font-size: 44px; 
            font-weight: 600; 
            color: var(--gold-color);
        }

        .btn-group { 
            display: flex; 
            gap: 15px; 
            width: 100%; 
            max-width: 320px;
            margin-top: 30px;
        }

        .btn {
            background-color: transparent;
            color: var(--gold-color);
            border: 1px solid var(--gold-color);
            padding: 14px;
            font-size: 14px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            flex: 1;
            cursor: pointer;
            transition: all 0.3s;
        }
    </style>
</head>
<body>
    <div class="header">SIGNET</div>

    <div class="card">
        <div class="balance-label">Доступный баланс</div>
        <div class="balance-value" id="balance">0.00 ₽</div>
    </div>

    <div class="btn-group">
        <button class="btn" onclick="topUp()">Ввод</button>
        <button class="btn btn-secondary" onclick="sendMoney()">Вывод</button>
    </div>

    <script>
        const tg = window.Telegram.WebApp;
        tg.ready();
        tg.expand();

        function topUp() {
            tg.showAlert("Для пополнения необходимо подключить сервер (Бэкенд).");
        }
        function sendMoney() {
            tg.showAlert("Для вывода необходимо подключить сервер (Бэкенд).");
        }
    </script>
</body>
</html>
