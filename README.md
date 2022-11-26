# CalculadoraBasica
Creada con JS, CSS y HTML.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora básica.</title>
    <link rel="stylesheet" href="Calculadora.css">
</head>
<body onload ="init();">
    <table class="calculadora">
        <tr>
            <td colspan="4"><span id="resultado"></span></td>
        </tr>
        <tr>
            <td><button id="siete">7</button></td>
            <td><button id="ocho">8</button></td>
            <td><button id="nueve">9</button></td>
            <td><button id="division">/</button></td>
        </tr>
        <tr>
            <td><button id="cuatro">4</button></td>
            <td><button id="cinco">5</button></td>
            <td><button id="seis">6</button></td>
            <td><button id="multiplicacion">*</button></td>
        </tr>
        <tr>
            <td><button id="uno">1</button></td>
            <td><button id="dos">2</button></td>
            <td><button id="tres">3</button></td>
            <td><button id="resta">-</button></td>
        </tr>
        <tr>
            <td><button id="igual">=</button></td>
            <td><button id="reset">C</button></td>
            <td><button id="cero">0</button></td>
            <td><button id="suma">+</button></td>
        </tr>

    </table>
    
</body>
<script src="Calculadora.js"></script>
</html>

.calculadora {
    display: block;
    margin: 0 auto;
    padding: 15px;
    background-color: goldenrod;
    width: 365px;
    height: 500px;
    border-radius: 25px;    
}

.calculadora td button {
    display: block;
    width: 70px;
    height: 70px;
    font-size: 25px;
    
}

#resultado {
    display: block;
    text-align: center;
    font-size: 40px;
    margin-bottom: 50px;
    width: 330px;
    height: 100px;
    line-height: 100px;
    background-color: white;
    border-radius: 25px;
    overflow-y: scroll;
}

let operandoa;
let operandob;
let operacion;

function init (){
    let resultado = document.getElementById("resultado");
    let reset = document.getElementById("reset");
    let suma = document.getElementById("suma");
    let resta = document.getElementById("resta");
    let multiplicacion = document.getElementById("multiplicacion");
    let division = document.getElementById("division");
    let igual = document.getElementById("igual");
    let uno = document.getElementById("uno");
    let dos = document.getElementById("dos");
    let tres = document.getElementById("tres");
    let cuatro = document.getElementById("cuatro");
    let cinco = document.getElementById("cinco");
    let seis = document.getElementById("seis");
    let siete = document.getElementById("siete");
    let ocho = document.getElementById("ocho");
    let nueve = document.getElementById("nueve");
    let cero = document.getElementById("cero");

    uno.onclick = function (e){
        resultado.textContent = resultado.textContent + "1";
    }
    dos.onclick = function (e){
        resultado.textContent = resultado.textContent + "2";
    }
    tres.onclick = function (e){
        resultado.textContent = resultado.textContent + "3";
    }
    uno.onclick = function (e){
        resultado.textContent = resultado.textContent + "1";
    }
    cuatro.onclick = function (e){
        resultado.textContent = resultado.textContent + "4";
    }
    cinco.onclick = function (e){
        resultado.textContent = resultado.textContent + "5";
    }
    seis.onclick = function (e){
        resultado.textContent = resultado.textContent + "6";
    }
    siete.onclick = function (e){
        resultado.textContent = resultado.textContent + "7";
    }
    ocho.onclick = function (e){
        resultado.textContent = resultado.textContent + "8";
    }
    nueve.onclick = function (e){
        resultado.textContent = resultado.textContent + "9";
    }
    cero.onclick = function (e){
        resultado.textContent = resultado.textContent + "0";
    }

    reset.onclick = function (e){
        resetear();
    }
    suma.onclick = function (e){
        operandoa = resultado.textContent;
        operacion = "+";
        limpiar();
    }
    resta.onclick = function (e){
        operandoa = resultado.textContent;
        operacion = "-";
        limpiar();
    }
    multiplicacion.onclick = function (e){
        operandoa = resultado.textContent;
        operacion = "*";
        limpiar();
    }
    division.onclick = function (e){
        operandoa = resultado.textContent;
        operacion = "+";
        limpiar();
    }
    igual.onclick = function (e){
        operandob = resultado.textContent;
        resolver();
    }
}

function limpiar(){
    resultado.textContent = "";
}
function resetear(){
    resultado.textContent = "";
    operandoa = 0;
    operandob = 0;
    operacion = "";
}
function resolver(){
    let res = 0;
    switch(operacion){
        case "+":
            res = parseFloat (operandoa) + parseFloat (operandob);
            break;
        case "-":
            res = parseFloat (operandoa) - parseFloat (operandob);
            break;
        case "*":
            res = parseFloat (operandoa) * parseFloat (operandob);
            break;
        case "/":
            res = parseFloat (operandoa) / parseFloat (operandob);
            break;

    }
    resetear ();
    resultado.textContent = res;
}
