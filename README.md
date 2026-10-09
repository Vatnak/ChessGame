# Chess

A two-player chess game built from scratch in Python with Pygame. No chess libraries are used. All rules and move logic are implemented manually.

## Features

- Full 8×8 board with all six piece types
- Click to select a piece and click to move it
- Legal move highlighting for the selected piece
- Special moves: castling, en passant, and pawn promotion
- Illegal moves that leave your own king in check are blocked
- Check, checkmate, and stalemate detection
- Game-over message and restart
- Undo move (optional)

## Requirements

- Python 3.10 or newer
- Pygame

## Installation

```bash
git clone https://github.com/<your-username>/chess.git
cd chess
pip install pygame
```

## Running the game

```bash
python main.py
```

## How to play

1. White moves first.
2. Click a piece to select it. Its legal moves are highlighted.
3. Click a highlighted square to move.
4. When a pawn reaches the last rank, choose a piece to promote to.
5. The game ends on checkmate or stalemate. Press `R` to restart.

### Controls

| Input | Action |
|-------|--------|
| Left click | Select piece / move piece |
| `U` | Undo last move |
| `R` | Restart game |
| `Esc` | Quit |

## Project structure

```
chess/
├── main.py          # game loop and mouse input
├── board.py         # board state, make move, undo move
├── rules.py         # legal moves, check, checkmate, stalemate
├── ui.py            # Pygame drawing and highlights
├── assets/
│   └── images/      # wP.png, wN.png, wB.png, wR.png, wQ.png, wK.png
│                    # bP.png, bN.png, bB.png, bR.png, bQ.png, bK.png
└── README.md
```

## How it works

- **Board**: an 8×8 list of lists, where each cell holds a piece code such as `"wP"` or `"bK"`, or `"--"` for empty.
- **Move generation**: each piece generates its pseudo-legal moves, then any move that leaves the player's own king in check is filtered out to produce legal moves.
- **Game state**: tracks whose turn it is, castling rights, the en passant square, and the move history used for undo.
- **Game end**: if the player to move has no legal moves, it is checkmate when their king is in check and stalemate otherwise.

## Roadmap

- [ ] Draw by threefold repetition, 50-move rule, and insufficient material
- [ ] Move list panel with algebraic notation
- [ ] Sound effects
- [ ] Simple AI opponent

## Credits

Piece images: add the source and license here (or note that Unicode symbols are used instead).

## License

MIT. Replace this with your preferred license.