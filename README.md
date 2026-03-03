<html lang="te">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Baby Reveal</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            overflow: hidden;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f0f8ff;
        }

        /* Curtain Styling */
        .curtain-container {
            position: fixed;
            width: 100%;
            height: 100%;
            display: flex;
            z-index: 10;
        }

        .curtain {
            width: 50%;
            height: 100%;
            background-color: #800000; /* Deep Red Curtain Color */
            transition: transform 1.5s ease-in-out;
            position: relative;
        }

        .left { border-right: 2px solid #ffd700; }
        .right { border-left: 2px solid #ffd700; }

        /* The Button */
        #revealBtn {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 120px;
            height: 120px;
            border-radius: 50%;
            border: 5px solid #ffd700;
            background: radial-gradient(circle, #ffffff, #e0e0e0);
            font-weight: bold;
            cursor: pointer;
            z-index: 20;
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
            transition: 0.3s;
        }

        #revealBtn:hover { transform: translate(-50%, -50%) scale(1.1); }

        /* Revealed Content */
        .content {
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(180deg, #e0f2fe 0%, #ffffff 100%);
        }

        .baby-announcement {
            opacity: 0;
            transform: scale(0.8);
            transition: 1s ease-out 1.2s; /* Delayed until curtains open */
        }

        .telugu-text {
            font-size: 3rem;
            color: #1e40af;
            margin-bottom: 20px;
            font-weight: bold;
        }

        .english-text {
            font-size: 1.5rem;
            color: #3b82f6;
        }

        /* Animation Classes */
        .open-left { transform: translateX(-100%); }
        .open-right { transform: translateX(100%); }
        .show-content { opacity: 1; transform: scale(1); }
        .fade-out { opacity: 0; pointer-events: none; transition: 0.5s; }

    </style>
</head>
<body>

    <button id="revealBtn">PRESS TO<br>REVEAL</button>

    <div class="curtain-container" id="curtainWrapper">
        <div class="curtain left" id="lCurtain"></div>
        <div class="curtain right" id="rCurtain"></div>
    </div>

    <div class="content">
        <div class="baby-announcement" id="babyInfo">
            <h1 class="telugu-text">మా కన్నయ్య కి స్వాగతం</h1>
            <h2 class="english-text">It's a Baby Boy! 💙</h2>
            <div style="font-size: 80px;">👶🏻🍼</div>
        </div>
    </div>

    <script>
        const btn = document.getElementById('revealBtn');
        const lCurtain = document.getElementById('lCurtain');
        const rCurtain = document.getElementById('rCurtain');
        const babyInfo = document.getElementById('babyInfo');

        btn.addEventListener('click', () => {
            // Hide the button
            btn.classList.add('fade-out');
            
            // Open curtains
            lCurtain.classList.add('open-left');
            rCurtain.classList.add('open-right');
            
            // Show the baby announcement
            babyInfo.classList.add('show-content');
        });
    </script>
</body>
</html>
