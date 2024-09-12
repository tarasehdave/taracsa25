---
toc: True
comments: True
layout: post
title: Locations
type: ccc
permalink: location
menu: nav/home.html
courses: {'csa': {'week': 0}}
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Select your destination</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f9f9f9;
            padding: 40px;
            /* display: flex; */
            justify-content: center;
            align-items: center;
/*             height: 100vh;
            margin: 0; */
        }
        .container {
            background-color: #fff;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            display: flex; 
            flex-direction: column;
            gap: 20px;
            align-items: center;
        }
        label {
            font-weight: 600;
            font-size: 1.1em;   
            flex-basis: 100px; 
        }
        select {
            padding: 12px 15px;
            width: 250px;
            border: 1px solid #ccc;
            border-radius: 8px;
            background-color: #fff;
            font-size: 1em;
            color: #333;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            transition: border-color 0.3s, box-shadow 0.3s;
        }
        select:focus {
            border-color: #007bff;
            box-shadow: 0 2px 8px rgba(0, 123, 255, 0.25);
            outline: none;
        }
        select:hover {
            cursor: pointer;
            border-color: #0056b3;
        }
        button {
            padding: 12px 20px;
            font-size: 1em;
            color: #fff;
            background-color: hotpink;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s, box-shadow 0.3s;
            align-self: left;
            margin-top: 20px;
        }
        button:hover {
            background-color: pink;
            box-shadow: 0 2px 8px rgba(0, 123, 255, 0.25);
        }
        .dropdown-group {
            display: flex;
            gap: 15px;
            align-items: center;
            width: 100%;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="dropdown-group">
            <label for="dropdown1">Country</label>
            <select id="dropdown1">
                <option value="">-- Select an Option --</option>
                <option value="italy">Italy</option>
                <option value="greece">Greece</option>
                <option value="india">India</option>
            </select>
        </div>
        <div class="dropdown-group">
            <label for="dropdown2">Cities</label>
            <select id="dropdown2">
                <option value="">-- Select an Option --</option>
            </select>
        </div>
        <button type="button" onclick="handleSubmit()">Select</button>
    </div>
    <script language="javascript">
        const dropdown1 = document.getElementById('dropdown1');
        const dropdown2 = document.getElementById('dropdown2');
        const options = {
            italy: [
            { value: 'rome', text: 'Rome' },
            { value: 'florence', text: 'Florence' },
            { value: 'venice', text: 'Venice' }
            ],
            greece: [
                { value: 'athens', text: 'Athens' },
                { value: 'corfu', text: 'Corfu' },
                { value: 'santorini', text: 'Santorini' }
            ],
            india: [
                { value: 'mumbai', text: 'Mumbai' },
                { value: 'delhi', text: 'Delhi' },
                { value: 'bangalore', text: 'Bangalore' }
            ]
            
        };
        dropdown1.addEventListener('change', function() {
            const selectedValue = this.value;  
            // Clear previous options in dropdown2
            dropdown2.innerHTML = '<option value="">-- Select an Option --</option>';  
            if (selectedValue) {
                // Populate dropdown2 based on the selected value in dropdown1
                const selectedOptions = options[selectedValue];
                selectedOptions.forEach(option => {
                    const newOption = document.createElement('option');
                    newOption.value = option.value;
                    newOption.textContent = option.text;
                    dropdown2.appendChild(newOption);
                });
            }
        });
        function handleSubmit() {
            const dropdown1Value = document.getElementById('dropdown1').value;
            const dropdown2Value = document.getElementById('dropdown2').value;
            alert(`You selected: ${dropdown1Value} and ${dropdown2Value}`);
        }
    </script>
    </body>
    </html>


