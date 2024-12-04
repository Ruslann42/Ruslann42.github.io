<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Вопросы</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: left; /* Изменил выравнивание текста на левое */
            margin-top: 50px;
        }
        #output {
            margin-top: 20px;
            font-weight: bold;
            white-space: pre-wrap; /* Сохраняет переносы строк */
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 5px;
        }
    </style>
</head>
<body>
    <h1>Вопросы</h1>
    <button onclick="loadText('file1.txt')">A1</button>
    <button onclick="loadText('file2.txt')">Б3.8</button>
    
    <div id="output"></div>

    <script>
        function loadText(file) {
            fetch(file)
                .then(response => {
                    if (!response.ok) {
                        throw new Error('Сеть не отвечает');
                    }
                    return response.text();
                })
                .then(data => {
                    document.getElementById('output').innerHTML = data;
                })
                .catch(error => {
                    document.getElementById('output').innerHTML = 'Ошибка загрузки текста: ' + error.message;
                });
        }
    </script>
</body>
</html>
