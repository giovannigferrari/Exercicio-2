<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        input, button, select {
            padding: 10px;
            margin: 5px;
        }
        .result {
            margin-top: 20px;
        }
        .container{
            align-items: center;
            align-content: center;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
    <h1>Conversor de Temperatura</h1>
    <label for="tempInput">Informe a temperatura:</label>
    <input type="number" id="tempInput" placeholder="Digite a temperatura" />
    <label for="converterPara">Converter para:</label>
    <select id="converterPara">
        <option value="fahrenheit">Fahrenheit</option>
        <option value="celsius">Celsius</option>
    </select>
    <button onclick="converterTemperatura()">Converter</button>
    <div class="result">
        <p>Resultado: <span id="resultado"></span></p>
    </div>
    </div>
    <script>
        function converterTemperatura() {
            const tempInput = document.getElementById('tempInput').value;
            const converterPara = document.getElementById('converterPara').value;
            const resultadoSpan = document.getElementById('resultado');
            if (tempInput === "") {
                alert("Por favor, insira uma temperatura.");
                return;
            }
            const temperatura = parseFloat(tempInput);
            let resultado;
            if (converterPara === "fahrenheit") {
                resultado = (temperatura * 1.8) + 32;
                resultadoSpan.textContent = `${resultado.toFixed(2)} °F`;
            } else if (converterPara === "celsius") {
                resultado = (temperatura - 32) / 1.8;
                resultadoSpan.textContent = `${resultado.toFixed(2)} °C`;
            }
        }
    </script>
</body>
</html>
 
