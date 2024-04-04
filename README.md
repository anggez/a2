
        <title>Adding Program</title>
    <style>
        body{
            background-image: url(https://marketplace.canva.com/EAFX1xLvlzg/1/0/1600w/canva-blue-aesthetic-watercolor-linktree-background-Q72D6PqhxRE.jpg);
            height: 600px;
            text-align: center;
            font-style: italic
            
            
        }
        h1{
            color: rgb(57, 151, 136);
            text-shadow: 1px 1px 2px black, 0 0 25px blue, 0 0 5px darkblue;
            text-align: center;
            height: 50px;
            font-size: 40px;
            

        }
        p{
        
            text-align: center;
            font-style: italic;
            color: black;
            font-size: larger;
            border: solid;
            font-size: 30px;
        }
       
    </style>    

    <body>
        <div class="container">
            <h1>JAVASCRIPT ARITHMETIC</h1>
            <input type="number" id="num1" placeholder="ENTER FIRST NUMBER">
            <input type="number" id="num2" placeholder="ENTER SECOND NUMBER">
            <select id="operation">
                <option value="add">(+) ADD</option> 
                <option value="add">(-) SUBTRACT</option> 
                <option value="add">(*) MULTIPLY</option> 
                <option value="add">(/) DIVIDE</option> 
            </select>
            <button id="sumbutton">SUM</button>
            <p id="result"></p>
        </div>
        <script src="script.js"></script>
        <script>
             // Get references to HTML elements
            const num1Input = document.getElementById('num1');
            const num2Input = document.getElementById('num2');
            const operationSelect = document.getElementById('operation');
            const sumbutton = document.getElementById('sumbutton');
            const resultdisplay = document.getElementById('result');

            // Function to perform arithmetic operation
            function performOperation() {
                // Get the values from the input fields and convert them to numbers
                const num1 = parseFloat(num1Input.value);
                const num2 = parseFloat(num2Input.value);
                const operation = operationSelect.value;
                //Check if the inputs are valid numbers
                if (isNaN(num1) || isNaN(num2)) {
                    resultdisplay.textContent =" Please enter valid number ";
                } else {
                    //perform the selected arithmetic operation
                    let result;
                    switch (operation) {
                        case 'add': 
                             result = num1 + num2
                             break;
                        case 'subtract': 
                            result = num1 - num2
                             break;
                        case 'multipy': 
                            result = num1 * num2
                             break;     
                        case 'divide': 
                            if (num2 === 0) {
                                result = "Cannot divide by zero";
                            } else {
                                result = num1 / num2
                            }
                            break;
                            default: 
                            result = "Invalid operation";
                    }
                    // Display the result
                    resultdisplay.textContent = `Result: ${result}`;
                }
            }
            // Add click event listener to the sum button
            sumbutton.addEventListener('click', performOperation)
        </script>
