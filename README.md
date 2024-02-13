<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Blackbox - Pegadinha</title>
<style>
    body {
        font-family: Arial, sans-serif;
        text-align: center;
    }
    .container {
        width: 80%;
        margin: auto;
        margin-top: 50px;
        border: 2px solid #333;
        border-radius: 10px;
        padding: 20px;
    }
    .question {
        font-size: 24px;
        margin-bottom: 20px;
    }
    .options {
        display: flex;
        justify-content: center;
    }
    .option {
        margin: 0 10px;
        padding: 10px 20px;
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 18px;
    }
    .form {
        display: flex;
        justify-content: center;
        margin-top: 20px;
    }
    input[type="text"] {
        padding: 10px;
        font-size: 18px;
        border-radius: 5px;
        border: 1px solid #ccc;
    }
    button {
        margin-left: 10px;
        padding: 10px 20px;
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 18px;
    }
</style>
</head>
<body>

<div class="container">
    <div class="story">
        <p>Você está caminhando por uma floresta misteriosa quando encontra uma caixa estranha.</p>
        <p>Na caixa, há uma pergunta intrigante escrita: <strong>Tu me ama?</strong></p>
        <p>Você decide responder:</p>
    </div>
    
    <div class="prompt">
        <div class="question">Tu me ama?</div>
        <div class="options">
            <button class="option" onclick="resposta('Não')">Sim</button>
            <button class="option" onclick="respostaErrada()">Não</button>
        </div>
    </div>
</div>

<div class="container" id="alianca" style="display: none;">
    <div class="story">
        <p>Parabéns! Você acertou a primeira pergunta.</p>
        <p>Agora, para prosseguir, responda: Qual é o tamanho da aliança que ela usa?</p>
    </div>
    
    <div class="form">
        <input type="text" id="tamanhoAlianca" placeholder="Digite o tamanho da aliança">
        <button onclick="verificarTamanho()">Enviar</button>
    </div>
</div>

<script>
    function resposta(resposta) {
        if (resposta === 'Não') {
            alert("Você escolheu: " + resposta + ". Resposta correta! A caixa se abre revelando seu próximo desafio.");
            // Exibir a próxima seção
            document.getElementById("alianca").style.display = "block";
        } else {
            alert("Resposta errada! Você escolheu a resposta sebosa.");
            // Aqui você pode adicionar ações para lidar com a resposta incorreta
        }
    }
    
    function respostaErrada() {
        alert("Resposta errada! Você escolheu a resposta sebosa.");
    }
    
    function verificarTamanho() {
        var tamanho = document.getElementById("tamanhoAlianca").value;
        if (tamanho.trim() === "") {
            alert("Por favor, digite o tamanho da aliança.");
        } else {
            alert("O tamanho da aliança que ela usa é: " + tamanho + ". Próximo desafio em breve!");
            // Aqui você pode adicionar mais ações com base na resposta do tamanho da aliança
        }
    }
</script>

</body>
</html>
