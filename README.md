<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>側網速系統</title>
    <style>
        /* 全局樣式 */
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
        }

        /* 側欄樣式 */
        .sidebar {
            height: 100%;
            width: 250px;
            position: fixed;
            top: 0;
            left: 0;
            background-color: #2c3e50;
            padding-top: 20px;
            transition: 0.3s;
            overflow-x: hidden;
        }

        .sidebar a {
            padding: 15px 20px;
            text-decoration: none;
            font-size: 18px;
            color: white;
            display: block;
            transition: 0.3s;
        }

        .sidebar a:hover {
            background-color: #34495e;
        }

        /* 主內容樣式 */
        .main-content {
            margin-left: 250px;
            padding: 20px;
            transition: 0.3s;
        }

        /* 側欄折疊 */
        .sidebar.collapsed {
            width: 0;
            padding-top: 0;
        }

        .main-content.collapsed {
            margin-left: 0;
        }

        /* 按鈕樣式 */
        .toggle-btn {
            position: absolute;
            top: 20px;
            left: 20px;
            background-color: #2c3e50;
            color: white;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
            transition: 0.3s;
        }

        .toggle-btn:hover {
            background-color: #34495e;
        }

        /* 網速卡片樣式 */
        .speed-card {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            text-align: center;
            max-width: 400px;
            margin: 20px auto;
        }

        .speed-card h2 {
            margin: 0;
            font-size: 24px;
            color: #2c3e50;
        }

        .speed-value {
            font-size: 48px;
            font-weight: bold;
            margin: 20px 0;
            color: #27ae60;
        }

        .speed-unit {
            font-size: 20px;
            color: #95a5a6;
        }

        .test-btn {
            background-color: #2e9c5c;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            transition: 0.3s;
        }

        .test-btn:hover {
            background-color: #2ecc71;
        }
    </style>
</head>
<body>
    <!-- 側欄 -->
    <div class="sidebar" id="sidebar">
        <a href="#home">首頁</a>
        <a href="#about">關於我們</a>
        <a href="#services">服務</a>
        <a href="#contact">聯繫我們</a>
    </div>

    <!-- 主內容 -->
    <div class="main-content" id="mainContent">
        <button class="toggle-btn" onclick="toggleSidebar()">☰</button>
        <h1>側網速系統</h1>
        <p>點擊下方按鈕測試網速。</p>
        <div class="speed-card" id="speedCard">
            <h2>網速測試結果</h2>
            <div>
                <span class="speed-value" id="speedValue">--</span>
                <span class="speed-unit">Mbps</span>
            </div>
            <button class="test-btn" onclick="testSpeed()">開始測試</button>
        </div>
    </div>

    <script>
        // 側欄摺疊功能
        function toggleSidebar() {
            const sidebar = document.getElementById('sidebar');
            const mainContent = document.getElementById('mainContent');
            sidebar.classList.toggle('collapsed');
            mainContent.classList.toggle('collapsed');
        }

        // 模擬網速測試功能
        function testSpeed() {
            const speedValue = document.getElementById('speedValue');
            speedValue.textContent = '測試中...';
            setTimeout(() => {
                const randomSpeed = (Math.random() * 100).toFixed(2); // 隨機網速值
                speedValue.textContent = randomSpeed;
            }, 2000); // 模擬測試延遲 2 秒
        }
    </script>
</body>
</html>
