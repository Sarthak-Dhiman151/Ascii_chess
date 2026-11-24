ASCII CHESS

    A classic in another dimension. Every piece a character. Every move your own.

License: MIT
Single File
No Build Step
Three.js
Chess Rules

text

  /\_/\
 ( o.o )   ASCII CHESS
  > ^ <

A complete game of chess rendered in real-time 3D ASCII — no textures,
no sprites, no shortcuts. Just chess, re-encoded as characters.

Open
index.html in a browser and play. That's it.
Table of Contents

    Features
    Quick Start
    How to Play
    Controls
    Game Modes
    Tech Stack
    How It Works
    Project Structure
    Customization
    Testing & Diagnostics
    Browser Support
    Deploy to GitHub Pages
    Contributing
    License

Features
♟️ Complete Chess Rules

    Full legal move generation on a reversible 0x88 board
    Castling (including all legality checks — no castling out of / through / into check)
    En passant (including the pinned-pawn edge case)
    Pawn promotion with underpromotion (Q / R / B / N)
    Check, checkmate, and stalemate detection
    Draws by threefold repetition, fifty-move rule, and insufficient material
    Standard Algebraic Notation (SAN) with disambiguation, + / # suffixes
    FEN import / export (window.ASCIIChess.loadFen())

🤖 Built-in AI Opponent

    Iterative-deepening negamax search with alpha-beta pruning
    Capture-only quiescence search to avoid horizon effects
    Material + piece-square table evaluation, bishop-pair and king-safety bonuses
    Move ordering (MVV-LVA style) for better pruning
    Runs in a Web Worker (serialized from the same file — no extra files needed)
    Three difficulties: Easy / Medium / Hard
    Graceful fallback to a yielded main-thread search if Workers are blocked (e.g. strict CSP)

⌨️ 3D ASCII Rendering

    Real 3D board and pieces rendered off-screen with Three.js (WebGL)
    Custom ASCII converter: samples the framebuffer, packs surface ID + view
    depth into the alpha channel, and draws from a cached, pre-colored glyph atlas
    Procedural piece geometry — lathed silhouettes, rings, and crowns built in code
    Adjustable ASCII density (96–256 columns), optional glitch effect, and board coordinates
    Orbit / zoom camera, move animations with particle trails, capture bursts
    Synthesized Web Audio sound effects (move, capture, castle, check, mate…) — no audio files

🎮 Game Experience

    Launch screen with session setup (opponent, side, difficulty, display)
    Clean in-game HUD: turn indicator, move counter, contextual prompts
    Slide-in Match Log: full move history, captured pieces, material advantage
    Undo, board flip, camera reset, pause menu, restart / resume
    Promotion picker, help dialog (?), and toast notifications
    Keyboard-only play (arrows + Enter), ARIA labels, focus management, and
    prefers-reduced-motion support
    Sound preference persisted in localStorage
