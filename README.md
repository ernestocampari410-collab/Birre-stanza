<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Birre Stanza Pazza</title>
<style>
    @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

    body {
        margin: 0;
        font-family: 'Press Start 2P', cursive;
        overflow-x: hidden;
        background-color: #111;
        color: #fff;
    }

    header {
        text-align: center;
        padding: 40px 20px;
        background: linear-gradient(45deg, #ff0000, #ffdd00, #00ff00, #00ffff, #ff00ff);
        background-size: 400% 400%;
        animation: gradientBG 10s ease infinite;
        color: white;
        text-shadow: 2px 2px #000;
    }

    @keyframes gradientBG {
        0% {background-position:0% 50%;}
        50% {background-position:100% 50%;}
        100% {background-position:0% 50%;}
    }

    h1 {margin:0; font-size:2.5em; animation: blink 1s step-start infinite;}
    @keyframes blink {0%,50%,100% {opacity:1;}25%,75%{opacity:0;}}

    .container {
        max-width: 900px;
        margin: auto;
        padding: 20px;
        text-align: center;
    }

    .stanza {
        display: none;
        padding: 20px;
        border-radius: 15px;
        margin-top: 20px;
        box-shadow: 0 0 20px #ff00ff;
        background: rgba(0,0,0,0.7);
    }

    .stanza.active {display: block;}

    .gif {
        width: 150px;
        margin: 10px;
        animation: float 4s ease-in-out infinite;
    }

    @keyframes float {
        0%,100% {transform: translateY(0);}
        50% {transform: translateY(-20px);}
    }

    .nav-buttons {
        margin-top: 20px;
    }

    .nav-buttons button {
        padding: 10px 20px;
        margin: 0 10px;
        border-radius: 10px;
        border: none;
        font-weight: bold;
        cursor: pointer;
        background: #ff00ff;
        color: white;
        transition: 0.3s;
    }

    .nav-buttons button:hover {background:#00ffff;color:black;}

    footer {
        text-align: center;
        margin-top: 30px;
        padding: 20px;
        background: rgba(0,0,0,0.8);
    }

</style>
</head>
<body>

<header>
    <h1>Birre Stanza Pazza</h1>
    <p>Un viaggio tra poesie stupide e GIF di birra!</p>
</header>

<div class="container">
    <!-- Stanza 1 -->
    <div class="stanza active" id="stanza1">
        <h2>Stanza della Birra Allegra</h2>
        <p>Oh birra mia, frizzante amica, <br> nella bocca fai festa, mai monotona e mica critica!</p>
        <img src="https://media.giphy.com/media/xT0xeJpnrWC4XWblEk/giphy.gif" class="gif">
        <img src="https://media.giphy.com/media/l0HlQ7LRal0yKZ8y0/giphy.gif" class="gif">
    </div>

    <!-- Stanza 2 -->
    <div class="stanza" id="stanza2">
        <h2>Stanza della Birra Ribelle</h2>
        <p>Bevo birra sul divano, <br> salto come un buffone, <br> e rido a ogni sorso, senza ragione!</p>
        <img src="https://media.giphy.com/media/3o7TKtnuHOHHUjR38Y/giphy.gif" class="gif">
        <img src="https://media.giphy.com/media/5GoVLqeAOo6PK/giphy.gif" class="gif">
    </div>

    <!-- Stanza 3 -->
    <div class="stanza" id="stanza3">
        <h2>Stanza della Birra Poetica</h2>
        <p>Schiuma bianca sulla bocca, <br> brindiamo alle risate, <br> ogni sorso è una rotta!</p>
        <img src="https://media.giphy.com/media/l0Exk8EUzSLsrErEQ/giphy.gif" class="gif">
        <img src="https://media.giphy.com/media/3o6Zt8MgUuvSbkZYWc/giphy.gif" class="gif">
    </div>

    <!-- Pulsanti -->
    <div class="nav-buttons">
        <button id="prev">← Stanza precedente</button>
        <button id="next">Stanza successiva →</button>
    </div>
</div>

<footer>
    <p>Il sito delle birre stupide e delle poesie pazze. 🍺</p>
</footer>

<script>
    let current = 1;
    const total = 3;

    const showStanza = (num) => {
        for(let i=1;i<=total;i++){
            document.getElementById('stanza'+i).classList.remove('active');
        }
        document.getElementById('stanza'+num).classList.add('active');
    }

    document.getElementById('next').addEventListener('click', ()=>{
        current = current<total ? current+1 : 1;
        showStanza(current);
    });

    document.getElementById('prev').addEventListener('click', ()=>{
        current = current>1 ? current-1 : total;
        showStanza(current);
    });
</script>

</body>
</html>
