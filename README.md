Calculadora-profissional 

Calculadora moderna e responsiva desenvolvida com HTML, CSS e JavaScript. Interface intuitiva, design profissional e totalmente funcional no navegador.


<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Calculadora Profissional</title>

<style>
body {
    background: #0f172a;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-family: Arial, sans-serif;
}

.calculadora {
    background: #1e293b;
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 0 25px #000;
}

.display {
    width: 100%;
    height: 60px;
    background: #020617;
    color: #38bdf8;
    font-size: 2em;
    text-align: right;
    padding: 10px;
    border-radius: 10px;
    margin-bottom: 15px;
    overflow: hidden;
}

.botoes {
    display: grid;
    grid-template-columns: repeat(4, 70px);
    gap: 10px;
}

button {
    height: 60px;
    font-size: 1.5em;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    background: #334155;
    color: white;
    transition: 0.2s;
}

button:hover {
    background: #475569;
}

.operador {
    background: #f59e0b;
}

.igual {
    background: #22c55e;
    grid-column: span 2;
}

.limpar {
    background: #ef4444;
}
</style>

</head>
<body>

<div class="calculadora">
    <div class="display" id="display">0</div>

    <div class="botoes">
        <button class="limpar" onclick="limpar()">C</button>
        <button onclick="apagar()">⌫</button>
        <button class="operador" onclick="adicionar('/')">÷</button>
        <button class="operador" onclick="adicionar('*')">×</button>

        <button onclick="adicionar('7')">7</button>
        <button onclick="adicionar('8')">8</button>
        <button onclick="adicionar('9')">9</button>
        <button class="operador" onclick="adicionar('-')">-</button>

        <button onclick="adicionar('4')">4</button>
        <button onclick="adicionar('5')">5</button>
        <button onclick="adicionar('6')">6</button>
        <button class="operador" onclick="adicionar('+')">+</button>

        <button onclick="adicionar('1')">1</button>
        <button onclick="adicionar('2')">2</button>
        <button onclick="adicionar('3')">3</button>
        <button onclick="calcular()" class="igual">=</button>

        <button onclick="adicionar('0')">0</button>
        <button onclick="adicionar('.')">.</button>
    </div>
</div>

<script>
let display = document.getElementById("display");

function adicionar(valor) {
    if (display.innerText === "0") {
        display.innerText = valor;
    } else {
        display.innerText += valor;
    }
}

function limpar() {
    display.innerText = "0";
}

function apagar() {
    display.innerText = display.innerText.slice(0, -1);
    if (display.innerText === "") {
        display.innerText = "0";
    }
}

function calcular() {
    try {
        display.innerText = eval(display.innerText);
    } catch {
        display.innerText = "Erro";
    }
}
</script>

</body>
</html>