# The Puzzle Hint 🔐

A logic puzzle game inspired by the world of programming and Puzzle systems. Crack a hidden secret code using only the hints provided — no guessing randomly, pure deduction.

---

## 🎮 Overview

The Puzzle Hint challenges you to figure out a randomly generated secret code. Before you start guessing, the game gives you a set of pre-generated hints — each one is a sequence of numbers accompanied by a clue about how close it is to the real code. Your job is to analyze every hint, cross-reference them, and deduce the correct code digit by digit.

The game has two difficulty modes and a full bilingual interface (Arabic / English) that can be switched at any time during gameplay.

---

## 🎯 Game Modes

| Mode | Code Length | Number of Hints |
|------|------------|-----------------|
| **4 Digit** | 4 digits (0–9) | 6 hints |
| **8 Digit** | 8 digits (0–9) | 10 hints |

Each digit in the code is independently chosen from 0 to 9, and digits can repeat. The 8-digit mode scales the wheel interface down automatically so everything fits on screen.

---

## 💡 Hint Types

Every hint shows a row of numbers and one of these three descriptions:

### ✅ One correct and well placed
One number in the hint matches the secret code **and** is in the exact same position. All other numbers in that hint are either absent from the code entirely or not in their correct position.

**Example:** If the secret code is `3 1 4 2` and the hint is `6 8 4 5` → the message says *"One correct and well placed"* → that means **4** in position 3 is correct.

---

### 🔄 One (or two) correct but wrongly placed
One or two numbers in the hint exist somewhere in the secret code, but they are **not** in the position shown. None of the remaining numbers appear in the code at all.

**Example:** If the secret code is `3 1 4 2` and the hint is `5 3 7 9` → the message says *"One correct but wrongly placed"* → the number **3** is in the code, but not in position 2.

---

### ❌ Nothing is correct
**None** of the numbers shown in this hint appear anywhere in the secret code. This is actually very useful — it lets you immediately eliminate four (or eight) digits from consideration.

---

## 🕹️ How to Play

1. **Choose a mode** — Pick either *4 Digit* or *8 Digit* at the top of the screen.
2. **Read all the hints** — Each hint card shows a number sequence and its clue. Study them carefully before guessing.
3. **Set your guess** — Use the ▲ and ▼ arrow buttons on each rotating wheel to select a digit for every position.
4. **Check your guess** — Press the *Check Guess* button. If the code is correct, you win. If not, the attempt counter goes up and you can try again.
5. **New game** — Press *New Game* at any time to reset everything and generate a fresh code with new hints.

### 💡 Tips for Solving

- Start with the ❌ hints. They let you rule out entire sets of digits right away.
- Use the ✅ hints to lock in specific positions one at a time.
- When you have a 🔄 hint, you know the number exists — you just need to find its real position using other hints.
- Write down your deductions on paper. Keeping track mentally across 6–10 hints is hard.

---

## 🏆 Win State

When you enter the correct code:
- A success message displays showing how many attempts it took.
- The wheels lock into place and highlight green.
- All hint cards animate to highlight every digit that matched the secret code in its correct position.
- A confetti celebration plays on screen.

---

## 🌐 Language Support

The game is fully bilingual. A language toggle button (`AR` / `EN`) is fixed to the bottom-left corner of the screen. Switching language updates everything instantly — buttons, hint descriptions, messages, and the help modal — without restarting the game.

| Element | Arabic | English |
|---|---|---|
| Hint labels | تلميح 1: | Hint 1: |
| Check button | تحقق من التخمين | Check Guess |
| New game button | لعبة جديدة | New Game |
| Attempts counter | عدد المحاولات: 3 | Attempts: 3 |

---

## 🎨 Design & Atmosphere

The visual style is a minimalist black-and-white aesthetic inspired by old DOS terminals and classic command-line interfaces. Key design elements include:

- **Puzzle rain background** — columns of 0s and 1s slowly fall behind the game board, reinforcing the coding/hacking theme.
- **Rotating wheel inputs** — each digit is selected through a smooth mechanical-style wheel with up/down controls.
- **Sound effects** — subtle audio feedback plays when rotating wheels, generated in real time using the Web Audio API (no external audio files needed).
- **Glowing accents** — white glows and shadows give the interface a faint neon feel against the dark background.

---

## 📁 Project Structure

```
.
└── index.html        # The entire game — HTML, CSS, and JS in a single file
```

The project is deliberately kept as a single self-contained HTML file with no dependencies, no build step, and no external libraries.

---

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| **HTML5** | Game structure and modals |
| **CSS3** | All styling, animations, and responsive layout |
| **Vanilla JavaScript** | Game logic, hint generation, wheel controls, localization |
| **Web Audio API** | Real-time sound effect generation |

---

## 🚀 How to Run

No installation or build tools required.

1. Download or clone the repository.
2. Open `index.html` in any modern web browser (Chrome, Firefox, Safari, Edge).
3. Start playing.

That's it. The game runs entirely in the browser with zero dependencies.

---

## 🔧 Hint Generation Logic

Understanding how hints are created can help you appreciate the puzzle design:

- A secret code is generated randomly at the start of each game.
- Each hint picks one of three types at random (well placed, wrongly placed, or nothing correct).
- For **well placed** hints, exactly one position is copied from the secret code. The remaining positions are randomized to avoid accidentally matching.
- For **wrongly placed** hints, one or two digits from the secret code are placed into positions they do not occupy in the real code. All other digits are guaranteed to not appear in the secret code at all.
- For **nothing correct** hints, every digit is regenerated until none of them appear anywhere in the secret code.

This ensures every hint is always logically consistent and solvable through deduction.

---

## 📝 License

This project is open source. Feel free to use, modify, or distribute it as you see fit.
