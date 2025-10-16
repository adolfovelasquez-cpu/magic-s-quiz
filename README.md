<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Juego de Verbos en Inglés -S, -ES, -IES</title>
  <style>
    body {
      font-family: "Poppins", sans-serif;
      background-color: #000;
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
      overflow: hidden;
    }

    .container {
      background-color: #111;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 0 20px #00aaff;
      text-align: center;
      width: 90%;
      max-width: 500px;
      animation: fadeIn 1s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    h1 {
      color: #00aaff;
      margin-bottom: 20px;
    }

    .question {
      font-size: 1.3em;
      margin-bottom: 20px;
    }

    .btn {
      display: block;
      background-color: #003366;
      color: #fff;
      border: none;
      padding: 12px;
      margin: 10px auto;
      border-radius: 10px;
      width: 80%;
      cursor: pointer;
      transition: all 0.3s ease;
      font-size: 1em;
    }

    .btn:hover {
      background-color: #0055aa;
      transform: scale(1.05);
    }

    .correct {
      background-color: #00cc66 !important;
    }

    .incorrect {
      background-color: #cc0033 !important;
    }

    .score {
      font-size: 1.1em;
      margin-bottom: 10px;
      color: #ffaa00;
    }

    .hidden {
      display: none;
    }

    #final {
      font-size: 1.3em;
      color: #00ff99;
    }

    #restart {
      background-color: #0077cc;
      margin-top: 20px;
      padding: 10px 20px;
      border-radius: 10px;
      border: none;
      cursor: pointer;
      color: white;
      transition: 0.3s;
    }

    #restart:hover {
      background-color: #00aaff;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>Juego: Verbos en Inglés</h1>
    <div class="score">Puntaje: <span id="score">0</span></div>
    <div id="quiz">
      <div id="question" class="question"></div>
      <div id="answers"></div>
    </div>
    <div id="final" class="hidden"></div>
    <button id="restart" class="hidden">Jugar de nuevo</button>
  </div>

  <script>
    const questions = [
      {
        question: "¿Cuál es la forma correcta del verbo para 'He ___ (play) soccer'?",
        answers: ["plays", "plaies", "playes"],
        correct: "plays"
      },
      {
        question: "¿Cuál es la forma correcta del verbo para 'She ___ (go) to school'?",
        answers: ["gos", "goes", "goies"],
        correct: "goes"
      },
      {
        question: "¿Cuál es la forma
