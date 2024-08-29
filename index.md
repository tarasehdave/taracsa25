---
layout: base
title: Student Home 
description: Home Page
hide: true
---

<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tic Tac Toe</title>
  <style>
    .board {
      display: grid;
      grid-template-columns: repeat(3, 150px);
      gap: 5px;
      margin: 20px auto;
      align-items: center;
      justify-content: center; 
    }
    .cell {
      width: 150px;
      height: 150px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 5em;
      cursor: pointer;
      border: 1px solid #333;
      border-color: #ff0000;
    }
    body {
      background-image: url('images/background.jpg');
      background-size: cover; /* Ensures the image covers the entire background */
      background-position: center; /* Centers the image */
      background-repeat: no-repeat; /* Prevents the image from repeating */
    }
    .title {
      margin-bottom: 20px;
      font-size: 4em;
      color: hotpink; /* Dark text color */
      text-align: center;
      font-family:cursive;
    }
    .button {
      padding: 10px 30px; /* Increases padding for an oval shape */
      font-size: 1.5em; /* Font size */
      color: white; /* Text color */
      background-color: teal; /* Button background color */
      border: none; /* Removes border */
      border-radius: 30px; /* High border-radius for oval shape */
      cursor: pointer; /* Cursor changes to pointer on hover */
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Adds a subtle shadow */
      transition: background-color 0.3s ease; /* Smooth transition for hover effect */
      text-align:center;
      justify-content: center;
      align-items: center;
      font-family: Georgia, serif;
    }
    .button:hover {
      background-color: hotpink; /* Darker teal on hover */
    }
    .container {
      text-align: center; /* Centers content horizontally */
      margin-top: 20px;  /* Optional: Add top margin for spacing */
    }

  </style>
</head>
<body>
<h1 class="title">Tic Tac Toe</h1>
  <div class="board">
    <div class="cell" id="cell-0" onclick="handleCellClick(0)"></div>
    <div class="cell" id="cell-1" onclick="handleCellClick(1)"></div>
    <div class="cell" id="cell-2" onclick="handleCellClick(2)"></div>
    <div class="cell" id="cell-3" onclick="handleCellClick(3)"></div>
    <div class="cell" id="cell-4" onclick="handleCellClick(4)"></div>
    <div class="cell" id="cell-5" onclick="handleCellClick(5)"></div>
    <div class="cell" id="cell-6" onclick="handleCellClick(6)"></div>
    <div class="cell" id="cell-7" onclick="handleCellClick(7)"></div>
    <div class="cell" id="cell-8" onclick="handleCellClick(8)"></div>
  </div>
<div class="container">
  <label class="button" onclick="resetGame()">Reset Game</label>
</div>

  <script language="javascript">
    // Initialize game state
let board = ["", "", "", "", "", "", "", "", ""];
let currentPlayer = "X";
let gameActive = true;

// Function to handle cell click
function handleCellClick(clickedCellIndex) {
  if (!gameActive || board[clickedCellIndex] !== "") return;

  board[clickedCellIndex] = currentPlayer;
  document.getElementById(`cell-${clickedCellIndex}`).innerText = currentPlayer;

  checkWinner();
  currentPlayer = currentPlayer === "X" ? "O" : "X";
}

// Function to check for a winner or a draw
function checkWinner() {
  const winningCombinations = [
    [0, 1, 2], [3, 4, 5], [6, 7, 8], // Rows
    [0, 3, 6], [1, 4, 7], [2, 5, 8], // Columns
    [0, 4, 8], [2, 4, 6]             // Diagonals
  ];

  for (let i = 0; i < winningCombinations.length; i++) {
    const [a, b, c] = winningCombinations[i];
    if (board[a] && board[a] === board[b] && board[a] === board[c]) {
      gameActive = false;
      alert(`Player ${currentPlayer} wins!`);
      return;
    }
  }

  if (!board.includes("")) {
    gameActive = false;
    alert("It's a draw!");
  }
}

// Function to reset the game
function resetGame() {
  board = ["", "", "", "", "", "", "", "", ""];
  currentPlayer = "X";
  gameActive = true;
  for (let i = 0; i < 9; i++) {
    document.getElementById(`cell-${i}`).innerText = "";
  }
}

  </script>
</body>
</html>


