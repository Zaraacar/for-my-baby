# for-my-baby
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine's Special</title>
    <style>
        body {
            text-align: center;
            font-family: 'Arial', sans-serif;
            background-color: #fbe9e7;
            color: black;
            padding-top: 50px;
        }
        h1 {
            font-size: 50px;
        }
        .question {
            font-size: 30px;
            margin-top: 20px;
        }
        .button {
            font-size: 20px;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            background-color: pink;
        }
        #response {
            font-size: 30px;
            margin-top: 20px;
        }
        #emojiContainer {
            font-size: 40px;
            display: none;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        .emoji {
            position: absolute;
            animation: flyEmojis 2s forwards;
        }
        @keyframes flyEmojis {
            0% { transform: translate(0, 0); opacity: 1; }
            100% { transform: translate(-100px, -300px); opacity: 0; }
        }
        #music {
            display: none;
        }
    </style>
</head>
<body>

    <!-- Start of the conversation -->
    <h1>Hiiii babyyyy</h1>
    <div id="question1" class="question">
        <button class="button" onclick="nextQuestion(1)">Weiter</button>
    </div>

    <!-- 1st Question: Valentine -->
    <div id="question2" class="question" style="display:none;">
        Ich weiß nicht, ob du was von Valentinstag hältst, aber trotzdem.
        <br>
        <button class="button" onclick="nextQuestion(2)">Weiter</button>
    </div>

    <!-- 2nd Question: Do you love me -->
    <div id="question3" class="question" style="display:none;">
        Do you love me?
        <br>
        <button class="button" onclick="answerLove('yes')">Ja</button>
        <button class="button" onclick="answerLove('no')">Nein</button>
    </div>

    <div id="response3" class="question" style="display:none;"></div>

    <!-- 3rd Question: Can you touch me -->
    <div id="question4" class="question" style="display:none;">
        Can you touch me?!
        <br>
        <button class="button" onclick="nextQuestion(4)">Yes please</button>
        <button class="button" onclick="nextQuestion(4)">Yes mommy</button>
        <button class="button" onclick="nextQuestion(4)">Yes mommy</button>
        <button class="button" onclick="nextQuestion(4)">Yes mommy</button>
        <button class="button" onclick="nextQuestion(4)">Yes mommy</button>
    </div>

    <!-- 4th Question: HEY -->
    <div id="question5" class="question" style="display:none;">
        HEY
        <br>
        <button class="button" onclick="nextQuestion(5)">Weiter</button>
    </div>

    <!-- 5th Question: I LOVE YOU -->
    <div id="question6" class="question" style="display:none;">
        I LOVE YOU…
        <br>
        <button class="button" onclick="nextQuestion(6)">I love you too</button>
    </div>

    <!-- Flying emojis -->
    <div id="emojiContainer">
        <span class="emoji">🎉</span>
        <span class="emoji">💖</span>
        <span class="emoji">🎈</span>
        <span class="emoji">🥳</span>
        <span class="emoji">💝</span>
    </div>

    <!-- Last Question: Will you be my Valentine -->
    <div id="question7" class="question" style="display:none;">
        Will you be my Valentine? (I hope you don't find this cringe)
        <br>
        <button class="button" onclick="nextQuestion(7)">Yes mommy</button>
        <button class="button" onclick="nextQuestion(7)">Yes mommy</button>
    </div>

    <!-- Final Message -->
    <div id="finalMessage" class="question" style="display:none;">
        <h1>I LOVE YOU MO!</h1>
        <audio id="music" autoplay>
            <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mp3">
            Your browser does not support the audio element.
        </audio>
    </div>

    <script>
        let currentQuestion = 1;

        // Go to the next question
        function nextQuestion(questionNumber) {
            if (questionNumber === 1) {
                document.getElementById("question1").style.display = 'none';
                document.getElementById("question2").style.display = 'block';
            } else if (questionNumber === 2) {
                document.getElementById("question2").style.display = 'none';
                document.getElementById("question3").style.display = 'block';
            } else if (questionNumber === 4) {
                document.getElementById("question4").style.display = 'none';
                document.getElementById("question5").style.display = 'block';
            } else if (questionNumber === 5) {
                document.getElementById("question5").style.display = 'none';
                document.getElementById("question6").style.display = 'block';
            } else if (questionNumber === 6) {
                document.getElementById("question6").style.display = 'none';
                document.getElementById("emojiContainer").style.display = 'block';
                setTimeout(() => {
                    document.getElementById("question7").style.display = 'block';
                }, 3000);
            } else if (questionNumber === 7) {
                document.getElementById("question7").style.display = 'none';
                document.getElementById("finalMessage").style.display = 'block';
                document.getElementById("music").style.display = 'block';
            }
        }

        // Handle the answer to 'Do you love me?'
        function answerLove(answer) {
            if (answer === 'yes') {
                document.getElementById("response3").innerHTML = "I love you too!";
            } else {
                document.getElementById("response3").innerHTML = "You're lying!";
            }
            document.getElementById("question3").style.display = 'none';
            document.getElementById("response3").style.display = 'block';
            setTimeout(() => {
                document.getElementById("question4").style.display = 'block';
            }, 2000);
        }
    </script>

</body>
</html>
