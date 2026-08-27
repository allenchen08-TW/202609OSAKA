<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>202609 大阪旅遊行程表</title>
  
  <!-- Google Fonts: 導入精緻黑體與英文 serif 字體 -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;700&family=Noto+Sans+TC:wght@300;400;500;600;700&display=swap" rel="stylesheet">

  <style>
    :root {
      --primary-color: #1a252c;      /* 深海軍藍 / 近黑 */
      --secondary-color: #a38157;    /* 香檳金 */
      --accent-color: #cbb28d;       /* 淺金色 */
      --bg-color: #f8f7f5;           /* 柔和奶油米白 */
      --card-bg: #ffffff;            /* 純白卡片 */
      --text-main: #2b2b2b;          /* 主文字 */
      --text-muted: #666666;         /* 次要文字 */
      --border-color: #e8e4de;       /* 淡雅邊框 */
      --smoke-bg: #f5ece9;           /* 警示/吸菸標籤底色 */
      --smoke-text: #b85c47;
    }

    * {
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Noto Sans TC', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      line-height: 1.7;
      color: var(--text-main);
      background-color: var(--bg-color);
      margin: 0;
      padding: 0;
      letter-spacing: 0.03em;
    }

    /* 頂部導覽列 */
    .nav-container {
      position: sticky;
      top: 0;
      background: rgba(26, 37, 44, 0.95);
      backdrop-filter: blur(10px);
      padding: 14px 20px;
      z-index: 1000;
      box-shadow: 0 4px 20px rgba(0,0,0,0.08);
      display: flex;
      gap: 12px;
      overflow-x: auto;
      white-space: nowrap;
    }

    .tab-btn {
      background: transparent;
      color: #e0d8cc;
      border: 1px solid rgba(203, 178, 137, 0.3);
      padding: 6px 18px;
      border-radius: 30px;
      cursor: pointer;
      font-weight: 400;
      font-size: 13px;
      text-decoration: none;
      transition: all 0.3s ease;
      letter-spacing: 0.05em;
    }

    .tab-btn:hover, .tab-btn.active {
      background: var(--secondary-color);
      color: #ffffff;
      border-color: var(--secondary-color);
      transform: translateY(-1px);
    }

    /* 主要容器 */
    .container {
      max-width: 960px;
      margin: 30px auto;
      padding: 0 20px;
    }

    /* 頁面精緻標題 */
    .page-header {
      text-align: center;
      margin-bottom: 35px;
    }

    .page-title-en {
      font-family: 'Cinzel', serif;
      font-size: 14px;
      letter-spacing: 0.3em;
      color: var(--secondary-color);
      text-transform: uppercase;
      margin-bottom: 5px;
    }

    .page-title {
      font-size: 26px;
      font-weight: 600;
      color: var(--primary-color);
      margin: 0;
    }

    /* 航班資訊卡片 */
    .flight-card {
      background: linear-gradient(135deg, #1a252c 0%, #2c3a44 100%);
      color: #fff;
      border-radius: 16px;
      padding: 28px 32px;
      margin-bottom: 35px;
      box-shadow: 0 10px 30px rgba(26, 37, 44, 0.12);
      border: 1px solid rgba(203, 178, 137, 0.2);
    }

    .flight-card h2 {
      margin-top: 0;
      font-family: 'Cinzel', serif;
      font-size: 18px;
      letter-spacing: 0.1em;
      border-bottom: 1px solid rgba(255,255,255,0.15);
      padding-bottom: 12px;
      color: var(--accent-color);
      font-weight: 500;
    }

    .flight-card p {
      margin: 8px 0;
      font-size: 14px;
      color: #d1d5db;
    }

    .flight-card strong {
      color: #ffffff;
      font-weight: 500;
    }

    /* 內容區塊卡片 */
    .section-card {
      background: var(--card-bg);
      border-radius: 16px;
      padding: 32px;
      margin-bottom: 35px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.03);
      border: 1px solid var(--border-color);
      scroll-margin-top: 80px;
      transition: box-shadow 0.3s ease;
    }

    .section-card:hover {
      box-shadow: 0 6px 25px rgba(0,0,0,0.06);
    }

    h1 {
      color: var(--primary-color);
      font-size: 20px;
      font-weight: 600;
      margin-top: 0;
      margin-bottom: 20px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    h1::before {
      content: '';
      display: inline-block;
      width: 4px;
      height: 20px;
      background: var(--secondary-color);
      border-radius: 2px;
    }

    h2 {
      color: var(--secondary-color);
      font-size: 16px;
      font-weight: 600;
      margin-top: 25px;
      margin-bottom: 12px;
      letter-spacing: 0.02em;
    }

    /* 表格樣式 */
    table {
      width: 100%;
      border-collapse: separate;
      border-spacing: 0;
      margin: 20px 0;
      border-radius: 10px;
      overflow: hidden;
      border: 1px solid var(--border-color);
    }

    th, td {
      padding: 14px 18px;
      text-align: left;
      font-size: 14px;
    }

    th {
      background-color: #f4f1ea;
      color: var(--primary-color);
      font-weight: 600;
      border-bottom: 1px solid var(--border-color);
    }

    td {
      border-bottom: 1px solid var(--border-color);
      color: var(--text-main);
    }

    tr:last-child td {
      border-bottom: none;
    }

    tr:nth-child(even) td {
      background-color: #faf9f6;
    }

    /* 清單樣式 */
    ul {
      padding-left: 0;
      list-style: none;
      margin: 0;
    }

    li {
      position: relative;
      padding-left: 20px;
      margin-bottom: 10px;
      font-size: 14px;
      color: var(--text-main);
    }

    li::before {
      content: '•';
      position: absolute;
      left: 0;
      color: var(--secondary-color);
      font-size: 18px;
      line-height: 1;
      top: 2px;
    }

    .grid-list {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 12px;
      padding: 0;
    }

    .grid-list li {
      background: #faf9f6;
      padding: 10px 14px 10px 32px;
      border-radius: 8px;
      border: 1px solid var(--border-color);
      margin-bottom: 0;
    }

    .grid-list li::before {
      left: 14px;
      top: 10px;
    }

    /* 連結風格 */
    a {
      color: var(--primary-color);
      text-decoration: none;
      border-bottom: 1px solid var(--accent-color);
      transition: all 0.2s ease;
      font-weight: 500;
    }

    a:hover {
      color: var(--secondary-color);
      border-bottom-color: var(--secondary-color);
    }

    /* 標籤 */
    .smoke-tag {
      color: var(--smoke-text);
      font-weight: 500;
      font-size: 12px;
      background: var(--smoke-bg);
      padding: 2px 8px;
      border-radius: 12px;
      margin-left: 6px;
      display: inline-block;
    }

    .highlight-tag {
      background: #eef4f8;
      color: #2970a6;
      font-size: 12px;
      padding: 2px 8px;
      border-radius: 12px;
      font-weight: 500;
    }

    /* 圖片容器 */
    .event-img-container {
      margin-top: 20px;
      text-align: center;
    }

    .event-img {
      max-width: 100%;
      max-height: 750px;
      height: auto;
      border-radius: 12px;
      box-shadow: 0 8px 25px rgba(0,0,0,0.08);
      border: 1px solid var(--border-color);
    }

    /* 溫馨提示框 */
    .alert-box {
      background: #fdfbf7;
      border-left: 3px solid var(--secondary-color);
      padding: 16px 20px;
      border-radius: 0 10px 10px 0;
      margin-top: 20px;
      font-size: 14px;
      color: #61513e;
    }
  </style>
</head>
<body>

  <!-- 頂部導覽列 -->
  <div class="nav-container">
    <a href="#section-1" class="tab-btn">1. 行李與預約</a>
    <a href="#section-2" class="tab-btn">2. 住宿附近資訊</a>
    <a href="#section-3" class="tab-btn">3. 9/10 (四)</a>
    <a href="#section-4" class="tab-btn">4. 9/11 (五)</a>
    <a href="#section-5" class="tab-btn">5. 9/12 (六)</a>
    <a href="#section-6" class="tab-btn">6. 9/13 (日)</a>
    <a href="#section-7" class="tab-btn">7. 9/14 (一)</a>
    <a href="#section-8" class="tab-btn">8. 9/15 (二)</a>
  </div>

  <div class="container">
    
    <div class="page-header">
      <div class="page-title-en">Kansai Travel Itinerary</div>
      <h1 class="page-title" style="justify-content: center;">2026 大阪 6 天 5 夜自由行</h1>
    </div>

    <!-- 航班資訊概覽 -->
    <div class="flight-card">
      <h2>FLIGHT INFORMATION ✈️</h2>
      <p><strong>旅遊日期：</strong> 2026/09/10 – 2026/09/15</p>
      <p><strong>🛫 去程：</strong> 9/10 (四) 虎航 IT210 ｜ 06:40 桃園起飛 → 10:25 抵達關西</p>
      <p><strong>🛬 回程：</strong> 9/15 (二) 捷星 GK57 ｜ 23:35 關西起飛 → 01:30 抵達桃園[cite: 1]</p>
    </div>

    <!-- 1. 行李與預約準備 -->
    <div id="section-1" class="section-card">
      <h1>1. 行李準備與重要預約</h1>
      
      <h2>重要票券與服務預約</h2>
      <ul class="grid-list">
        <li><strong>機場接送預約</strong>（去程 03:50）</li>
        <li><strong>環球影城門票</strong></li>
        <li><strong>USJ 快速通關券</strong></li>
        <li><strong>VJW 填寫完畢</strong> (Visit Japan)</li>
        <li><strong>eSIM 開通確認</strong></li>
        <li><strong>西瓜卡 / IC 儲值</strong></li>
      </ul>

      <h2>隨身與托運行李</h2>
      <ul class="grid-list">
        <li>護照正本</li>
        <li>日幣現金</li>
        <li><strong>一般打火機</strong><br><small style="color:var(--text-muted);">（隨身限帶1個，不可託運）</small></li>
        <li>隱形眼鏡</li>
        <li>刮鬍刀</li>
        <li>手環 / 飾品</li>
        <li>充電線 / 充電器 / 行線</li>
        <li>相機 / 底片</li>
        <li>提醒 GG 專輯</li>
      </ul>
    </div>

    <!-- 2. 住宿附近資訊 -->
    <div id="section-2" class="section-card">
      <h1>2. 住宿附近資訊</h1>
      <p><strong>🏨 住宿飯店：</strong> <a href="https://maps.app.goo.gl/Ps6VMHA6K9UKRSUQ6" target="_blank">Hotel Forza Osaka Kitahama</a></p>

      <h2>附近超商與超市</h2>
      <ul>
        <li>全家 FamilyMart：<a href="https://maps.app.goo.gl/9ZPVvmAvhKohBCfp9" target="_blank">分店 1</a>｜<a href="https://maps.app.goo.gl/ryTLE4RkSKCupa9AA" target="_blank">分店 2</a></li>
        <li>7-Eleven：<a href="https://maps.app.goo.gl/7Euqv4h5Q9P8xuUb6" target="_blank">分店 1</a>｜<a href="https://maps.app.goo.gl/GYe3DBhTxHkprFGCA" target="_blank">分店 2</a></li>
        <li>Lawson：<a href="https://maps.app.goo.gl/PgGFqtdpNeTM4Uod6" target="_blank">分店 1</a>｜<a href="https://maps.app.goo.gl/E5YGyFP9wmE5LpHN7" target="_blank">分店 2</a>｜<a href="https://maps.app.goo.gl/CqLdZspQ3DivkVFNA" target="_blank">分店 3</a></li>
        <li><a href="https://maps.app.goo.gl/79mEWD8W1mp5YTERA" target="_blank">Fresco超市</a>（平日 08:00-23:00 / 假日 10:00-21:00）</li>
      </ul>

      <h2>咖啡與喫茶店</h2>
      <ul>
        <li><a href="https://maps.app.goo.gl/2TWThmrEx1xgbNXt6" target="_blank">珈琲専門店 リヴォリ Rivoli</a>（07:00-17:30 週末休，喫茶）</li>
        <li><a href="https://maps.app.goo.gl/6yfzkRT3n2nPjtWS6" target="_blank">新北浜</a>（07:00-18:00 週末休，喫茶）</li>
        <li><a href="https://maps.app.goo.gl/ka5revLTuZsJUEG48" target="_blank">Lisbon</a>（07:30-14:30 週末休，喫茶）</li>
        <li><a href="https://maps.app.goo.gl/ECkYdM5hKsmzpnC6A" target="_blank">Embankment Coffee</a>（09:00-18:00，河邊現代咖啡）</li>
        <li><a href="https://maps.app.goo.gl/paWGYjHq4upeqH4P8" target="_blank">Brooklyn Roasting Company</a>（08:00-20:00，河邊景觀）</li>
        <li><a href="https://maps.app.goo.gl/RABFa66RLtKLceRG7" target="_blank">SCHOOL BUS COFFEE STOP</a>（10:00-18:00、五至日延長至 23:00）</li>
        <li><a href="https://maps.app.goo.gl/a5mPehnE4xN3K7T6A" target="_blank">SOT COFFEE ROASTER</a>（09:00-17:00，現代精品咖啡）</li>
        <li><a href="https://maps.app.goo.gl/i1LwSahiNhsZT4UC6" target="_blank">Kissa Kojiro</a>（13:00-00:00 週二休，深夜咖啡）</li>
        <li><a href="https://maps.app.goo.gl/CKo8Q9EQtTApXtqy5" target="_blank">Coffee Scarlet</a>（07:00-14:00 週末休，喫茶）</li>
        <li><a href="https://maps.app.goo.gl/BnxiUUa7gRQZ1Wp47" target="_blank">佛蘭</a> <span class="smoke-tag">🚬 可吸菸</span>（07:00-17:00 六日休，喫茶）</li>
        <li><a href="https://maps.app.goo.gl/cx3rPP8oJ1QtYNdo7" target="_blank">HOMER</a> <span class="smoke-tag">🚬 可吸菸</span>（07:30-18:00 六日休，喫茶）</li>
      </ul>

      <h2>餐飲美食</h2>
      <ul>
        <li><a href="https://maps.app.goo.gl/h4DYqQjSzPEdRPTU7" target="_blank">Gokan 五感 本店</a>（10:00-19:00，知名法式甜點蛋糕）</li>
        <li><a href="https://maps.app.goo.gl/u7qZMRj4T8gQnKyN7" target="_blank">Pain Karato</a>（08:00-20:00，精緻麵包與內用早午餐）</li>
        <li><a href="https://maps.app.goo.gl/WXVA5qwEhZrsBExN6" target="_blank">foodscape! BAKERY</a>（08:30-18:00，人氣烘焙麵包）</li>
        <li><a href="https://maps.app.goo.gl/CCAAk6xQM1dg5N766" target="_blank">Bakery torico</a>（07:30-15:00 六日休，麵包）</li>
        <li><a href="https://maps.app.goo.gl/bqupT1HLRGxARuaZ6" target="_blank">Tonkatsu GENYA</a>（11:30-14:00 / 17:30-21:00 週二休，日式豬排）</li>
        <li><a href="https://maps.app.goo.gl/QUFoxopEKXiHNsdUA" target="_blank">燒肉七星</a>（17:00-23:00，燒肉）</li>
        <li><a href="https://maps.app.goo.gl/QUFoxopEKXiHNsdUA" target="_blank">YAKINIKUEN 忍鬨</a>（17:00-00:00，厚切牛舌人氣燒肉）</li>
        <li><a href="https://maps.app.goo.gl/nfZ2Ax7gk1BVTgKJA" target="_blank">Yakiniku Nikudoishi</a>（17:00-00:00，燒肉套餐）</li>
      </ul>

      <h2>宵夜與錢湯</h2>
      <ul>
        <li><a href="https://maps.app.goo.gl/9q3SskA3MNfpzxY38" target="_blank">Mifu</a>（18:00-22:00 週末休，大阪燒）</li>
        <li><a href="https://maps.app.goo.gl/kp9c4SAqeabw5pJx7" target="_blank">Hanamarutei Yodoyabashi</a>（17:00-23:00，大阪燒）</li>
        <li><a href="https://maps.app.goo.gl/ifdif2NFmXyzhJpq9" target="_blank">Nakau なか卯</a>（04:00-03:00，平價定食丼飯）</li>
        <li><a href="https://maps.app.goo.gl/Nnd5zFgj62bQgfM36" target="_blank">中華そば ニカク食堂</a>（營業至 00:30，深夜拉麵）</li>
        <li><a href="https://maps.app.goo.gl/vZw6vfSUhLsBvn7a8" target="_blank">Okonomiyaki ArAkA</a>（17:00-23:00，大阪燒）</li>
        <li><a href="https://maps.app.goo.gl/5V9k9h9kYxK8k6yX7" target="_blank">餃子の王將</a>（11:00-23:30）</li>
        <li><a href="https://maps.app.goo.gl/RBoB21b87btrBT867" target="_blank">紅梅溫泉</a>（14:30-00:00 週六休，傳統錢湯）</li>
        <li><a href="https://maps.app.goo.gl/nCGXM2YDQY8hiDeG9" target="_blank">末廣湯</a>（營業至 01:30 週一休，深夜錢湯）</li>
      </ul>
    </div>

    <!-- 3. 9/10 -->
    <div id="section-3" class="section-card">
      <h1>3. 9/10 (四) 行程：心齋橋、道頓堀、難波</h1>
      <table>
        <thead>
          <tr>
            <th style="width:25%;">時間</th>
            <th>行程規劃</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>03:50</td>
            <td>搭乘預約專車前往桃園機場</td>
          </tr>
          <tr>
            <td>06:40 - 10:25</td>
            <td>搭乘虎航 IT210 前往關西機場</td>
          </tr>
          <tr>
            <td>10:25 - 11:35</td>
            <td>入境手續辦理（預估 11:30 完成）</td>
          </tr>
          <tr>
            <td>11:35 - 12:35</td>
            <td>搭乘南海特急至天下茶屋，轉堺筋線至北濱站</td>
          </tr>
          <tr>
            <td>12:40</td>
            <td>抵達 <a href="https://maps.app.goo.gl/Ps6VMHA6K9UKRSUQ6" target="_blank">Hotel Forza Osaka Kitahama</a> 寄放行李</td>
          </tr>
          <tr>
            <td>13:00 - 14:00</td>
            <td>心齋橋午餐（可選 <a href="https://maps.app.goo.gl/75FaGX4btm5fi3gP8" target="_blank">大起水產</a> 壽司）</td>
          </tr>
          <tr>
            <td>14:00 - 20:00</td>
            <td>心齋橋、道頓堀、美國村、難波逛街與咖啡歇腳</td>
          </tr>
          <tr>
            <td>20:00</td>
            <td>晚餐：壽喜燒 / 燒肉 / 咖哩 / 拉麵選擇</td>
          </tr>
          <tr>
            <td>21:30 - </td>
            <td>彈性安排，可至錢湯放鬆（<a href="https://maps.app.goo.gl/RBoB21b87btrBT867" target="_blank">紅梅溫泉</a> 或 <a href="https://maps.app.goo.gl/nCGXM2YDQY8hiDeG9" target="_blank">末廣湯</a>）</td>
          </tr>
        </tbody>
      </table>

      <h2>心齋橋 / 道頓堀精選店家</h2>
      <ul>
        <li><strong>購物與唱片：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/D6wZdV6TcoXB3ukLA" target="_blank">心齋橋 PARCO</a>｜<a href="https://maps.app.goo.gl/MsaWNN12BAAoN31g7" target="_blank">Orange Street</a></li>
            <li><a href="https://maps.app.goo.gl/sq2BV3XftjJdnrQGA" target="_blank">Revenge record</a>（13:00-20:00，唱片行）</li>
            <li><a href="https://maps.app.goo.gl/7MTauWUr19enyfUW8" target="_blank">King Kong honten</a>（11:00-20:00，二手唱片）</li>
            <li><a href="https://maps.app.goo.gl/KjvQXpHbrrvrjVPW6" target="_blank">Punk and Destroy</a>｜<a href="https://maps.app.goo.gl/P8AfGDk46qbftyE36" target="_blank">Flake Record</a>｜<a href="https://maps.app.goo.gl/jnZWZk95yR12finZ8" target="_blank">Time Bomb</a></li>
          </ul>
        </li>
        <li><strong>咖啡與喫茶：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/eZAskA7YgDxz8joF6" target="_blank">Barista Map Coffee Roasters</a>（11:00-18:00 週一休）</li>
            <li><a href="https://maps.app.goo.gl/rdqxj9v1uiqnt8z4A" target="_blank">Lilo coffee roaster</a>（11:00-23:00）</li>
            <li><a href="https://maps.app.goo.gl/4HKhCYX1hwJpHysx7" target="_blank">The Roasters Coffee Shinsaibashi</a>（09:00-18:30）</li>
            <li><a href="https://maps.app.goo.gl/9k3J8d7L6u2B1Y6t8" target="_blank">Millpour</a>（09:00-18:00）</li>
            <li><a href="https://maps.app.goo.gl/yN1s4k3J8u5B2Y7t9" target="_blank">Mel Coffee Roasters</a>（10:00-18:00 週一休）</li>
            <li><a href="https://maps.app.goo.gl/3k7N8d2M1u4B9Y8t0" target="_blank">Aoma coffee</a>（10:00-17:00）</li>
            <li><a href="https://maps.app.goo.gl/xdnoxgMH7MrCM6TR6" target="_blank">珈琲艇 喫茶</a>（10:00-19:00，復古船型咖啡店）</li>
            <li><a href="https://maps.app.goo.gl/4haRMRpPQ235xzMLA" target="_blank">Lilo Coffee Kissa</a>（11:00-21:00，手沖咖啡喫茶）</li>
          </ul>
        </li>
        <li><strong>美食餐廳：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/5J7k9d2N1u4B9Y8t1" target="_blank">New Light</a>（11:00-19:00，咖喱飯）</li>
            <li><a href="https://maps.app.goo.gl/8K2n3d4M1u5B9Y8t2" target="_blank">すき焼き藤もと</a>（營業至 23:00，壽喜燒）</li>
            <li><a href="https://maps.app.goo.gl/1L3n4d5M2u6B0Y9t3" target="_blank">WAGYU SUKIYAKI 極</a>（10:00-23:00，壽喜燒）</li>
            <li><a href="https://maps.app.goo.gl/4P5n6d7M3u8B1Y0t4" target="_blank">Wagyu Sukiyaki GYUMON</a>（12:00-23:00，壽喜燒）</li>
            <li><a href="https://maps.app.goo.gl/7R8n9d0M4u1B2Y1t5" target="_blank">WAGYU ZANMAI</a>（11:00-00:00，壽喜燒）</li>
            <li><a href="https://maps.app.goo.gl/75FaGX4btm5fi3gP8" target="_blank">大起水產</a>（11:00-22:00，迴轉壽司）</li>
            <li><a href="https://maps.app.goo.gl/0S1n2d3M5u4B3Y2t6" target="_blank">一斗燒肉</a>（17:00-00:00，燒肉）</li>
            <li><a href="https://maps.app.goo.gl/3T4n5d6M7u8B4Y3t7" target="_blank">燒肉 Kurumi</a>（11:30-01:00，燒肉）</li>
            <li><a href="https://maps.app.goo.gl/6U7n8d9M0u1B5Y4t8" target="_blank">黒毛和牛一頭買い焼肉</a>（11:00-01:00，燒肉）</li>
            <li><a href="https://maps.app.goo.gl/9V0n1d2M3u4B6Y5t9" target="_blank">辻田心齋橋</a>（11:00-00:00，拉麵）</li>
          </ul>
        </li>
      </ul>

      <h2>難波 / 日本橋精選店家</h2>
      <ul>
        <li><strong>動漫與唱片購物：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/jiHZ1jUfcy1zBZDY7" target="_blank">安利美特</a>｜<a href="https://maps.app.goo.gl/eRYV6WdpNFb7scKq7" target="_blank">Super Kids Land</a>｜<a href="https://maps.app.goo.gl/KQudTtpJcADq7GUW8" target="_blank">駿河屋</a>｜<a href="https://maps.app.goo.gl/6v7NZCKjWZYKWLPT7" target="_blank">Tower Records</a></li>
            <li><a href="https://maps.app.goo.gl/2W3n4d5M6u7B8Y9t0" target="_blank">Village Vanguard</a>（11:00-21:00）｜<a href="https://maps.app.goo.gl/5X6n7d8M9u0B1Y2t1" target="_blank">Bookoff plus</a>（10:00-22:00）｜<a href="https://maps.app.goo.gl/8Y9n0d1M2u3B4Y5t2" target="_blank">Forever record</a>（12:00-20:00）</li>
          </ul>
        </li>
        <li><strong>咖啡與喫茶：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/1Z2n3d4M5u6B7Y8t3" target="_blank">Oranda</a> <span class="smoke-tag">🚬</span>（08:00-18:00）</li>
            <li><a href="https://maps.app.goo.gl/4A5n6d7M8u9B0Y1t4" target="_blank">Coffee Adria</a> <span class="smoke-tag">🚬</span>（08:00-18:00）</li>
            <li><a href="https://maps.app.goo.gl/7B8n9d0M1u2B3Y4t5" target="_blank">Shemowa Cafe</a> <span class="smoke-tag">🚬</span>（12:00-22:00）</li>
            <li><a href="https://maps.app.goo.gl/0C1n2d3M4u5B6Y7t6" target="_blank">Asuka</a>（07:30-17:00）｜<a href="https://maps.app.goo.gl/3D4n5d6M7u8B9Y0t7" target="_blank">American</a>（11:00-21:45）｜<a href="https://maps.app.goo.gl/6E7n8d9M0u1B2Y3t8" target="_blank">Arabiya coffee</a>（12:00-18:00）</li>
          </ul>
        </li>
        <li><strong>美食餐廳：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/9F0n1d2M3u4B5Y6t9" target="_blank">Kusaka Curry</a>（11:30-15:00 / 17:00-21:00，咖喱）</li>
            <li><a href="https://maps.app.goo.gl/2G3n4d5M6u7B8Y9t0" target="_blank">Okonomiyaki AT THE 21</a>（大阪燒）</li>
            <li><a href="https://maps.app.goo.gl/7bLxdLbunkb7UUQY9" target="_blank">焼鳥と鰻 蜂谷</a>（11:30-04:00，鰻魚與燒鳥）</li>
            <li><a href="https://maps.app.goo.gl/5H6n7d8M9u0B1Y2t1" target="_blank">大衆すき焼き 北斗</a>（壽喜燒）</li>
            <li><a href="https://maps.app.goo.gl/75FaGX4btm5fi3gP8" target="_blank">大起水產</a>（11:00-22:00）｜<a href="https://maps.app.goo.gl/8I9n0d1M2u3B4Y5t2" target="_blank">迴轉壽司長次郎</a></li>
            <li><a href="https://maps.app.goo.gl/1J2n3d4M5u6B7Y8t3" target="_blank">中華そばふじい</a>（11:00-02:30）｜<a href="https://maps.app.goo.gl/pzssUTwezrGrrFKo6" target="_blank">味乃家御好燒</a>（11:00-22:00 週一休）</li>
            <li><a href="https://maps.app.goo.gl/4K5n6d7M8u9B0Y1t4" target="_blank">自由軒</a>（11:00-19:35 週一休）｜<a href="https://maps.app.goo.gl/39iYAgGNzt9t8CJr7" target="_blank">燒肉力丸</a>（11:30-01:00）</li>
          </ul>
        </li>
      </ul>
    </div>

    <!-- 4. 9/11 -->
    <div id="section-4" class="section-card">
      <h1>4. 9/11 (五) 行程：谷町四丁目、中崎町、梅田</h1>
      <table>
        <thead>
          <tr>
            <th style="width:25%;">時間</th>
            <th>行程規劃</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>10:00</td>
            <td>飯店樓下買蛋糕，附近散步或喫茶店休息</td>
          </tr>
          <tr>
            <td>11:30 / 12:00</td>
            <td>谷町四丁目享用 Pizza：<a href="https://maps.app.goo.gl/7VnUDac9327onAz37" target="_blank">Henry’s Pizza</a>（11:30-22:00）或 <a href="https://maps.app.goo.gl/a5mPehnE4xN3K7T6A" target="_blank">SOT Coffee</a>（09:00-17:00）</td>
          </tr>
          <tr>
            <td>13:00 - 15:30</td>
            <td>中崎町文青散步：<br>
              <a href="https://maps.app.goo.gl/tG6xUKmuErfDCjr16" target="_blank">太陽ノ塔洋菓子店</a>（10:00-20:00）｜
              <a href="https://maps.app.goo.gl/caSK2ewVjTkE9mYaA" target="_blank">うてな喫茶店</a>（12:00-19:00）｜
              <a href="https://maps.app.goo.gl/s3yyMBJFUCf2Bkiu5" target="_blank">green pepe 復古選物</a>（12:00-19:00 週二三休）｜
              <a href="https://maps.app.goo.gl/jfNTkmjC5uaxynVP7" target="_blank">Yama Store</a>（13:00-19:00 週三四休）｜
              <a href="https://maps.app.goo.gl/7L8n9d0M1u2B3Y4t5" target="_blank">PAUHANA COFFEE ROASTERS</a>（11:00-18:00 週二休）
            </td>
          </tr>
          <tr>
            <td>15:30 - 19:00</td>
            <td>梅田區購物：<a href="https://maps.app.goo.gl/xYwzmx5yq25PW75p9" target="_blank">LUCUA</a>（10:30-20:30）｜<a href="https://maps.app.goo.gl/qv2rEwe7pvhakffx6" target="_blank">Tower Records</a>（11:00-21:00）｜<a href="https://maps.app.goo.gl/iqX17dPaYkdNNCJ38" target="_blank">梅田藍天大廈</a>（09:30-22:30）</td>
          </tr>
          <tr>
            <td>17:30 / 19:00</td>
            <td>
              <strong>分流支線：</strong><br>
              ・<strong>支線一：</strong>17:30 前往 <a href="https://maps.app.goo.gl/KDsfAaVLRdQeosKa8" target="_blank">Yogibo META VALLEY</a> 看表演，21:30 結束會合吃宵夜<br>
              ・<strong>支線二：</strong>19:00 / 19:30 享用生日大餐，結束後可再逛街或泡錢湯
            </td>
          </tr>
        </tbody>
      </table>

      <h2>梅田咖啡與美食清單</h2>
      <ul>
        <li><a href="https://maps.app.goo.gl/0M1n2d3M4u5B6Y7t8" target="_blank">Mel 咖啡</a>（11:00-22:00）</li>
        <li><a href="https://maps.app.goo.gl/3N4n5d6M7u8B9Y0t9" target="_blank">Madura</a> <span class="smoke-tag">🚬</span>（07:00-21:00，昭和風地下街喫茶店）</li>
        <li><a href="https://maps.app.goo.gl/ynx4yNveBGCPWkuq5" target="_blank">New YC 喫茶</a>（07:00-22:00）｜<a href="https://maps.app.goo.gl/KGZZQkRADSNauSxv6" target="_blank">YC 喫茶</a>（07:00-22:00）</li>
        <li><a href="https://maps.app.goo.gl/DRMZn8Gs1PRrEits8" target="_blank">Arisa 喫茶</a>（08:00-18:00）｜<a href="https://maps.app.goo.gl/T6uNzYAyVTsXbAx19" target="_blank">函太郎迴轉壽司</a>（11:00-22:00）</li>
      </ul>
    </div>

    <!-- 5. 9/12 -->
    <div id="section-5" class="section-card">
      <h1>5. 9/12 (六) 行程：ONE & ONLY FESTIVAL 2026 (Day 1)</h1>
      <table>
        <thead>
          <tr>
            <th style="width:25%;">時間</th>
            <th>行程規劃</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>08:20</td>
            <td>早餐時間：<br>
              <a href="https://maps.app.goo.gl/u7qZMRj4T8gQnKyN7" target="_blank">Pain Karato</a>（08:00-20:00）｜
              <a href="https://maps.app.goo.gl/WXVA5qwEhZrsBExN6" target="_blank">foodscape! BAKERY</a>（08:30-18:00）｜
              <a href="https://maps.app.goo.gl/BnxiUUa7gRQZ1Wp47" target="_blank">佛蘭</a> <span class="smoke-tag">🚬 六日休</span>（07:00-17:00）｜
              <a href="https://maps.app.goo.gl/6O7n8d9M0u1B2Y3t0" target="_blank">白馬</a> <span class="smoke-tag">日休</span>（07:00-18:00）｜
              <a href="https://maps.app.goo.gl/aPzH8nsdFqnwQg356" target="_blank">9 Borden Coffee</a>（08:00-18:00）
            </td>
          </tr>
          <tr>
            <td>09:45 / 10:30</td>
            <td>抵達音樂祭會場（09:45 開場 / 10:30 開演，約 19:40 終演）</td>
          </tr>
          <tr>
            <td>19:40 後</td>
            <td>音樂祭結束，會合吃宵夜（已知 TIVE 時間可衝）</td>
          </tr>
        </tbody>
      </table>

      <h2>🖼️ 9/12 (DAY 1) 音樂祭時間表</h2>
      <div class="event-img-container">
        <img src="S__124993544_0.jpg" alt="ONE & ONLY FESTIVAL 2026 Day 1 Timetable" class="event-img">
      </div>
    </div>

    <!-- 6. 9/13 -->
    <div id="section-6" class="section-card">
      <h1>6. 9/13 (日) 行程：ONE & ONLY FESTIVAL 2026 (Day 2) & 燒肉宵夜</h1>
      <table>
        <thead>
          <tr>
            <th style="width:25%;">時間</th>
            <th>行程規劃</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>08:20</td>
            <td>早餐時間：<br>
              <a href="https://maps.app.goo.gl/u7qZMRj4T8gQnKyN7" target="_blank">Pain Karato</a>（08:00-20:00）｜
              <a href="https://maps.app.goo.gl/WXVA5qwEhZrsBExN6" target="_blank">foodscape! BAKERY</a>（08:30-18:00）｜
              <a href="https://maps.app.goo.gl/aPzH8nsdFqnwQg356" target="_blank">9 Borden Coffee</a>（08:00-18:00）｜
              <a href="https://maps.app.goo.gl/9P0n1d2M3u4B5Y6t1" target="_blank">Roman</a> <span class="smoke-tag">六休</span>（07:30-17:00）｜
              <a href="https://maps.app.goo.gl/cx3rPP8oJ1QtYNdo7" target="_blank">Coffee shop homer</a> <span class="smoke-tag">🚬</span>（07:30-21:00）
            </td>
          </tr>
          <tr>
            <td>09:45 / 10:30</td>
            <td>抵達音樂祭會場（09:45 開場 / 10:30 開演，約 19:35 終演）</td>
          </tr>
          <tr>
            <td>19:35 後</td>
            <td>慶功燒肉或宵夜，時間充裕可泡錢湯舒緩腳力</td>
          </tr>
        </tbody>
      </table>

      <h2>🖼️ 9/13 (DAY 2) 音樂祭時間表</h2>
      <div class="event-img-container">
        <img src="S__124993545_0.jpg" alt="ONE & ONLY FESTIVAL 2026 Day 2 Timetable" class="event-img">
      </div>
    </div>

    <!-- 7. 9/14 -->
    <div id="section-7" class="section-card">
      <h1>7. 9/14 (一) 行程：日本環球影城 (USJ)</h1>
      <table>
        <thead>
          <tr>
            <th style="width:25%;">時間</th>
            <th>行程規劃</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>08:00</td>
            <td>享用早餐並準備出發（確認帶齊 <span class="highlight-tag">USJ門票</span> 與 <span class="highlight-tag">快速通關券</span>）</td>
          </tr>
          <tr>
            <td>09:30 - 21:30</td>
            <td>全天暢玩 <a href="https://maps.app.goo.gl/24GMzTAxibqk4i9c7" target="_blank">日本環球影城 (USJ)</a></td>
          </tr>
          <tr>
            <td>21:30 結束</td>
            <td>返回市區享用燒肉/宵夜，泡錢湯舒緩身心</td>
          </tr>
        </tbody>
      </table>
    </div>

    <!-- 8. 9/15 -->
    <div id="section-8" class="section-card">
      <h1>8. 9/15 (二) 行程：最後一日 (三支線可選)</h1>
      <p><strong>11:00 退房</strong> 寄放行李後自由活動，依選擇的支線展開：</p>

      <h2>🔀 支線一：慶生餐 & 天王寺/通天閣區</h2>
      <ul>
        <li>12:30 吃慶生餐（如 9/11 未吃）</li>
        <li>14:00 天神橋 / <a href="https://maps.app.goo.gl/C5xRx8cNvjUdkzSM7" target="_blank">南森町</a> / <a href="https://maps.app.goo.gl/V3ZQ28uHrtMh333WA" target="_blank">COBATO 鐵盒餅乾</a>（10:00-17:00，外帶餅乾店）</li>
        <li><strong>觀光景點：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/tcQyriaJfZokgBum8" target="_blank">Harukas 300 展望台</a>（天王寺 09:00-22:00）｜<a href="https://maps.app.goo.gl/EfKvseqpSqmQU2px5" target="_blank">通天閣</a>（09:30-20:00）</li>
          </ul>
        </li>
        <li><strong>特色喫茶店：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/2Q3n4d5M6u7B8Y9t2" target="_blank">New World</a> <span class="smoke-tag">🚬</span>（08:00-15:00）｜<a href="https://maps.app.goo.gl/5R6n7d8M9u0B1Y2t3" target="_blank">喫茶Doremi</a> <span class="smoke-tag">🚬 週一休</span>（10:00-18:00）</li>
            <li><a href="https://maps.app.goo.gl/8S9n0d1M2u3B4Y5t4" target="_blank">喫茶通天閣</a>（08:00-18:00）｜<a href="https://maps.app.goo.gl/1T2n3d4M5u6B7Y8t5" target="_blank">咖啡專科</a>（07:00-17:00 週四休）｜<a href="https://maps.app.goo.gl/4U5n6d7M8u9B0Y1t6" target="_blank">Kissa Garo</a> <span class="smoke-tag">🚬</span>（07:00-17:30）</li>
          </ul>
        </li>
        <li><strong>美食串炸與大阪燒：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/7V8n9d0M1u2B3Y4t7" target="_blank">Kitanoya 北野屋</a>（11:30-22:00 週一休）｜<a href="https://maps.app.goo.gl/0W1n2d3M4u5B6Y7t8" target="_blank">大阪燒千歲</a></li>
            <li><a href="https://maps.app.goo.gl/3X4n5d6M7u8B9Y0t9" target="_blank">Usagiya</a>（12:00-20:00 週一四休）｜<a href="https://maps.app.goo.gl/6Y7n8d9M0u1B2Y3t0" target="_blank">Taisei</a></li>
          </ul>
        </li>
      </ul>

      <h2>🔀 支線二：中之島 / 北新地 / 東梅田藝術散策</h2>
      <ul>
        <li><strong>景點與散策：</strong><a href="https://maps.app.goo.gl/pRvwSDrRSAE1waq29" target="_blank">中之島美術館</a>（10:00-17:00 週一休）｜<a href="https://maps.app.goo.gl/bhVTi5mMVpoK7sJ9A" target="_blank">中之島公園</a>｜<a href="https://maps.app.goo.gl/9Z0n1d2M3u4B5Y6t1" target="_blank">青春末世天橋</a>｜<a href="https://maps.app.goo.gl/2A3n4d5M6u7B8Y9t2" target="_blank">WoWus</a>（08:00-21:00）</li>
        <li><strong>咖啡與麵包：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/5ZGW9AFrgc7MEtzVA" target="_blank">Glitch 咖啡</a>（08:00-19:00 週四休）｜<a href="https://maps.app.goo.gl/5B6n7d8M9u0B1Y2t3" target="_blank">White bird 咖啡</a>（11:00-23:00）</li>
            <li><a href="https://maps.app.goo.gl/3N4n5d6M7u8B9Y0t9" target="_blank">Madura</a> <span class="smoke-tag">🚬</span>（09:00-20:30）｜<a href="https://maps.app.goo.gl/8C9n0d1M2u3B4Y5t4" target="_blank">Mahoroba Nighttime Bakery</a>（17:00-03:00 週日休）</li>
          </ul>
        </li>
        <li><strong>美食：</strong><a href="https://maps.app.goo.gl/1D2n3d4M5u6B7Y8t5" target="_blank">武士道 燒肉</a>（營業至 00:00，下午休息）</li>
      </ul>

      <h2>🔀 支線三：神戶半日遊</h2>
      <ul>
        <li>12:00 前往神戶，逛至 18:00 返回市區（車程約 40 分鐘）</li>
        <li><strong>景點與商圈：</strong><a href="https://maps.app.goo.gl/r3WbRypcP9r7mJgz5" target="_blank">神戶舊居留地</a>｜<a href="https://maps.app.goo.gl/Hu2yLqc3YisD6XBt8" target="_blank">神戶北野異人館</a>｜<a href="https://maps.app.goo.gl/4E5n6d7M8u9B0Y1t6" target="_blank">神戶三宮中心街</a></li>
        <li><strong>咖啡與喫茶：</strong>
          <ul>
            <li><a href="https://maps.app.goo.gl/gjwV4tEdtSVeppcH7" target="_blank">にしむら珈琲店 中山手本店</a>（08:30-22:00，老派經典喫茶）</li>
            <li><a href="https://maps.app.goo.gl/7F8n9d0M1u2B3Y4t7" target="_blank">Bivere 咖啡</a>（13:00-18:00）｜<a href="https://maps.app.goo.gl/0G1n2d3M4u5B6Y7t8" target="_blank">Taoka Coffee</a>（10:00-19:00）</li>
          </ul>
        </li>
      </ul>

      <div class="alert-box">
        <strong>⚠️ 返程提醒：</strong>最晚 19:30 準備回飯店拿行李，<strong>最晚 20:20 搭車前往關西機場</strong>，準備搭乘 23:35 捷星 GK57 班機返台[cite: 1]！
      </div>
    </div>

  </div>

</body>
</html>
