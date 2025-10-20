🟩 Wordle in Google Sheets

This project is a fully playable Wordle game implemented entirely in Google Sheets using Google Apps Script. It allows you to play Wordle directly in a spreadsheet, with a grid for guesses, an on-sheet keyboard, and color feedback matching the original Wordle rules.

Features

Play Wordle directly in Google Sheets.

5×6 guess grid with automatic coloring (green, yellow, grey).

On-sheet virtual keyboard that updates with guess statuses.

Random or manually set target words.

Dictionary validation to ensure valid guesses.

Status messages and notifications with toast pop-ups.

Setup Instructions

Open a new Google Sheet.

Fill a column (e.g., B11:B2341) with your 5-letter word list (dictionary).

Open Extensions → Apps Script and paste the provided script.

Save and run onOpen once to authorize the script.

Back in your Sheet, use the menu Wordle → New game to start a new game.

Type your 5-letter guess into the merged input cell J9:P9 and press Enter.

Layout Assumptions

Guess grid: B2:F8 (6 rows × 5 columns).

Keyboard rows: I3:R3, I4:Q4, J5:P5.

Guess input box: merged J9:P9.

Instructions cell: J7:P7 (not overwritten).

Dictionary range: B11:B2341.

Status messages: J8.

How to Play

Start a new game from the menu or set a target word manually.

Enter a 5-letter guess in the input cell.

Press Enter.

The script writes the guess into the grid and colors each letter:

Green: Correct letter, correct position.

Yellow: Correct letter, wrong position.

Grey: Letter not in the target word.

Keyboard letters update to reflect the highest status seen.

You have 6 attempts to guess the target word.

Functions

onOpen() – Creates the Wordle menu.

startNewGame() – Starts a random new Wordle game.

setTargetManually() – Set a specific target word.

revealTarget() – Shows the current target word.

onEdit(e) – Handles guesses typed into the input cell.

evaluateGuess(guess, target) – Computes green/yellow/grey feedback.

updateKeyboardForGuess(sheet, letters, statuses) – Updates on-sheet keyboard.

clearGrid(sheet) – Clears the guess grid.

resetKeyboard(sheet) – Resets keyboard colors.

getDictionary(sheet) – Reads dictionary words.

Notes & Tips

Only uppercase letters A–Z are valid.

Guess must exist in the dictionary.

Merged input box ensures guesses are always read from the same cell.

Script uses document properties to store the target word and attempt count.

Status messages appear above the input and provide feedback.

Learning & Development

Creating this Wordle in Google Sheets taught me a lot about:

Using Google Apps Script for spreadsheet automation.

Handling onEdit triggers and merged cells.

Manipulating cell background colors, fonts, and alignment programmatically.

Implementing game logic in a live environment.

Debugging and testing via trial and error in Google’s online dev tools.

This project combined scripting, spreadsheet functions, and interactive design, offering a fun and educational challenge.
