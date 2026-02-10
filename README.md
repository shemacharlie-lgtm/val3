<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Baby Raïssa ❤️</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Fredoka+One&family=Gaegu:wght@400;700&display=swap');

        body {
            background-color: #fff2e6;
            background-image: radial-gradient(#ffb3c1 0.5px, transparent 0.5px);
            background-size: 20px 20px;
            font-family: 'Fredoka One', cursive;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            overflow-x: hidden;
        }

        .container { text-align: center; max-width: 800px; padding: 20px; }

        h1 {
            color: #ff4d8d;
            font-size: clamp(2.5rem, 8vw, 4rem);
            margin-bottom: 20px;
            text-shadow: 2px 2px #fff;
        }

        /* Initial UI */
        .main-ui { display: flex; flex-direction: column; align-items: center; gap: 30px; }
        .btn-box { display: flex; gap: 20px; align-items: center; justify-content: center; min-height: 200px; }
        
        button {
            padding: 15px 40px;
            font-size: 1.5rem;
            border: none;
            border-radius: 100px;
            cursor: pointer;
            font-family: 'Fredoka One', cursive;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        #noBtn { background-color: #ff85a2; color: white; }
        #yesBtn { background-color: #ff4d8d; color: white; position: relative; }

        /* Success & Letter Style */
        #success { display: none; flex-direction: column; align-items: center; animation: fadeIn 1s ease; }
        
        .envelope {
            width: 150px;
            height: 100px;
            background-color: #ff85a2;
            position: relative;
            cursor: pointer;
            margin: 20px auto;
            border-radius: 0 0 5px 5px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        .envelope::after {
            content: "";
            position: absolute;
            top: 0; left: 0;
            border-left: 75px solid transparent;
            border-right: 75px solid transparent;
            border-top: 60px solid #ff4d8d;
        }

        .letter-box {
            display: none;
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(255, 77, 141, 0.2);
            max-width: 450px;
            font-family: 'Gaegu', cursive;
            font-size: 1.6rem;
            color: #444;
            line-height: 1.4;
            text-align: left;
            border: 2px dashed #ffb3c1;
            animation: slideUp 0.8s ease;
        }

        #message-list { color: #d63384; font-size: 1.2rem; height: 50px; }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes slideUp { from { transform: translateY(50px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
    </style>
</head>
<body>

    <div id="content" class="container">
        <h1>Baby Raïssa <br> will you be my Valentine?</h1>
        <div class="main-ui">
            <div id="message-list"></div>
            <div class="btn-box">
                <button id="noBtn">NO</button>
                <button id="yesBtn">YES</button>
            </div>
        </div>
    </div>

    <div id="success" class="container">
        <h1 style="font-size: 2rem;">thank you for being my valentine, i love u so much ❤️</h1>
        <p style="color: #ff4d8d;">Click the envelope to read your letter 📩</p>
        
        <div class="envelope" id="envelope"></div>

        <div class="letter-box" id="letter">
            My Love Raïssa,<br><br>
            I wanna tell you how much I really appreciate and admire the way you carry yourself, the warmth you bring in my life without even trying and mostly the way your smile stays with me longer than it should.<br><br>
            Baby you brought something in my life that I didn’t know I was missing. Be my valentine for now and forever, I love you ❤️<br><br>
            Forever yours,<br>
            Charlie
        </div>
    </div>

    <script>
        const yesBtn = document.getElementById('yesBtn');
        const noBtn = document.getElementById('noBtn');
        const messageList = document.getElementById('message-list');
        const content = document.getElementById('content');
        const success = document.getElementById('success');
        const envelope = document.getElementById('envelope');
        const letter = document.getElementById('letter');

        let yesScale = 1;
        let messageIndex = 0;
        const guiltMessages = [
            "are you sure?😏", 
            "you hate me and want me to die?😩", 
            "Say yes please?🙂", 
            "Clicked No? Wow!!!! 😩", 
            "baby pleaseee? 🤗"
        ];

        noBtn.addEventListener('click', () => {
            yesScale += 0.6;
            yesBtn.style.transform = `scale(${yesScale})`;
            if (messageIndex < guiltMessages.length) {
                messageList.innerText = guiltMessages[messageIndex];
                messageIndex++;
            }
        });

        yesBtn.addEventListener('click', () => {
            content.style.display = 'none';
            success.style.display = 'flex';
        });

        envelope.addEventListener('click', () => {
            envelope.style.display = 'none';
            letter.style.display = 'block';
        });
    </script>
</body>
</html>
