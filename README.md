<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>💌 时空浪漫存折</title>
    <style>
        :root {
            --bg: linear-gradient(135deg, #7b4397 0%, #dc2430 100%);
            --card-bg: rgba(255,255,255,0.15);
        }
        body {
            margin: 0;
            padding: 20px;
            min-height: 100vh;
            background: var(--bg);
            font-family: 'Segoe UI', sans-serif;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
        }
        .card {
            width: 300px;
            height: 180px;
            background: var(--card-bg);
            backdrop-filter: blur(5px);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
            border: 1px solid rgba(255,255,255,0.2);
            cursor: pointer;
            transition: transform 0.3s;
            position: relative;
            overflow: hidden;
        }
        .card:hover {
            transform: translateY(-5px);
        }
        .card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1));
            transform: rotate(45deg);
        }
        h2 {
            color: #ffd3e0;
            margin: 0 0 10px;
            font-size: 1.3em;
            text-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }
        p {
            color: rgba(255,255,255,0.9);
            font-size: 0.9em;
            line-height: 1.4;
            margin: 0;
        }
        .heart {
            position: absolute;
            opacity: 0.1;
            pointer-events: none;
        }
        /* 点击特效 */
        .card.active {
            animation: heartbeat 0.8s;
        }
        @keyframes heartbeat {
            0% { transform: scale(1); }
            15% { transform: scale(1.1); }
            30% { transform: scale(0.95); }
            45% { transform: scale(1.05); }
            60% { transform: scale(0.98); }
            75% { transform: scale(1.02); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body>
    <!-- 卡片模板 -->
    <div class="card" onclick="this.classList.toggle('active')">
        <h2>🍜 任性美食通行证</h2>
        <p>凌晨三点突然想吃火锅？本券可召唤穿睡衣陪你煮泡面的骑士</p>
    </div>

    <div class="card" onclick="this.classList.toggle('active')">
        <h2>🛡️ 反悔豁免权</h2>
        <p>当你搞砸事情时使用，可获得无理由背锅侠一名（附赠摸头安慰服务）</p>
    </div>

    <div class="card" onclick="this.classList.toggle('active')">
        <h2>👵 退休生活体验日</h2>
        <p>提前预演80岁生活：推轮椅逛公园，用保温杯喝奶茶吐槽年轻人</p>
    </div>

    <div class="card" onclick="this.classList.toggle('active')">
        <h2>🦸 超能力租赁服务</h2>
        <p>任选：找钥匙/送文件/猜餐厅（每日限用1次，能力随机刷新）</p>
    </div>

    <div class="card" onclick="this.classList.toggle('active')">
        <h2>🌍 世界任意角落奔向你</h2>
        <p>勾选地球仪坐标，72小时内必带着你最爱的零食闪现</p>
    </div>

    <div class="card" onclick="this.classList.toggle('active')">
        <h2>🎧 感官共享实验</h2>
        <p>盲选我的歌单/相册/备忘录，同步心率与脑内弹幕</p>
    </div>

    <div class="card" onclick="this.classList.add('active'); setTimeout(()=>this.classList.remove('active'),2000)">
        <h2>✍️ 空白契约书</h2>
        <p>长按此卡3秒，说出你的愿望——<br>「遵命，我的公主殿下」</p>
    </div>

    <script>
        // 随机生成漂浮爱心
        function createHearts() {
            const colors = ['#ff7eb6', '#ff65a3', '#7afcff'];
            for(let i=0; i<20; i++) {
                const heart = document.createElement('div');
                heart.className = 'heart';
                heart.innerHTML = '❤';
                heart.style.left = Math.random()*100 + 'vw';
                heart.style.animation = `float ${5+Math.random()*10}s infinite`;
                heart.style.color = colors[Math.floor(Math.random()*3)];
                document.body.appendChild(heart);
            }
        }
        createHearts();
    </script>
</body>
</html>
