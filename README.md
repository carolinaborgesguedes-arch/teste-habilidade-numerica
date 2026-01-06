# teste-habilidade-numerica<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Teste de Habilidades</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f6f8;
      padding: 20px;
    }
    .container {
      max-width: 700px;
      margin: auto;
      background: #fff;
      padding: 25px;
      border-radius: 8px;
    }
    h1 {
      text-align: center;
    }
    .question {
      margin-bottom: 20px;
    }
    button {
      background: #007bff;
      color: white;
      border: none;
      padding: 12px 20px;
      font-size: 16px;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background: #0056b3;
    }
    .result {
      margin-top: 20px;
      font-weight: bold;
      font-size: 18px;
      text-align: center;
    }
  </style>
</head>
<body>

<div class="container">
  <h1>Teste de Habilidade Numérica</h1>

  <form id="quizForm">

    <div class="question">
      <p><strong>1. Quanto é 25% de 200?</strong></p>
      <label><input type="radio" name="q1" value="a"> 25</label><br>
      <label><input type="radio" name="q1" value="b"> 40</label><br>
      <label><input type="radio" name="q1" value="c"> 50</label><br>
      <label><input type="radio" name="q1" value="d"> 75</label>
    </div>

    <div class="question">
      <p><strong>2. Se um produto custa R$ 120 e sofre 10% de desconto, qual o valor final?</strong></p>
      <label><input type="radio" name="q2" value="a"> R$ 100</label><br>
      <label><input type="radio" name="q2" value="b"> R$ 108</label><br>
      <label><input type="radio" name="q2" value="c"> R$ 110</label><br>
      <label><input type="radio" name="q2" value="d"> R$ 112</label>
    </div>

    <div class="question">
      <p><strong>3. Qual é o próximo número da sequência: 2, 4, 8, 16, ?</strong></p>
      <label><input type="radio" name="q3" value="a"> 18</label><br>
      <label><input type="radio" name="q3" value="b"> 20</label><br>
      <label><input type="radio" name="q3" value="c"> 24</label><br>
      <label><input type="radio" name="q3" value="d"> 32</label>
    </div>

    <button type="button" onclick="corrigir()">Enviar Respostas</button>

    <div class="result" id="resultado"></div>

  </form>
</div>

<script>
  function corrigir() {
    let score = 0;

    const respostasCorretas = {
      q1: "c",
      q2: "b",
      q3: "d"
    };

    for (let pergunta in respostasCorretas) {
      const resposta = document.querySelector(`input[name="${pergunta}"]:checked`);
      if (resposta && resposta.value === respostasCorretas[pergunta]) {
        score++;
      }
    }

    document.getElementById("resultado").innerText =
      `Você acertou ${score} de ${Object.keys(respostasCorretas).length} questões.`;
  }
</script>

</body>
</html>
