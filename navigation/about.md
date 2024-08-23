---
layout: page
title: About
permalink: /about/
---

<code style= "color: #f64f2c; font-size:24px"> Tara Sehdave

<code style= "color: #f95b39; font-size:12px"> About Me

Hi, my name is Tara Sehdave and I am a senior in highschool. The reason I decided to take AP Computer Science A is because I would like to challenge myself. Although I am not an aspiring software programmer nor an expert in coding, I believe the ability to code is increasingly becoming more relevant and may someday assist me in my future career as a lawyer. 

<code style= "color: #f95b39; font-size:12px"> About Me

<code style= "color: #f95b39; font-size:12px"> About Me

<code style= "color: #f95b39; font-size:12px"> My Schedule 

| Class       | Period 
| ----------- |:-------|
| AP English Literature      |   1      |
| AP Statistics        |   2      |
| AP Computer Science A      |   3      |
| AP United States Government and Politics     |   4      |
| Offroll   |   5      |

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title><code style= "color: #f95b39; font-size:12px">Simple Drawing App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
        }

        h1 {
            margin-bottom: 20px;
        }

        .toolbar {
            margin-bottom: 10px;
        }

        canvas {
            border: 2px solid #2e3a46;
            cursor: crosshair;
        }
    </style>
</head>
<body>
    <h1>Simple Drawing App</h1>
    <div class="toolbar">
        <label for="colorPicker">Color: </label>
        <input type="color" id="colorPicker" value="#000000">
        
        <label for="brushSize">Brush Size: </label>
        <input type="range" id="brushSize" min="1" max="20" value="5">
        
        <button id="clearButton">Clear</button>
    </div>
    <canvas id="drawingCanvas"></canvas>
    <script>
        const canvas = document.getElementById('drawingCanvas');
        const ctx = canvas.getContext('2d');
        const colorPicker = document.getElementById('colorPicker');
        const brushSize = document.getElementById('brushSize');
        const clearButton = document.getElementById('clearButton');

        canvas.width = window.innerWidth * 0.8;
        canvas.height = window.innerHeight * 0.7;

        let drawing = false;

        canvas.addEventListener('mousedown', startDrawing);
        canvas.addEventListener('mouseup', stopDrawing);
        canvas.addEventListener('mousemove', draw);
        clearButton.addEventListener('click', clearCanvas);

        function startDrawing(e) {
            drawing = true;
            draw(e);  // Start drawing immediately
        }

        function stopDrawing() {
            drawing = false;
            ctx.beginPath();  // Reset the path
        }

        function draw(e) {
            if (!drawing) return;

            ctx.lineWidth = brushSize.value;
            ctx.lineCap = 'round';
            ctx.strokeStyle = colorPicker.value;

            ctx.lineTo(e.clientX - canvas.offsetLeft, e.clientY - canvas.offsetTop);
            ctx.stroke();
            ctx.beginPath();
            ctx.moveTo(e.clientX - canvas.offsetLeft, e.clientY - canvas.offsetTop);
        }

        function clearCanvas() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
        }
    </script>
</body>
</html>







