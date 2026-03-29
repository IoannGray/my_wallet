<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Signet Wallet</title>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        body {
            background-color: #000000;
            color: #ffffff;
            font-family: -apple-system, BlinkMacSystemFont, sans-serif;
            margin: 0;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            overflow: hidden;
        }
        .header { margin-top: 20px; font-size: 20px; font-weight: 600; letter-spacing: 1px; }
        .card {
            background: linear-gradient(135deg, #1c1c1e 0%, #2c2c2e 100%);
            width: 90%;
            border-radius: 25px;
            padding: 40px 20px;
            margin: 30px 0;
            text-align: center;
            border: 1px solid #3a3a3c;
        }
        .balance-label { color: #8e8e93; font-size: 13px; text-transform: uppercase; margin-bottom: 10px; }
        .balance-value { font-size: 42px; font-weight: 700; }
        .btn-group { display: flex; gap: 15px; width: 100%; justify-content: center; }
        .btn {
            background-color: #ffffff;
            color: #000000;
            border: none;
            padding: 15px 35px;
            border-radius: 15px;
            font-size: 16px;
            font-weight: 600;
            flex: 1;
        }
        .btn-dark { background-color: #1c1c1e; color: #ffffff; border: 1px solid #3a3a3c; }
    </style>
</head>
<body>
    <div class="header" id="user-name">SIGNET</div>

    <div class="card">
        <div class="balance-label">Доступный баланс</div>
        <div class="balance-value" id="balance">0.00 ₽</div>
    </div>

    <div class="btn-group">
        <button class="btn" onclick="tgAction('Пополнение')">Ввод</button>
        <button class="btn btn-dark" onclick="tgAction('Перевод')">Вывод</button>
    </div>

    <script>
        const tg = window.Telegram.WebApp;
        tg.expand();
        tg.ready();

        // Отображаем имя пользователя
        if (tg.initDataUnsafe && tg.initDataUnsafe.user) {
            document.getElementById('user-name').innerText = tg.initDataUnsafe.user.first_name.toUpperCase();
        }

        function tgAction(type) {
            tg.HapticFeedback.impactOccurred('medium'); // Вибрация при нажатии
            tg.showAlert(`Функция "${type}" будет настроена на этапе подключения базы данных.`);
        }
    </script>
</body>
</html>
