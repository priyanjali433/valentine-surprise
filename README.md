<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine Surprise</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: #f7e7ea;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Poppins', sans-serif;
}

.container {
  text-align: center;
}

/* Gift box */
.gift {
  width: 160px;
  height: 140px;
  background: #c1121f;
  border-radius: 10px;
  position: relative;
  cursor: pointer;
  box-shadow: 0 20px 35px rgba(0,0,0,0.2);
  margin: auto;
}

/* Ribbon vertical */
.gift::before {
  content: "";
  position: absolute;
  width: 30px;
  height: 100%;
  background: #fdf0d5;
  left: 50%;
  transform: translateX(-50%);
}

/* Ribbon horizontal */
.gift::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 30px;
  background: #fdf0d5;
  top: 45%;
}

/* Bow */
.bow {
  width: 60px;
  height: 30px;
  background: #fdf0d5;
  position: absolute;
  top: -15px;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 20px;
}

/* Text under box */
.surprise {
  margin-top: 12px;
  font-size: 16px;
  color: #7a1e2d;
}

/* Question section */
.question {
  margin-top: 25px;
  font-size: 20px;
  color: #5a0f1b;
  display: none;
}

/* Buttons */
.buttons {
  margin-top: 15px;
  display: none;
}

button {
  padding: 10px 20px;
  font-size: 15px;
  border: none;
  border-radius: 20px;
  cursor: pointer;
  margin: 5px;
}

.yes {
  background: #c1121f;
  color: white;
}

.no {
  background: #f2b5c0;
  position: absolute;
}

/* Message */
.message {
  margin-top: 20px;
  font-size: 18px;
  color: #7a1e2d;
}
</style>
</head>

<body>

<div class="container">

  <div class="gift" id="gift">
    <div class="bow"></div>
  </div>

  <div class="surprise">Surprise ♡</div>

  <div class="question" id="question">
    Will you be my Valentine? 💖
  </div>

  <div class="buttons" id="buttons">
    <button class="yes" id="yesBtn">Yes</button>
    <button class="no" id="noBtn">No</button>
  </div>

  <div class="message" id="message"></div>

</div>

<script>
const gift = document.getElementById("gift");
const question = document.getElementById("question");
const buttons = document.getElementById("buttons");
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");
const message = document.getElementById("message");

let noCount = 0;

const noMessages = [
  "Oops… missed it 😜",
  "That button doesn’t like you",
  "Try again, cutie",
  "Wrong universe 😌",
  "Just say yes already 💘"
];

gift.addEventListener("click", () => {
  question.style.display = "block";
  buttons.style.display = "block";
});

noBtn.addEventListener("mouseover", () => {
  noCount++;
  noBtn.style.left = Math.random() * 200 + "px";
  noBtn.style.top = Math.random() * 100 + "px";
  message.innerText = noMessages[Math.min(noCount - 1, noMessages.length - 1)];
});

yesBtn.addEventListener("click", () => {
  question.style.display = "none";
  buttons.style.display = "none";
  message.innerHTML = `
    <b>Correct answer ❤️</b><br><br>
    See? That wasn’t so hard.<br>
    Happy Valentine’s Day 💝
  `;
});
</script>

</body>
</html>
