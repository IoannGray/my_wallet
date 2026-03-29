<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Signet Wallet</title>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        body {
        background-color: var(--bg-color);
        /* Добавляем легкий радиальный градиент, чтобы центр чуть светился */
        background-image: radial-gradient(circle at center, #1e1e1e 0%, #121212 100%);
        color: var(--text-color);
        font-family: -apple-system, BlinkMacSystemFont, sans-serif;
        margin: 0;
        padding: 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
        min-height: 100vh;
    }
    .header { 
        margin-top: 20px; 
        font-size: 18px; 
        font-weight: 300; 
        letter-spacing: 3px; 
        color: #a1a1a1;
    }
    .card {
        background: var(--card-bg);
        width: 90%;
        border-radius: 24px;
        padding: 40px 20px;
        margin: 30px 0;
        text-align: center;
        /* Тонкая рамка, которая создает эффект стекла */
        border: 1px solid rgba(255, 255, 255, 0.05);
        box-shadow: 0 10px 30px rgba(0,0,0,0.5);
    }
    .balance-label { color: #636366; font-size: 12px; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 8px; }
    .balance-value { font-size: 40px; font-weight: 600; }
    
    .btn-group { display: flex; gap: 12px; width: 100%; }
    .btn {
        background-color: #ffffff;
        color: #000000;
        border: none;
        padding: 16px;
        border-radius: 14px;
        font-size: 15px;
        font-weight: 600;
        flex: 1;
        transition: opacity 0.2s;
    }
    .btn-dark { background-color: #2c2c2e; color: #ffffff; border: 1px solid #3a3a3c; }
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
