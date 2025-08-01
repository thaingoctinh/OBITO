<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <title>Game Đoán Số</title>
</head>
<body>
    <h2>Chào mừng bạn đến với game Đoán số!</h2>
    <p>Hãy đoán một số từ 1 đến 100.</p>
    <input type="number" id="guessInput" min="1" max="100">
    <button onclick="checkGuess()">Đoán</button>
    <p id="result"></p>
    <p id="attempts"></p>

    <script>
        let secret = Math.floor(Math.random() * 100) + 1;
        let attempts = 0;

        function checkGuess() {
            const guess = Number(document.getElementById('guessInput').value);
            attempts++;
            let result = "";

            if (guess < secret) {
                result = "Số bạn nhỏ hơn số bí mật.";
            } else if (guess > secret) {
                result = "Số bạn lớn hơn số bí mật.";
            } else {
                result = `Chúc mừng! Bạn đã đoán đúng sau ${attempts} lần.`;
            }

            document.getElementById('result').textContent = result;
            document.getElementById('attempts').textContent = `Số lần đoán: ${attempts}`;
        }
    </script>
</body>
</html>
