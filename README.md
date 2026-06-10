# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

Game Purpose

The Game Glitch Investigator is a number guessing game built with Streamlit. The player tries to guess a secret number within a limited number of attempts while receiving hints that indicate whether the guess is too high or too low.

Bugs Found

1. The secret number was being reset unexpectedly, making the game difficult or impossible to win.
2. The hint logic was incorrect and returned misleading "Too High" and "Too Low" messages.
3. Core game logic was mixed into the Streamlit UI instead of being separated into reusable functions.

Fixes Applied

1. Moved the game logic functions into logic_utils.py.
2. Corrected the guess comparison logic so hints match the player's guess.
2. Added automated tests in tests/test_game_logic.py.
4. Verified all tests pass using pytest.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. Start the game and select the Normal difficulty level.
2. Enter a guess lower than the secret number and receive a "Too Low" message.
3. Enter a guess higher than the secret number and receive a "Too High" message.
4. Continue narrowing the range using the hints.
5. Enter the correct secret number and receive the "Win" outcome.
6. The score updates correctly based on the outcome and attempt number.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
(.venv) PS C:\Training_2\ai110-module1show-gameglitchinvestigator-starter> python -m pytest

collected 3 items

tests/test_game_logic.py ...                                  [100%]

3 passed in 0.07s
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
