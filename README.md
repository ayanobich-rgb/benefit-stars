<!DOCTYPE html>
<html>
<head>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        body { background: #f0f2f5; font-family: sans-serif; text-align: center; padding: 20px; }
        .card { background: white; border-radius: 15px; padding: 15px; margin: 10px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
        button { background: #0088cc; color: white; border: none; padding: 10px 20px; border-radius: 10px; width: 100%; cursor: pointer; }
        h2 { color: #333; }
    </style>
</head>
<body>
    <h2>Магазин Звезд ⭐</h2>
    <div class="card">
        <h3>100 Звезд</h3>
        <p>Цена: 133.84 руб.</p>
        <button onclick="sendOrder(100, 199)">Купить</button>
    </div>
    <div class="card">
        <h3>500 Звезд</h3>
        <p>Цена: 669.1 руб.</p>
        <button onclick="sendOrder(500, 950)">Купить</button>
    </div>

    <script>
        let tg = window.Telegram.WebApp;
        tg.expand(); // Раскрыть на весь экран

        function sendOrder(amount, price) {
            // Отправляем данные обратно в бота
            let data = {
                amount: amount,
                price: price
            };
            tg.sendData(JSON.stringify(data)); 
            tg.close(); // Закрыть окно после выбора
        }
    </script>
</body>
</html>
