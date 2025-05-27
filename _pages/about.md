---
permalink: /about/
title: "About"
---

#Tempor velit sint sunt ipsum tempor enim ad qui ullamco. Est dolore anim ad velit duis dolore minim sunt aliquip amet commodo labore. Ut eu pariatur aute ea aute excepteur laborum. Esse ea esse excepteur minim mollit qui cillum excepteur ex dolore magna. Labore deserunt fugiat incididunt incididunt sint ea. Consequat dolore aute laboris quis proident quis non et est consectetur ex eiusmod sit culpa.

#Cupidatat ea do et in excepteur in. Ad nostrud ut est esse eu duis ea sunt eiusmod. Aliquip tempor veniam sint elit fugiat. Velit incididunt laboris amet incididunt labore dolore irure velit excepteur commodo deserunt laborum. Consectetur eu fugiat veniam veniam Lorem labore magna eiusmod. Ea occaecat reprehenderit pariatur consectetur minim labore ut aliquip.


## 🧠 Quick Quiz

What is the capital of France?

<div id="quiz-container">
  <button class="quiz-btn" onclick="checkAnswer(this, false)">A. Berlin</button>
  <button class="quiz-btn" onclick="checkAnswer(this, false)">B. Madrid</button>
  <button class="quiz-btn" onclick="checkAnswer(this, true)">C. Paris</button>
</div>

<style>
  .quiz-btn {
    display: block;
    margin: 8px 0;
    padding: 10px 15px;
    background-color: #eee;
    border: 1px solid #ccc;
    border-radius: 6px;
    cursor: pointer;
    width: fit-content;
    font-weight: bold;
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
</style>

<script>
  function checkAnswer(button, isCorrect) {
    if (isCorrect) {
      button.classList.add("correct");
    } else {
      button.classList.add("incorrect");
    }
    // Disable all buttons
    const buttons = document.querySelectorAll("#quiz-container .quiz-btn");
    buttons.forEach(btn => btn.disabled = true);
  }
</script>
