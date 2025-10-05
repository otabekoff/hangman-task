# 🎮 Hangman Game

> [!NOTE]
> This Hangman game task was solved by Otabek Sadiridinov and reviewed by AI. For feedback or issues, please open a [GitHub issue](https://github.com/otabekoff/hangman-task/issues/new) in this repository.

A classic word-guessing game implemented in Python as part of MIT 6.0001 Problem Set 2. Test your vocabulary skills by guessing letters to reveal the hidden word!

## 📋 Table of Contents

- [Features](#features)
- [Game Rules](#game-rules)
- [Installation](#installation)
- [How to Play](#how-to-play)
- [Game Modes](#game-modes)
- [Scoring System](#scoring-system)
- [File Structure](#file-structure)
- [Development](#development)
- [Examples](#examples)
- [Contributing](#contributing)

## ✨ Features

- **Classic Hangman Gameplay** - Guess letters to reveal the hidden word
- **Smart Warning System** - 3 warnings for invalid inputs before losing guesses
- **Vowel/Consonant Penalties** - Different guess penalties for vowels (2) vs consonants (1)
- **Hint System** - Get possible word matches when stuck (Part 3)
- **Large Word Database** - Over 55,000 words from `words.txt`
- **Score Calculation** - Based on remaining guesses and unique letters
- **Input Validation** - Handles invalid characters and repeated guesses

## 🎯 Game Rules

### Basic Rules
- **Starting Guesses**: 6 guesses
- **Starting Warnings**: 3 warnings
- **Word Source**: Random selection from 55,900+ words

### Penalties
- **Invalid Input**: Lose 1 warning (or 1 guess if no warnings left)
- **Repeated Guess**: Lose 1 warning (or 1 guess if no warnings left)
- **Wrong Consonant**: Lose 1 guess
- **Wrong Vowel** (a, e, i, o, u): Lose 2 guesses
- **Correct Guess**: No penalty

### Winning & Scoring
- **Win Condition**: Guess all letters in the word
- **Lose Condition**: Run out of guesses
- **Score**: `remaining_guesses × unique_letters_in_word`

## 🚀 Installation

1. **Clone or download** this repository
2. **Ensure Python 3.x** is installed on your system
3. **Navigate** to the project directory:
   ```bash
   cd hangman-task
   ```

## 🎮 How to Play

### Quick Start
```bash
python hangman.py
```

### Manual Word Selection (for testing)
Edit the bottom of `hangman.py`:
```python
if __name__ == "__main__":
    # For manual testing
    secret_word = "apple"  # Set your test word
    hangman(secret_word)
```

### Random Word Selection
```python
if __name__ == "__main__":
    secret_word = choose_word(wordlist)
    hangman(secret_word)
```

## 🎯 Game Modes

### Mode 1: Classic Hangman
```python
secret_word = choose_word(wordlist)
hangman(secret_word)
```

### Mode 2: Hangman with Hints
```python
secret_word = choose_word(wordlist)
hangman_with_hints(secret_word)
```

**Hint Feature**: Type `*` to see all possible words that match your current progress!

## 📊 Scoring System

Your final score is calculated as:
```
Score = Remaining Guesses × Number of Unique Letters
```

**Example**:
- Word: "tact" (4 unique letters: t, a, c)
- Remaining guesses: 3
- Score: 3 × 4 = 12 points

## 📁 File Structure

```
hangman-task/
├── hangman.py              # Main game implementation
├── words.txt               # Word database (55,900+ words)
├── README.md               # This file
├── MIT6_0001F16_Pset2.pdf  # Original problem set
├── .editorconfig           # Code formatting configuration
├── .vscode/                # VS Code settings
│   └── settings.json
└── test_files/             # Test scripts (if any)
```

## 🛠️ Development

### Key Functions

#### Core Game Functions
- `hangman(secret_word)` - Main game loop
- `hangman_with_hints(secret_word)` - Game with hint system

#### Helper Functions
- `is_word_guessed(secret_word, letters_guessed)` - Check if word is complete
- `get_guessed_word(secret_word, letters_guessed)` - Get current word state
- `get_available_letters(letters_guessed)` - Get unguessed letters
- `match_with_gaps(my_word, other_word)` - Check if partial word matches
- `show_possible_matches(my_word)` - Display matching words for hints

#### Utility Functions
- `load_words()` - Load word list from file
- `choose_word(wordlist)` - Select random word

### Code Style
- Follows Python PEP 8 guidelines
- 4-space indentation
- 79-character line limit
- Comprehensive docstrings

## 📖 Examples

### Winning Game
```
Welcome to the game Hangman!
I am thinking of a word that is 4 letters long.
You have 3 warnings left.
-------------
You have 6 guesses left.
Available letters: abcdefghijklmnopqrstuvwxyz
Please guess a letter: a
Good guess: a_ _ _
------------
You have 6 guesses left.
Available letters: bcdefghijklmnopqrstuvwxyz
Please guess a letter: p
Good guess: app_
------------
You have 6 guesses left.
Available letters: bcdefghijklmnopqrstuvwxyz
Please guess a letter: l
Good guess: appl
------------
You have 6 guesses left.
Available letters: bcdefghijkmnopqrstuvwxyz
Please guess a letter: e
Good guess: apple
------------
Congratulations, you won!
Your total score for this game is: 24
```

### Using Hints
```
You have 4 guesses left.
Available letters: bcdefghijkmnopqrstuvwxyz
Please guess a letter: *
Possible word matches are:
apple ample
------------
```

### Invalid Input Example
```
Please guess a letter: 123
Oops! That is not a valid letter. You have 2 warnings left: a_ _ _
```

## 🤝 Contributing

This is an educational project based on MIT's 6.0001 course. Feel free to:

1. **Fork** the repository
2. **Create** a feature branch
3. **Make** your improvements
4. **Submit** a pull request

### Ideas for Enhancement
- Add difficulty levels
- Implement categories (animals, countries, etc.)
- Add a GUI interface
- Create multiplayer mode
- Add word definitions
- Implement save/load game state

## 📚 Educational Context

This project implements MIT 6.0001 Problem Set 2, focusing on:
- **String manipulation**
- **List operations**
- **Control flow** (loops, conditionals)
- **Function design**
- **Input validation**
- **Game logic implementation**

## 🏆 Credits

- **Original Problem Set**: MIT 6.0001 Introduction to Computer Science and Programming in Python
- **Implementation**: Otabek Sadiridinov
- **Word List**: MIT-provided dictionary

---

**Enjoy playing Hangman! 🎯**

*Challenge yourself with this classic word game and improve your vocabulary while having fun!*
