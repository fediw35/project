<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Internet Addiction Quiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .quiz-container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 600px;
        }
        h1 {
            text-align: center;
        }
        .question {
            margin-bottom: 15px;
        }
        .answers {
            list-style-type: none;
            padding: 0;
        }
        .answers li {
            margin-bottom: 10px;
        }
        .result {
            display: none;
            text-align: center;
        }
        .show {
            display: block;
        }
        button {
            display: block;
            width: 100%;
            padding: 10px;
            margin-top: 20px;
            background: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background: #0056b3;
        }
    </style>
</head>
<body>
  <hr>
    <div class="quiz-container">
        <h1>Internet Addiction Quiz</h1>
        <form id="quiz-form">
            <div class="question">
                <p>1. Do you find it difficult to stop using the internet?</p>
                <ul class="answers">
                    <li><input type="radio" name="q1" value="1" required> Yes</li>
                    <li><input type="radio" name="q1" value="0"> No</li>
                </ul>
            </div>
            <div class="question">
                <p>2. Do you lose track of time when you are online?</p>
                <ul class="answers">
                    <li><input type="radio" name="q2" value="1" required> Yes</li>
                    <li><input type="radio" name="q2" value="0"> No</li>
                </ul>
            </div>
            <div class="question">
                <p>3. Do you neglect household chores to spend more time online?</p>
                <ul class="answers">
                    <li><input type="radio" name="q3" value="1" required> Yes</li>
                    <li><input type="radio" name="q3" value="0"> No</li>
                </ul>
            </div>
            <div class="question">
                <p>4. Do you find yourself staying online longer than intended?</p>
                <ul class="answers">
                    <li><input type="radio" name="q4" value="1" required> Yes</li>
                    <li><input type="radio" name="q4" value="0"> No</li>
                </ul>
            </div>
            <div class="question">
                <p>5. Do you prefer the excitement of the internet to intimacy with your partner?</p>
                <ul class="answers">
                    <li><input type="radio" name="q5" value="1" required> Yes</li>
                    <li><input type="radio" name="q5" value="0"> No</li>
                </ul>
            </div>
            <div class="question">
                <p>6. Do you form new relationships with fellow online users?</p>
                <ul class="answers">
                    <li><input type="radio" name="q6" value="1" required> Yes</li>
                    <li><input type="radio" name="q6" value="0"> No</li>
                </ul>
            </div>
            <div class="question">
                <p>7. Do others in your life complain about the amount of time you spend online?</p>
                <ul class="answers">
                    <li><input type="radio" name="q7" value="1" required> Yes</li>
                    <li><input type="radio" name="q7" value="0"> No</li>
                </ul>
            </div>
            <div class="question">
                <p>8. Does your work suffer because of the amount of time you spend online?</p>
                <ul class="answers">
                    <li><input type="radio" name="q8" value="1" required> Yes</li>
                    <li><input type="radio" name="q8" value="0"> No</li>
                </ul>
            </div>
            <div class="question">
                <p>9. Do you check your email or social media before something else that you need to do?</p>
                <ul class="answers">
                    <li><input type="radio" name="q9" value="1" required> Yes</li>
                    <li><input type="radio" name="q9" value="0"> No</li>
                </ul>
            </div>
            <div class="question">
                <p>10. Do you become defensive or secretive when anyone asks what you do online?</p>
                <ul class="answers">
                    <li><input type="radio" name="q10" value="1" required> Yes</li>
                    <li><input type="radio" name="q10" value="0"> No</li>
                </ul>
            </div>
            <button type="button" onclick="calculateResult()">Submit</button>
        </form>
        <div class="result" id="result">
            <h2>Your Score: <span id="score"></span></h2>
            <p id="feedback"></p>
        </div>
    </div>

    <script>
        function calculateResult() {
            var form = document.getElementById('quiz-form');
            var result = document.getElementById('result');
            var scoreElement = document.getElementById('score');
            var feedback = document.getElementById('feedback');
            var score = 0;

            var answers = form.querySelectorAll('input[type="radio"]:checked');
            for (var i = 0; i < answers.length; i++) {
                score += parseInt(answers[i].value);
            }

            scoreElement.textContent = score;

            if (score > 5) {
                feedback.textContent = 'You might be addicted to the internet. Consider seeking professional advice.';
            } else {
                feedback.textContent = 'You do not appear to be addicted to the internet.';
            }

            result.classList.add('show');
        }
    </script>
</body>
</html>
