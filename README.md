<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Proxy Server Example</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }

        #result {
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <h1>Proxy Server Example</h1>

    <button onclick="makeProxyRequest()">Make Proxy Request</button>

    <div id="result"></div>

    <script>
        function makeProxyRequest() {
            var proxyUrl = 'https://cors-anywhere.herokuapp.com/';
            var targetUrl = 'https://www.example.com'; // Replace with your target URL

            fetch(proxyUrl + targetUrl)
                .then(response => response.text())
                .then(data => {
                    document.getElementById('result').innerHTML = '<strong>Proxy Response:</strong><br>' + data;
                })
                .catch(error => {
                    console.error('Error fetching data:', error);
                    document.getElementById('result').innerHTML = '<strong>Error:</strong><br>' + error;
                });
        }
    </script>
</body>
</html>
