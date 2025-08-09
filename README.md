---
# Musōken Chess Engine

![MIT License](https://img.shields.io/badge/license-MIT-FF4136?labelColor=gray)
![Rust](https://img.shields.io/badge/language-Rust-orange?labelColor=gray)
![Creator](https://img.shields.io/badge/Creator-Tonmoy_KS-7DF9FF?labelColor=gray)

**Musōken V.1.2.0 — The Peerless Chess Engine**  
_Blade-sharp parallel search, self-optimizing evaluation, and a modern learning core._

---

## Features

- **Lightning-Fast Parallel Search**: Harnesses Rayon to search deeply and quickly across many cores.
- **Advanced Evaluation**: Customizable piece values and piece-square tables, with genetic algorithm tuning.
- **Self-Learning Module**: Adapts evaluation and opening book from self-play and recorded games.
- **Modern Move Ordering**: Killer moves, history heuristics, MVV-LVA, and SEE for tactical sharpness.
- **Transposition Table**: High-performance, concurrent hash map to avoid repeated calculations.
- **UCI Protocol Support**: Plug into GUIs like CuteChess, Arena, or Scid vs PC.
- **Configurable Depth & Time Controls**: Tweak search strength and speed to your liking.
- **Parameter Save/Load**: Easily persist and reload your learned engine knowledge.
- **Genetic Optimization**: Built-in GA for feature tuning—let your engine self-improve.
- **Rust Power**: Safe, concurrent, and blazing fast.  

---

## Build & Install

**Requirements:**  
- Rust (1.70+ recommended)  
- [Rayon](https://crates.io/crates/rayon), [dashmap](https://crates.io/crates/dashmap), [serde](https://crates.io/crates/serde), [chess](https://crates.io/crates/chess), [rand](https://crates.io/crates/rand)

**Clone and Build:**
```sh
git clone https://github.com/Tonmoy-KS/Musoken-Chess-Engine.git
cd Musoken-Chess-Engine
cargo build --release
```

---

## Usage

**Command Line (Analysis):**
```sh
cargo run --release
```
- The engine will analyze the initial position and output its chosen move.

**UCI Mode (for Chess GUIs):**
```sh
cargo run --release uci
```
- Then connect to your favorite GUI as a UCI engine.

**Custom Search:**
- Edit depth/time in `main()` or use UCI commands (e.g., `go depth 8`, `go movetime 3000`).

---

## Engine Commands (UCI + Custom)

- `uci` — Identify as Musōken, report author, and UCI compliance.
- `isready` — Engine status.
- `ucinewgame` — Reset tables.
- `position startpos [moves ...]` — Set up a position.
- `position fen <FEN> [moves ...]` — Set up via FEN.
- `go [depth N] [movetime MS]` — Start search.
- `stop` — Stop current search.
- `quit` — Exit engine.

**Musōken Custom:**
- `tune` — Run genetic tuning of all evaluation parameters.
- `selfplay N` — Play N games of self-play for learning.
- `saveparams <file>` — Save evaluation parameters.
- `loadparams <file>` — Load evaluation parameters.

---

## How It Works

- **Parallel PVS Search**: Uses Principal Variation Search, late move reductions, and aspiration windows for deep, efficient search.
- **Feature-Tuned Evaluation**: Material, PSTs, mobility, king safety, and more—parameters can be optimized via GA or learned from games.
- **Self-Play & Learning**: Plays itself, logs results, and adapts opening book and evaluation for continual improvement.
- **Genetic Algorithms**: Evolve piece values and PSTs for best performance—no hand-tuning required!

---

## Saving & Loading Knowledge

- Save learning and parameter files with `saveparams <filename>`.
- Reload them with `loadparams <filename>`.
- Opening book and self-play games are stored in JSON format for easy analysis.

---

## License

MIT License  
© [Tonmoy-KS](https://github.com/Tonmoy-KS)

---

## Contributing

PRs welcome! Please open an issue for feature requests or ideas.

---

## Contact

GitHub: [Tonmoy-KS](https://github.com/Tonmoy-KS)

---

*Sharpen your mind with Musōken — the peerless blade of chess engines.*

---

[PUP](https://github.com/Tonmoy-KS/Musoken-Chess-Engine/PUP)