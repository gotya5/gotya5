<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>APKPure Search</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
        }
        .header {
            background-color: #333;
            color: white;
            padding: 10px;
            text-align: center;
        }
        .search-container {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }
        .search-box {
            width: 70%;
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .search-button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .results {
            margin-top: 20px;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
        }
        .result-card {
            background-color: white;
            border: 1px solid #ddd;
            margin: 10px;
            width: 200px;
            padding: 10px;
            border-radius: 8px;
            text-align: center;
        }
        .result-card img {
            max-width: 100%;
            border-radius: 5px;
        }
        .result-card a {
            display: block;
            margin-top: 10px;
            padding: 8px;
            background-color: #4CAF50;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
        }
        .result-card a:hover {
            background-color: #45a049;
        }
        .bottom-nav {
            position: fixed;
            bottom: 0;
            width: 100%;
            background-color: #333;
            display: flex;
            justify-content: space-around;
            padding: 10px;
        }
        .bottom-nav a {
            color: white;
            font-size: 20px;
            text-decoration: none;
        }
    </style>
</head>
<body>

    <div class="header">
        <h1>APKPure ऐप सर्च</h1>
    </div>

    <div class="search-container">
        <input type="text" class="search-box" id="searchBox" placeholder="गेम या ऐप खोजें">
        <button class="search-button" onclick="searchApps()">खोजें</button>
    </div>

    <div class="results" id="resultsContainer"></div>

    <div class="bottom-nav">
        <a href="#home"><i class="fas fa-home"></i> होम</a>
        <a href="#history"><i class="fas fa-history"></i> हिस्ट्री</a>
    </div>

    <script>
        const apps = [
            { name: 'GTA San Andreas', image: 'https://via.placeholder.com/150', downloadLink: 'https://apkpure.com/gta-san-andreas/com.rockstargames.gtasa' },
            { name: 'PUBG Mobile', image: 'https://via.placeholder.com/150', downloadLink: 'https://apkpure.com/pubg-mobile/com.tencent.ig' },
            { name: 'WhatsApp', image: 'https://via.placeholder.com/150', downloadLink: 'https://apkpure.com/whatsapp/com.whatsapp' }
        ];

        function searchApps() {
            const query = document.getElementById('searchBox').value.toLowerCase();
            const filteredApps = apps.filter(app => app.name.toLowerCase().includes(query));
            displayResults(filteredApps);
        }

        function displayResults(filteredApps) {
            const resultsContainer = document.getElementById('resultsContainer');
            resultsContainer.innerHTML = '';

            if (filteredApps.length === 0) {
                resultsContainer.innerHTML = '<p>कोई परिणाम नहीं मिला।</p>';
                return;
            }

            filteredApps.forEach(app => {
                const appCard = document.createElement('div');
                appCard.classList.add('result-card');
                appCard.innerHTML = `
                    <img src="${app.image}" alt="${app.name} की इमेज">
                    <h3>${app.name}</h3>
                    <a href="${app.downloadLink}" target="_blank">डाउनलोड APK</a>
                `;
                resultsContainer.appendChild(appCard);
            });
        }
    </script>

</body>
</html>

<!--
**gotya5/gotya5** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
