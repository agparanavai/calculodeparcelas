<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Salarios</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }
    input {
      margin: 5px 0;
      padding: 5px;
      width: 200px;
    }
    button {
      padding: 6px 12px;
      margin: 10px 0;
    }
    p {
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h2>Informe os salarios</h2>

  <label for="salario1">Salario 1:</label><br>
  <input type="number" id="salario1" placeholder="Ex: 2500"><br>

  <label for="salario2">Salario 2:</label><br>
  <input type="number" id="salario2" placeholder="Ex: 3200"><br>

  <label for="salario3">Salario 3:</label><br>
  <input type="number" id="salario3" placeholder="Ex: 4100"><br>

  <button onclick="calcularParcelas()">Calcular Parcelas</button>

  <p id="parcelas"></p>

  <script>
    function calcularParcelas() {
      const s1 = parseFloat(document.getElementById("salario1").value) || 0;
      const s2 = parseFloat(document.getElementById("salario2").value) || 0;
      const s3 = parseFloat(document.getElementById("salario3").value) || 0;

      const media = (s1 + s2 + s3) / 3;
      let parcela = 0;

      if (media <= 2138.76) {
        parcela = media * 0.80;
      } else if (media <= 3564.96) {
        parcela = ((media - 2138.76) * 0.50) + 1711.01;
      } else {
        parcela = 3564.96;
      }

      document.getElementById("parcelas").innerText = 
        `Valor da parcela: R$ ${parcela.toFixed(2)}`;
    }
  </script>

</body>
</html>
