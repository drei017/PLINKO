[README.md](https://github.com/user-attachments/files/25826195/README.md)
# 🎰 ThisIsNotGambling

**UMindanao LIC — Premium Plinko Casino Login**
*UM BBL & LIC Inside*

> 🔞 18+ ONLY | FOR EDUCATIONAL / DEMO PURPOSES ONLY | NOT REAL MONEY

---

## Project Overview

ThisIsNotGambling is a satirical, deliberately chaotic browser-based login page built as a creative web development project for the University of Mindanao LIC course. It parodies the manipulative dark patterns and predatory UX tactics employed by real online gambling platforms.

Instead of a normal username and password input, users type their credentials by dropping balls on a Plinko physics board. The board shuffles its character slots on every drop, and a cascade of chaos mechanics — cursed balls, exploding balls, flipped boards, sneeze-blasting pegs, runaway buttons, fake BSOD screens, and aggressive promo popups — make the simple act of logging in deliberately frustrating and absurd.

The project is purely educational and satirical. No real money, no real gambling, no personal data is stored.

---

## Team Members

| Name | Role |
| Adam Kintanar | Lead Developer / Physics Engine |
| Xander Salarda | Frontend & UI/CSS Design |
| Gabriel Yap | Chaos & Dark Pattern Systems |
| Adrian Maratas | Backend (PHP) & Session Logic |

---

## How It Works

### The Plinko Keyboard

The login page replaces the standard keyboard with a Plinko physics board rendered on an HTML5 Canvas. Users click anywhere on the board to drop a ball from the top. As the ball bounces through rows of pegs, it eventually lands in one of 36 character slots (A–Z, 0–9). That character is then typed into whichever input field is currently active. The slots are shuffled into a random order on every single drop, making it impossible to predict where a character will land.

### Chaos Mechanics

Every ball drop has a chance to trigger one or more chaos events:

- **Cursed Ball** (every 3rd drop) — a purple ball that types a random wrong character instead of the one it lands on.
- **Exploding Ball** (every 4th drop) — the ball detonates mid-board in a particle explosion without typing anything.
- **Flipped Board** (every 5th drop) — the entire Plinko board flips upside down for 3.5 seconds.
- **Barrier Wall** (every 5th drop) — the bottom 3 peg rows become a solid wall that bounces the ball back.
- **Slow Motion** (every 8th drop or 20% random chance) — gravity is reduced to 28%, making each drop take much longer.
- **Sneezing Pegs** (every 6th drop) — 1 to 3 pegs glow and blast nearby balls sideways.
- **Slot Drift** — the character slot labels drift slowly sideways at all times, making targeting impossible.

### Additional Annoying Features

- **Runaway Submit Button** — the "SPIN TO LOGIN" button moves to a random position inside the card whenever you hover over it (up to 6 times).
- **Fake Loader** — hovering the submit button triggers a fake loading bar with messages like *"Counting your remaining dignity..."*
- **Frustration Shake** — after 45 seconds of idling, the login card shakes violently.
- **Promo Popups** — fake gambling advertisements appear every 7–10 seconds. They are draggable and auto-dismiss after 12 seconds.
- **Heartbeat Background** — the page background slowly pulses red the longer you stay on the page.
- **PANIC Button** — scrambles all characters already typed into both fields using a Fisher-Yates shuffle.
- **DELETE Button** — 80% chance of deleting two characters instead of one, with a red field flash.
- **BSOD Jackpot** — after logging in, clicking "CLAIM JACKPOT" triggers a fake Windows Blue Screen of Death sequence.

---

## File Structure

| File | Description |
|---|---|
| `indexMain.php` | Main entry point. Handles PHP session-based authentication, renders the full page, and switches between the login view and the post-login welcome screen. |
| `plinko.js` | Core physics engine. Renders the canvas board, simulates ball physics with peg collisions, manages slot drift, barrier walls, slot highlighting, and exposes the public drop/flip/sneeze/barrier API. |
| `chaos.js` | Chaos & dark-pattern orchestrator. Manages promo popup spawning, jackpot counters, heartbeat background, frustration shake, runaway button, fake loader, and the per-drop chaos event dispatch. |
| `fields.js` | Input field manager. Handles activating fields, appending characters, backspace, clear, field switching, and the panic shuffle. Blocks all real keyboard input. |
| `ui.js` | UI feedback module. Displays the animated "YOU GOT / CURSED!" congratulations bubble and triggers the confetti system. |
| `main.js` | Wiring module. Connects the Plinko land callback to the Fields and UI modules, and kicks off `Chaos.init()`. |
| `confetti.js` | Self-contained confetti burst renderer using a secondary canvas overlay. |
| `style.css` | All visual styling: casino theme, card layouts, animations, promo popups, BSOD overlay, ticker, and responsive design. |

---

## Demo Accounts

| Username | Password | Title |
|---|---|---|
| `admin` | `pass123` | High Roller 🎰 |
| `user1` | `hello456` | Card Shark 🃏 |
| `bigwins` | `money999` | Whale 💰 |
| `lucky7` | `lucky777` | Lucky Charm 🍀 |
| `dealer` | `house000` | The House 🎲 |

---

## Setup & Running

### Requirements

- PHP 7.4 or higher
- A local web server (XAMPP, WAMP, Laragon, or PHP's built-in server)
- A modern browser with Canvas and CSS animation support (Chrome, Firefox, Edge)

### Installation

1. Clone or download the repository into your web server's document root (e.g. `htdocs/` for XAMPP).
2. Ensure JavaScript files are under `js/` and CSS under `css/` relative to `indexMain.php`.
3. Navigate to the project in your browser: `http://localhost/ThisIsNotGambling/indexMain.php`
4. Log in using any demo account above — remember, you must type credentials using the Plinko board.

---

## Technical Notes

- All physics run in a `requestAnimationFrame` loop with per-frame collision detection against all pegs.
- The slot drift offset is applied globally so ball landing positions are offset-adjusted at resolution time, not during flight.
- The keyboard is fully disabled via `keydown` and `keypress` event listeners on the document. Only the Plinko board can type.
- The PHP backend uses simple in-memory arrays for user data — there is no database. This is by design for a demo project.
- Promo popup links point to real gambling websites as part of the satirical commentary on predatory advertising.
- The BSOD overlay is purely cosmetic and runs entirely in CSS/JS with no system-level access.

---

## Disclaimer

> This project is a satirical educational exercise created for the University of Mindanao LIC course. It is designed to illustrate and critique the dark UX patterns, addictive design, and manipulative advertising commonly found on gambling platforms. No real money is involved, no real gambling functionality exists, and no user data is stored or transmitted. The project is not intended to promote gambling in any form.

---

*🎰 ThisIsNotGambling | University of Mindanao LIC | Not Real Money*
