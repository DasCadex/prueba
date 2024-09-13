<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carta Romántica</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffe6f2; /* Fondo rosa suave */
            margin: 0;
            font-family: 'Arial', sans-serif;
        }
        .envelope {
            width: 300px;
            height: 200px;
            background-color: #ffb3ba;
            position: relative;
            cursor: pointer;
            transition: transform 0.5s;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            border-radius: 10px;
        }
        .flap {
            width: 100%;
            height: 50%;
            background-color: #ff6666;
            position: absolute;
            top: 0;
            left: 0;
            clip-path: polygon(0% 100%, 50% 0%, 100% 100%);
            transition: 0.5s;
        }
        .envelope.open .flap {
            transform: rotateX(180deg);
            transform-origin: bottom;
        }
        .heart-message {
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: white;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            text-align: center;
            border-radius: 10px;
        }
        .envelope.open .heart-message {
            display: flex;
        }
        .heart {
            width: 100px;
            height: 90px;
            background-color: red;
            position: relative;
            margin-bottom: 10px;
        }
        .heart::before, .heart::after {
            content: "";
            width: 100px;
            height: 100px;
            background-color: red;
            border-radius: 50%;
            position: absolute;
            top: -50px;
        }
        .heart::before {
            left: 0;
        }
        .heart::after {
            right: 0;
        }
        .message {
            font-size: 20px;
            font-weight: bold;
            color: #ff4d4d; /* Rojo amoroso */
        }
        .message::after {
            content: "❤";
            display: block;
            margin-top: 10px;
            font-size: 25px;
            color: red;
        }
    </style>
</head>
<body>

<div class="envelope" onclick="openEnvelope()">
    <div class="flap"></div>
    <div class="heart-message">
        <div class="heart"></div>
        <div class="message">Te quiero :3</div>
    </div>
</div>

<script>
    function openEnvelope() {
        document.querySelector('.envelope').classList.toggle('open');
    }
</script>

</body>
</html>
