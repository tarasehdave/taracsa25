---
layout: page
title: Traveling
permalink: /git/
---

{% include home.html %}

<!-- <html lang="en"> -->
<!-- <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dependent Dropdown Example</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            padding: 20px;
        }
        div {
            margin-bottom: 20px;
        }
        label {
            margin-right: 10px;
            font-weight: bold;
        }   
        select {
            padding: 10px;
            width: 200px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #fff;
            font-size: 16px;
            transition: border-color 0.3s;
        }
        select:focus {
            border-color: #007bff;
            outline: none;
        }
        select option {
            padding: 10px;
        }
    </style>
</head>
<body>
    <div>
        <label for="dropdown1">Climate</label>
        <select id="dropdown1">
            <option value="">-- Select an Option --</option>
            <option value="tropical">Tropical</option>
            <option value="island">Island</option>
        </select>
    </div>
    <div>
        <label for="dropdown2">Cities</label>
        <select id="dropdown2">
            <option value="">-- Select an Option --</option>
        </select>
    </div>
    <script language="javascript">
        const dropdown1 = document.getElementById('dropdown1');
        const dropdown2 = document.getElementById('dropdown2');
        const options = {
            tropical: [
            { value: 'india', text: 'India' },
            { value: 'brazil', text: 'Brazil' },
            { value: 'mexico', text: 'Mexico' }
    ],
    island: [
        { value: 'hawaii', text: 'Hawaii' },
        { value: 'borabora', text: 'Bora Bora' },
        { value: 'bahrain', text: 'Bahrain' }
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
    </script>
    </body>
    </html>



 -->