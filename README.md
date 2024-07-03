<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Open Multiple URLs</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
        }
        textarea {
            width: 300px;
            height: 150px;
            padding: 10px;
            margin-bottom: 10px;
            font-size: 16px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Open Multiple URLs</h1>
    <textarea id="urlList" placeholder="Enter each URL on a new line"></textarea>
    <button onclick="openUrls()">Open URLs</button>

    <script>
        function openUrls() {
            var urlList = document.getElementById('urlList').value;
            var urls = urlList.split('\n').map(url => url.trim()).filter(url => url);

            urls.forEach(function(url) {
                if (!url.startsWith('http')) {
                    url = 'http://' + url;
                }
                window.open(url, '_blank');
            });
        }
    </script>
</body>
</html>
