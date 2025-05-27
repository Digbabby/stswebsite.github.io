---
permalink: /about/
title: "About"
---

#Tempor velit sint sunt ipsum tempor enim ad qui ullamco. Est dolore anim ad velit duis dolore minim sunt aliquip amet commodo labore. Ut eu pariatur aute ea aute excepteur laborum. Esse ea esse excepteur minim mollit qui cillum excepteur ex dolore magna. Labore deserunt fugiat incididunt incididunt sint ea. Consequat dolore aute laboris quis proident quis non et est consectetur ex eiusmod sit culpa.

#Cupidatat ea do et in excepteur in. Ad nostrud ut est esse eu duis ea sunt eiusmod. Aliquip tempor veniam sint elit fugiat. Velit incididunt laboris amet incididunt labore dolore irure velit excepteur commodo deserunt laborum. Consectetur eu fugiat veniam veniam Lorem labore magna eiusmod. Ea occaecat reprehenderit pariatur consectetur minim labore ut aliquip.

#quiz sample
<h2 style="text-align:center;">🧠 Quick Quiz</h2>
<p style="text-align:center;">What is the capital of France?</p>

<div id="quiz-container" style="text-align:center;">
  <button class="quiz-btn" onclick="checkAnswer(this, false)">A. Berlin</button>
  <button class="quiz-btn" onclick="checkAnswer(this, false)">B. Madrid</button>
  <button class="quiz-btn" onclick="checkAnswer(this, true)">C. Paris</button>
</div>

<div id="score-container" style="text-align:center; display:none; margin-top:20px;">
  <p id="score-msg" style="font-weight:bold;"></p>
  <button onclick="resetQuiz()" class="retry-btn">Retry Quiz</button>
</div>

<style>
  .quiz-btn {
    display: block;
    margin: 10px auto;
    padding: 10px 20px;
    background-color: #eee;
    border: 1px solid #ccc;
    border-radius: 6px;
    cursor: pointer;
    font-weight: bold;
    transition: background-color 0.3s ease;
  }

  .quiz-btn.correct {
    background-color: #28a745;
    color: white;
  }

  .quiz-btn.incorrect {
    background-color: #ccc;
    color: #666;
    pointer-events: none;
  }

  .retry-btn {
    background-color: #007bff;
    color: white;
    padding: 8px 16px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-weight: bold;
  }

  .retry-btn:hover {
    background-color: #0056b3;
  }
</style>

<script>
  let answered = false;
  let score = 0;

  function checkAnswer(button, isCorrect) {
    if (answered) return;
    answered = true;

    if (isCorrect) {
      button.classList.add("correct");
      score += 1;
    } else {
      button.classList.add("incorrect");
    }

    // Disable all buttons
    const buttons = document.querySelectorAll("#quiz-container .quiz-btn");
    buttons.forEach(btn => btn.disabled = true);

    // Show score
    const scoreBox = document.getElementById("score-container");
    const scoreMsg = document.getElementById("score-msg");
    scoreMsg.innerText = score === 1 ? "✅ Correct! Your score: 1/1" : "❌ Incorrect. Your score: 0/1";
    scoreBox.style.display = "block";
  }

  function resetQuiz() {
    answered = false;
    score = 0;

    // Reset buttons
    const buttons = document.querySelectorAll("#quiz-container .quiz-btn");
    buttons.forEach(btn => {
      btn.disabled = false;
      btn.classList.remove("correct", "incorrect");
    });

    // Hide score
    const scoreBox = document.getElementById("score-container");
    scoreBox.style.display = "none";
    document.getElementById("score-msg").innerText = "";
  }
</script>
