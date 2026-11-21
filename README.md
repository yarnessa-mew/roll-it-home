# 🧶 Roll It Home

**Roll It Home** is a cozy, family-friendly sliding puzzle game set in *The Kitty Crochet Collective*—a rescue where shy kittens learn to play. Roll a bright ball of yarn across a cluttered living room floor to reach a waiting kitten on its cushion.

> **The Catch:** Once the yarn ball starts rolling, it keeps going in a straight line until it bumps into a wall, a piece of furniture, or a roaming Roomba!

---

## ✨ Features

* **Classic Sliding-Ice Puzzle Mechanics:** Plan multi-step bank shots off cardboard boxes, potted plants, and footstools.
* **Kitten-Piloted Roombas:** Roaming robotic vacuums—each with a kitten riding on top—patrol set tracks across the room. Wait for them to clear a lane, or bounce off them as moving backstops!
* **Guaranteed Solvable Procedural Levels:** Every board is dynamically generated and verified by an integrated Breadth-First Search (BFS) solver so no two playthroughs are alike.
* **Play Anywhere (Ages 6+):** Designed for families passing a phone around or playing on a laptop, with responsive scaling, scroll-locked touch swipes, large tap targets, and keyboard support.
* **Zero Dependencies:** Built 100% with vanilla HTML5, CSS3, and JavaScript in a single self-contained `index.html` file. Every kitten, yarn ball, obstacle, and animation is drawn with inline SVGs and CSS.

---

## 🎮 How to Play

1. **Aim for the Cushion:** Roll the yarn ball onto the waiting kitten's pink cushion. If the ball passes over the cushion at any point during a roll, the kitten catches it and the board is solved!
2. **Watch Your Trail:** A pink yarn trail marks your path across the floor so you can visualize your previous moves.
3. **Reset Anytime:** Stuck in a corner? Tap **Start over** to return the yarn ball to its starting tile and clear the trail. *(Note: Starting over keeps your current move count running for par scoring.)*

### Controls

| Input Method | Action |
| :--- | :--- |
| **Touch / Swipe** | Swipe up, down, left, or right anywhere on the game board |
| **On-Screen D-Pad** | Tap the `▲`, `◀`, `▶`, `▼` directional buttons below the board |
| **Keyboard** | Use the **Arrow Keys** (`↑` `←` `↓` `→`) or **`W` `A` `S` `D`** |

### Rounds & Progression

A full game spans **12 boards** across **3 rounds**, growing larger and busier as you go:

| Round | Boards | Grid Size | Roaming Roombas | Target Par |
| :---: | :---: | :---: | :---: | :---: |
| **Round 1** | 3 | $7 \times 7$ | 2 | 2 – 3 moves |
| **Round 2** | 4 | $9 \times 9$ | 3 | 3 – 5 moves |
| **Round 3** | 5 | $11 \times 11$ | 4 | 4 – 7 moves |

### Scoring

* **2 Points:** Solve a board in **par moves or fewer**.
* **1 Point:** Solve a board in **more than par moves**.
* **Maximum Score:** **24 points** across all 12 boards.

---

## 🐱 Meet the Kittens

Each board introduces one of the twelve rescue kittens from the Collective:

* **Round 1:** Pepper, Biscuit, Mochi
* **Round 2:** Clementine, Dot, Waffles, Pickles
* **Round 3:** Juniper, Noodle, Marmalade, Figgy, Tofu

Complete all three rounds to celebrate with all twelve kittens on the victory screen!

---

## 🛠️ Under the Hood

### Single-File Architecture
The entire application lives inside `index.html` with no external fonts, images, audio files, or third-party libraries:
* **Graphics & Animation:** Custom inline `<svg>` definitions paired with CSS keyframe animations for ball squishing on impact, obstacle wobbling, kitten pounces, floating hearts, and blinking Roomba LEDs.
* **Responsive Viewport Fitting:** Uses a `ResizeObserver` alongside dynamic viewport units (`dvh`) so the board and D-pad fit comfortably on mobile screens without accidental page scrolling.

### Procedural Generation & BFS Solver (`findPar`)
Rather than relying on static handcrafted maps, `generateBoard()` builds rooms procedurally (~35% obstacle density) and validates each candidate with `findPar()`:
1. Places the yarn ball, target kitten, patrolling Roomba lanes, and static obstacles.
2. Runs a **Breadth-First Search** over all reachable stopping positions on the grid, accounting for both static obstacles and potential backstops along Roomba patrol tracks.
3. Discards any board that is unsolvable, solvable in a single move, or outside the current round's target par window.

---

## 🚀 Running Locally & Deploying

### Run Locally
Because there is no build step or server requirement:
1. Clone or download this repository.
2. Open `index.html` directly in any modern web browser (Chrome, Safari, Firefox, Edge).

### Host Free on GitHub Pages
1. Push `index.html` and `README.md` to your GitHub repository.
2. Go to **Settings → Pages** in your repository.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose your `main` branch and `/ (root)` folder, and click **Save**.
4. Your game will be live at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

---

## 📁 Repository Structure

```text
.
├── index.html   # Complete game (HTML, CSS, inline SVGs, and JavaScript)
└── README.md    # Project documentation
```

---

## 📄 License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).
