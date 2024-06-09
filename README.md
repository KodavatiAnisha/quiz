# Quiz App README

## Overview

This is a simple quiz application built with HTML, CSS, and JavaScript. The app presents a series of questions and provides feedback on the user's score at the end. It is designed to demonstrate the use of basic web technologies to create an interactive and user-friendly quiz.

## Features

- **Multiple Choice Questions:** Users can select from multiple options for each question.
- **Score Calculation:** The app calculates and displays the user's total score at the end of the quiz.
- **Responsive Design:** The app adjusts to different screen sizes for a seamless user experience.

## Technologies Used

- **HTML:** Structure of the web page.
- **CSS:** Styling for the quiz app.
- **JavaScript:** Logic for handling the quiz functionality.

## Getting Started

### Prerequisites

No special prerequisites are needed other than a web browser.

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/quiz-app.git
   cd quiz-app
   ```

2. **Open the application:**
   - Simply open the `index.html` file in your web browser.

### Running the Application

1. **Open the `index.html` file:**
   - Navigate to the project directory and open the `index.html` file in your web browser.

### Project Structure

- `index.html`: Main HTML file containing the structure of the quiz app.
- `style.css`: CSS file for styling the quiz app.
- `script.js`: JavaScript file containing the logic of the quiz app.

## Usage

1. **Launching the Quiz:**
   - Open the `index.html` file in your web browser.

2. **Answering Questions:**
   - Read the question displayed on the screen.
   - Select one of the options provided for the question.
   - Click the "Next" button to proceed to the next question.

3. **Viewing Results:**
   - After answering all questions, the total score will be displayed on the screen.

## Code Overview

### HTML (`index.html`)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz App</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>Quiz App</h1>
        <div class="question">
            <p id="questionText">Question 1: What is the capital of France?</p>
            <div class="options">
                <label><input type="radio" name="q1" value="paris"> Paris</label>
                <label><input type="radio" name="q1" value="london"> London</label>
                <label><input type="radio" name="q1" value="berlin"> Berlin</label>
            </div>
        </div>
        <button id="nextButton">Next</button>
        <div id="result" style="display: none;">
            <p>Total Score: <span id="score">0</span></p>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

### CSS (`style.css`)

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    text-align: center;
}

.container {
    margin: 100px auto;
    padding: 20px;
    background-color: #fff;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    max-width: 400px;
}

h1 {
    color: #333;
}

.question {
    font-size: 18px;
    margin: 20px 0;
}

.options {
    display: flex;
    flex-direction: column;
    gap: 10px;
    text-align: left;
}

button {
    background-color: #007BFF;
    color: #fff;
    border: none;
    padding: 10px 20px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
```

### JavaScript (`script.js`)

```javascript
document.addEventListener("DOMContentLoaded", function() {
    let currentQuestion = 1;
    let score = 0;

    const questionText = document.getElementById("questionText");
    const nextButton = document.getElementById("nextButton");
    const result = document.getElementById("result");
    const scoreDisplay = document.getElementById("score");

    nextButton.addEventListener("click", () => {
        const selectedOption = document.querySelector(`input[name="q${currentQuestion}"]:checked`);
        if (selectedOption) {
            if (currentQuestion === 1 && selectedOption.value === "paris") {
                score++;
            }
            if (currentQuestion === 2 && selectedOption.value === "8") {
                score++;
            }
            if (currentQuestion === 3 && selectedOption.value === "blue whale") {
                score++;
            }

            currentQuestion++;

            if (currentQuestion <= 3) {
                if (currentQuestion === 1) {
                    questionText.textContent = "Question 1: What is the capital of France?";
                    document.querySelector(".options").innerHTML = `
                        <label><input type="radio" name="q1" value="paris"> Paris</label>
                        <label><input type="radio" name="q1" value="london"> London</label>
                        <label><input type="radio" name="q1" value="berlin"> Berlin</label>
                    `;
                } else if (currentQuestion === 2) {
                    questionText.textContent = "Question 2: How many planets are there in the solar system?";
                    document.querySelector(".options").innerHTML = `
                        <label><input type="radio" name="q2" value="7"> 7</label>
                        <label><input type="radio" name="q2" value="8"> 8</label>
                        <label><input type="radio" name="q2" value="9"> 9</label>
                    `;
                } else if (currentQuestion === 3) {
                    questionText.textContent = "Question 3: What is the largest mammal in the world?";
                    document.querySelector(".options").innerHTML = `
                        <label><input type="radio" name="q3" value="elephant"> Elephant</label>
                        <label><input type="radio" name="q3" value="giraffe"> Giraffe</label>
                        <label><input type="radio" name="q3" value="blue whale"> Blue Whale</label>
                    `;
                }
            } else {
                // All questions are done
                questionText.style.display = "none";
                document.querySelector(".options").style.display = "none";
                result.style.display = "block";
                scoreDisplay.textContent = score;
            }
        }
    });
});
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/your-feature-name`
3. Make your changes and commit them: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Contact

If you have any questions, feel free to reach out:

- Email: anishakodavati7@gmail.com
- GitHub: https://github.com/KodavatiAnisha/quiz
