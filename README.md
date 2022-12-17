# Compiladores

#Codigo JavaScript

var hojas = "";
[10, 2].forEach(j => {
    new Array(j).fill('').forEach((v, i) => {
        hojas += (
            [
                ...new Array(9 - i).fill("<span> </span>"),
                ...new Array(1 + i * 2).fill('<span class = "rojo">*</span>'),
                ...new Array(9 - i).fill("<span> </span>")
            ].join('')
        );
        hojas += "<br>"
    });
});

document.getElementById("arbol").innerHTML = hojas;

let animacion = document.querySelectorAll(".rojo")
animacion.innerHTML = hojas;

function animar() {
    for (var i = 0; i < animacion.length; i++) {
        let tiempo = i / 20 + 1;
        animacion[i].style.animation = "colores " + tiempo + "s infinite";
    }
}

window.addEventListener("load", animar);

#Codigo html

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ARBOL DE NAVIDAD</title>
    <style>
        body {
            background: black;
            display: grid;
            justify-content: center;
            text-align: center;
        }

        h1 {
            color: greenyellow;
        }

        p {
            color: teal;
        }

        .estrella {
            font-size: 100px;
            animation: colores 1s infinite;
        }

        #arbol {
            color: green;
            transition: all 1.5s;
            font-size: 25px;
        }

        .rojo {
            color: red;
            transition: all 1.5s;
            font-size: 25px;
        }

        @keyframes colores {
            0% {
                color: red;
            }

            33% {
                color: green;
            }

            66% {
                color: blue;
            }

            100% {
                color: yellow;
            }
        }
    </style>
</head>

<body>
    <div class="estrella">*</div>
    <div id="arbol"></div>
    <h1>FELIZ NAVIDAD!! Y PRÓSPERO AÑO NUEVO 2022</h1>
    <p>A toda la Escuela Politécnica Nacional</p>
    <script src="arbolDeNavidad.js"></script>

</body>

</html>

