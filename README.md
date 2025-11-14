<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ANTeam Title Song Sort</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .song-list {
            margin-bottom: 20px;
        }
        .song-item {
            margin: 10px 0;
        }
    </style>
</head>
<body>

    <h1>ANTeam Title Song Sort</h1>

    <div class="song-list">
        <div class="song-item">
            <img src="image_url1.jpg" alt="War Cry" width="50"> <br> 
            War Cry
            <select id="song1">
                <option value="좋음">좋음</option>
                <option value="나쁨">나쁨</option>
                <option value="둘다좋다">둘다좋다</option>
                <option value="둘다모르겠다">둘다모르겠다</option>
            </select>
        </div>

        <div class="song-item">
            <img src="image_url2.jpg" alt="Yukiakari" width="50"> <br>
            Yukiakari
            <select id="song2">
                <option value="좋음">좋음</option>
                <option value="나쁨">나쁨</option>
                <option value="둘다좋다">둘다좋다</option>
                <option value="둘다모르겠다">둘다모르겠다</option>
            </select>
        </div>

        <div class="song-item">
            <img src="image_url3.jpg" alt="Under the skin" width="50"> <br>
            Under the skin
            <select id="song3">
                <option value="좋음">좋음</option>
                <option value="나쁨">나쁨</option>
                <option value="둘다좋다">둘다좋다</option>
                <option value="둘다모르겠다">둘다모르겠다</option>
            </select>
        </div>

        <div class="song-item">
            <img src="image_url4.jpg" alt="FIREWORK" width="50"> <br>
            FIREWORK
            <select id="song4">
                <option value="좋음">좋음</option>
                <option value="나쁨">나쁨</option>
                <option value="둘다좋다">둘다좋다</option>
                <option value="둘다모르겠다">둘다모르겠다</option>
            </select>
        </div>

        <div class="song-item">
            <img src="image_url5.jpg" alt="Samidare" width="50"> <br>
            Samidare
            <select id="song5">
                <option value="좋음">좋음</option>
                <option value="나쁨">나쁨</option>
                <option value="둘다좋다">둘다좋다</option>
                <option value="둘다모르겠다">둘다모르겠다</option>
            </select>
        </div>

        <div class="song-item">
            <img src="image_url6.jpg" alt="Aoarashi" width="50"> <br>
            Aoarashi
            <select id="song6">
                <option value="좋음">좋음</option>
                <option value="나쁨">나쁨</option>
                <option value="둘다좋다">둘다좋다</option>
                <option value="둘다모르겠다">둘다모르겠다</option>
            </select>
        </div>

        <div class="song-item">
            <img src="image_url7.jpg" alt="Jyuugoya" width="50"> <br>
            Jyuugoya
            <select id="song7">
                <option value="좋음">좋음</option>
                <option value="나쁨">나쁨</option>
                <option value="둘다좋다">둘다좋다</option>
                <option value="둘다모르겠다">둘다모르겠다</option>
            </select>
        </div>

        <div class="song-item">
            <img src="image_url8.jpg" alt="Back to Life" width="50"> <br>
            Back to Life
            <select id="song8">
                <option value="좋음">좋음</option>
                <option value="나쁨">나쁨</option>
                <option value="둘다좋다">둘다좋다</option>
                <option value="둘다모르겠다">둘다모르겠다</option>
            </select>
        </div>

        <div class="song-item">
            <img src="image_url9.jpg" alt="Go in Blind" width="50"> <br>
            Go in Blind
            <select id="song9">
                <option value="좋음">좋음</option>
                <option value="나쁨">나쁨</option>
                <option value="둘다좋다">둘다좋다</option>
                <option value="둘다모르겠다">둘다모르겠다</option>
            </select>
        </div>
    </div>

    <button onclick="generateRanking()">Generate Ranking</button>

    <div id="rankingResults"></div>

    <script>
        function generateRanking() {
            // 각 노래의 선택값을 가져옵니다.
            let results = [];
            for (let i = 1; i <= 9; i++) {
                let song = document.getElementById('song' + i).value;
                results.push({ song: document.getElementById('song' + i).previousElementSibling.textContent.trim(), vote: song });
            }

            // 결과를 정렬하기 (예시: '좋음' > '둘다좋다' > '둘다모르겠다' > '나쁨')
            results.sort(function(a, b) {
                const order = { '좋음': 1, '둘다좋다': 2, '둘다모르겠다': 3, '나쁨': 4 };
                return order[a.vote] - order[b.vote];
            });

            // 결과 표시
            let rankingHTML = "<h2>Ranking Results:</h2><ul>";
            results.forEach(function(result, index) {
                rankingHTML += `<li>${index + 1}. ${result.song} - ${result.vote}</li>`;
            });
            rankingHTML += "</ul>";

            document.getElementById('rankingResults').innerHTML = rankingHTML;
        }
    </script>

</body>
</html>
