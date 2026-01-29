# Free-calculator-online
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Calculator</title>
<style>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #0f172a;
    font-family: Arial, sans-serif;
}

.calculator {
    background: #020617;
    padding: 20px;
    border-radius: 15px;
    width: 280px;
}

.display {
    width: 100%;
    height: 60px;
    font-size: 24px;
    text-align: right;
    padding: 10px;
    border-radius: 10px;
    border: none;
    margin-bottom: 15px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    height: 50px;
    font-size: 18px;
    border-radius: 10px;
    border: none;
    cursor: pointer;
}

.number { background: #1e293b; color: white; }
.operator { background: #2563eb; color: white; }
.clear { background: #dc2626; color: white; }
.equal { background: #16a34a; color: white; grid-column: span 2; }
</style>
</head>
<body>

<div class="calculator">
    <input type="text" id="display" class="display" disabled>
    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button class="operator" onclick="append('/')">÷</button>
        <button class="operator" onclick="append('*')">×</button>
        <button class="operator" onclick="append('-')">−</button>

        <button class="number" onclick="append('7')">7</button>
        <button class="number" onclick="append('8')">8</button>
        <button class="number" onclick="append('9')">9</button>
        <button class="operator" onclick="append('+')">+</button>

        <button class="number" onclick="append('4')">4</button>
        <button class="number" onclick="append('5')">5</button>
        <button class="number" onclick="append('6')">6</button>

        <button class="number" onclick="append('1')">1</button>
        <button class="number" onclick="append('2')">2</button>
        <button class="number" onclick="append('3')">3</button>

        <button class="number" onclick="append('0')">0</button>
        <button class="number" onclick="append('.')">.</button>
        <button class="equal" onclick="calculate()">=</button>
    </div>
</div>

<script>
let display = document.getElementById("display");

function append(value) {
    display.value += value;
}

function clearDisplay() {
    display.value = "";
}

function calculate() {
    try {
        display.value = eval(display.value);
    } catch {
        display.value = "Error";
    }
}
</script>

</body>
</html>
