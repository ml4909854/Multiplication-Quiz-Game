# Netlify link : https://velvety-travesseiro-45497c.netlify.app/
# Multiplication-Quiz-Game
This is a simple Multiplication Quiz Game built using HTML, CSS, and JavaScript. It generates random multiplication questions, updates the user's score based on their answers, and saves the score in the browser's local storage for persistence.

# Features
Dynamic Question Generation: Each question features two randomly generated numbers between 1 and 10.
Score Tracking: User's score is updated after every correct or incorrect answer.
Local Storage Integration: The score persists even after refreshing the browser.
Interactive UI: A user-friendly interface to display the current question and score.
File Structure
less
Copy code
|-- index.html  // Main HTML file
|-- style.css   // CSS file for styling
|-- script.js   // JavaScript file for game logic
How It Works
Random Multiplication Questions:

The app generates two random numbers (num1 and num2) using Math.ceil(Math.random() * 10).
The question is displayed in the format: "What is X multiplied by Y?".
User Input:

The user enters their answer in the input field and submits the form.
Score Evaluation:

If the user's answer matches the correct result (num1 * num2), the score increases by 1.
If the answer is incorrect, the score decreases by 1.
Score Persistence:

The score is stored in the browser's local storage using localStorage.setItem() and retrieved with localStorage.getItem().
Dynamic UI Updates:

The current score and question are dynamically updated without requiring a page reload.
Code Description
JavaScript (script.js):
Random Numbers:

javascript
Copy code
const num1 = Math.ceil(Math.random() * 10);
const num2 = Math.ceil(Math.random() * 10);
Generates two random numbers for the multiplication question.
Question Display:

javascript
Copy code
question.innerHTML = `What is ${num1} multiplied by ${num2}?`;
Displays the question on the webpage.
Score Handling:

javascript
Copy code
let score = JSON.parse(localStorage.getItem("score"));
totalScore.innerHTML = `score : ${score}`;
Retrieves the score from local storage and updates the UI.
Local Storage Update:

javascript
Copy code
function updateLocalStorage() {
    localStorage.setItem("score", JSON.stringify(score));
}
Updates the score in local storage after every submission.
Form Submission:

javascript
Copy code
form.addEventListener("submit", function () {
    const userAnswer = +input.value;
    if (userAnswer === correctAnswer) {
        score++;
    } else {
        score--;
    }
    updateLocalStorage();
    input.value = ""; // Clear input
});
Evaluates the user's answer and adjusts the score accordingly.
HTML and CSS
HTML (index.html):

Contains the structure for the quiz, including:
A question display area.
An input field for answers.
A form for submission.
A score display section.
CSS (style.css):

Adds styling to enhance the visual appeal of the quiz.
Getting Started
Clone the repository:
bash
Copy code
git clone https://github.com/your-username/multiplication-quiz-game.git
Open index.html in your browser to play the game.
