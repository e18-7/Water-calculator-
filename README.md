# Water-calculator-
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>حاسبة استهلاك الماء</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&display=swap');

        body {
            font-family: 'Cairo', sans-serif;
            background: linear-gradient(to right, #4facfe, #00f2fe);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            padding: 20px;
        }

        .container {
            background: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            text-align: center;
            width: 100%;
            max-width: 400px;
        }

        h2 {
            color: #007acc;
            margin-bottom: 10px;
        }

        .input-group {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            margin: 10px 0;
        }

        input {
            width: 50%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
            text-align: center;
        }

        button {
            background: #007acc;
            color: white;
            padding: 12px;
            border: none;
            border-radius: 5px;
            font-size: 18px;
            cursor: pointer;
            transition: 0.3s;
            width: 100%;
        }

        button:hover {
            background: #005fa3;
        }

        .result-box {
            margin-top: 20px;
            padding: 15px;
            background: #e0f7fa;
            border-radius: 8px;
            font-size: 18px;
            display: none;
            transition: 0.3s ease-in-out;
        }

        .error {
            color: red;
            font-size: 14px;
            margin-top: 5px;
        }

        @media (max-width: 480px) {
            .container {
                width: 90%;
                padding: 20px;
            }

            h2 {
                font-size: 20px;
            }

            input {
                width: 60%;
                font-size: 14px;
            }

            button {
                font-size: 16px;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <h2>حاسبة استهلاك الماء</h2>
        <p>أدخل وزنك بالكيلوغرام:</p>
        <div class="input-group">
            <input type="number" id="weight" placeholder="مثال: 70">
        </div>
        <button onclick="calculateWater()">احسب كمية الماء</button>
        <p class="error" id="error-msg"></p>
        <div class="result-box" id="result"></div>
    </div>

    <script>
        function calculateWater() {
            var weight = document.getElementById('weight').value;
            var errorMsg = document.getElementById('error-msg');
            var resultBox = document.getElementById('result');

            if (!weight || weight <= 0) {
                errorMsg.textContent = 'الرجاء إدخال وزن صحيح!';
                resultBox.style.display = 'none';
                return;
            }

            errorMsg.textContent = ''; // مسح رسالة الخطأ
            var waterInLiters = (weight * 35) / 1000; // تحويل إلى لتر
            
            resultBox.innerHTML = `💧 يجب أن تشرب حوالي <strong>${waterInLiters.toFixed(2)} لتر</strong> من الماء يومياً للحفاظ على صحتك!`;
            resultBox.style.display = 'block';
        }
    </script>

</body>
</html>
