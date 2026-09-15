# quiz-cli

An interactive terminal-based multiple-choice quiz for programming concepts, implemented as a JavaScript Node.js ESM project.

## Overview

`quiz-cli` presents programming questions in the terminal and guides the user through category and question-count selection. It provides immediate correctness feedback, explanations when available, progress tracking, a final score, and a review of incorrect answers.

The quiz currently covers:

- JavaScript Basics
- Node.js Fundamentals
- General Programming

Each category currently contains five questions.

## Features

- Terminal banner displayed when the application starts
- Category selection
- Question-count selection where available:
  - All questions
  - Three questions
  - Five questions
- Randomized question order
- Numbered answer choices
- Immediate correctness feedback
- Explanations for questions that provide them
- Progress bar during the quiz
- Final score and percentage
- Review of incorrectly answered questions
- Option to replay the quiz
- Interactive terminal input using Node.js `readline`

## Prerequisites

- Node.js `>=18.0.0`

No other software or services are required.

## Installation

Clone the repository and enter the project directory:

```bash
git clone https://github.com/Khushi-K07/test-app.git
cd test-app
```

The project has no external dependencies or development dependencies, so `npm install` is not required.

## Usage

Start the quiz with the npm script:

```bash
npm start
```

Alternatively, run the entry point directly with Node.js:

```bash
node index.js
```

The application runs interactively in the terminal. Follow the prompts to:

1. Select a programming category.
2. Select the number of questions when options are available.
3. Choose an answer by its numbered option.
4. Review feedback and any available explanation.
5. Continue until the quiz is complete.
6. Review the final score and incorrect answers.
7. Choose whether to replay the quiz.

## Available Commands

The available npm scripts are defined in `package.json`.

| Command | Description |
| --- | --- |
| `npm start` | Runs `node index.js` and starts the interactive quiz |
| `npm test` | Runs Node.js's built-in test runner with `node --test` |

There is no build step.

## Dependencies

The project does not declare runtime dependencies or development dependencies.

It uses only Node.js built-in modules:

- `node:fs/promises` for file-system operations
- `node:url` for URL-related module handling
- `node:path` for path operations
- `node:readline` for interactive terminal input

No framework is used.

## Project Structure

```text
.
├── README.md
├── package.json
├── index.js
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### File Responsibilities

#### `index.js`

The application entry point. It starts the quiz and coordinates the main interactive flow.

#### `src/colors.js`

Provides terminal color and formatting functionality used to present the quiz interface and feedback.

#### `src/input.js`

Handles interactive input from the terminal.

#### `src/quiz.js`

Contains the quiz behavior, including question selection, answer handling, progress, scoring, feedback, and replay-related flow.

#### `data/questions.json`

Contains the quiz question data for the available programming categories.

## Question Data

Questions are stored in `data/questions.json` and are organized by category. The current categories are:

- `JavaScript Basics`
- `Node.js Fundamentals`
- `General Programming`

Each category currently provides five questions. A question includes the information needed to display the prompt and numbered answer choices, identify the correct answer, and show an explanation when one is provided.

The data file is the content source for the quiz, while the JavaScript files implement the interactive behavior.

## Architecture and Workflow

The application follows a small command-line workflow:

1. `index.js` starts the application.
2. Quiz logic loads the questions from `data/questions.json`.
3. The user selects a category and question count through terminal prompts.
4. The quiz selects and randomizes the questions.
5. `readline` collects the user's numbered answers.
6. The application displays correctness feedback, explanations, and progress.
7. After all questions are answered, it calculates and displays the final score percentage.
8. Incorrect answers are reviewed, and the user may replay the quiz.

## Configuration

No configuration files or environment variables are required.

The application reads its question content from:

```text
data/questions.json
```

To change the available quiz content, update that data file while preserving the structure expected by the quiz logic.

## Testing

The project defines the following test command:

```bash
npm test
```

This runs:

```bash
node --test
```

No test files or test directory are currently present in the repository. As a result, the test command is configured, but the repository does not currently include application tests.

## Development

This is a Node.js ESM project. Its `package.json` specifies:

- `"type": "module"`
- `index.js` as the package entry point
- Node.js version requirement of `>=18.0.0`
- MIT license metadata

Source files use JavaScript modules and Node.js built-in APIs. There is no compilation, bundling, or separate build process.

## Limitations

- The application is designed for interactive terminal use.
- The available questions are limited to the contents of `data/questions.json`.
- Each currently defined category contains five questions.
- No external dependencies, web interface, or additional configuration is included in the repository.
- No repository test files are currently present.

## License

The project metadata specifies the MIT license. No `LICENSE` file is currently included in the repository.