# 🐒 Baboons Over London — AI Coding Agent Benchmark

A real-world benchmark comparing **Amp Ultra** vs **Claude Code v2.1.209** — both powered by **Claude Fable 5** — on the same coding task: building a complete 3D first-person shooter game from scratch.

## 🎮 Play the Games

Both versions are playable right now — just open the HTML file in any modern browser:

### Amp Version (3 cold runs)
- [Amp Run 1](amp-version/game_run_1.html)
- [Amp Run 2](amp-version/game_run_2.html)
- [Amp Run 3](amp-version/game_run_3.html)

### Claude Code Version (3 cold runs)
- [Claude Run 1](claude-version/game_run_1.html)
- [Claude Run 2](claude-version/game_run_2.html)
- [Claude Run 3](claude-version/game_run_3.html)

## 📊 The Task

Both agents received the **exact same prompt** ([read it here](prompt.txt)): create a complete FPS game with a pump-action shotgun, baboon enemies on London streets, 5 levels of difficulty, Three.js 3D rendering, and dynamic buckshot spread mechanics.

## 🔑 Key Finding

**Same model, different efficiency.** Both agents use Claude Fable 5, but Amp's agent framework achieved the same result **2.1x faster** and **2.6x cheaper** per run.

| Metric | Amp Ultra (Fable 5) | Claude Code (Fable 5) | Winner |
|--------|---------------------|----------------------|--------|
| Avg Duration | 453.75s | 953.31s | **Amp 2.1x faster** |
| Avg Cost/run | $2.65 | $6.95 | **Amp 2.6x cheaper** |
| Avg Lines of Code | 1,162 | 1,206 | ~Equal |
| Total 3-run cost | $7.95 | $20.84 | **Amp 2.6x cheaper** |
| LOC/sec | 2.56 | 1.27 | **Amp 2.0x** |
| Cost per 1000 LOC | $2.28 | $5.76 | **Amp 2.5x** |

## 📁 Repository Structure

```
Baboons-Over-London/
├── amp-version/          # 3 game HTML files built by Amp Ultra
│   ├── game_run_1.html
│   ├── game_run_2.html
│   └── game_run_3.html
├── claude-version/       # 3 game HTML files built by Claude Code
│   ├── game_run_1.html
│   ├── game_run_2.html
│   └── game_run_3.html
├── presentation.html     # Mobile-friendly interactive presentation
├── benchmark-report.html # Detailed benchmark report with charts
├── prompt.txt            # The exact prompt given to both agents
├── LICENSE               # MIT License
└── README.md             # This file
```

## 🛠️ Technology

Both agents independently chose the **identical tech stack**:
- **Language**: JavaScript (ES modules)
- **Framework**: Three.js r0.160.0 (via CDN importmap)
- **Controls**: PointerLockControls (Three.js addons)
- **Rendering**: WebGL
- **Audio**: Web Audio API (AudioContext)
- **Output**: Single self-contained HTML file, no external dependencies

## 🔍 Methodology

- **3 cold runs** per agent (fresh context, no reference implementation)
- Both agents received the identical prompt
- Amp Ultra: `amp -x --mode ultra` (Claude Fable 5)
- Claude Code: `claude -p --output-format json --effort high` (Claude Fable 5)
- Amp cost: real per-thread cost via `amp threads usage` (zero-markup pass-through pricing)
- Claude cost: `total_cost_usd` from result JSON

Sources:
- Amp Ultra model: https://ampcode.com/models
- Amp pricing: https://ampcode.com/pricing (zero markup, pass-through API costs)

## 💬 Which Version Is Better?

**Play both versions and let us know!** Open an issue or start a discussion on GitHub:
- Which game feels more polished?
- Which has better graphics, AI, or gameplay?
- Does the performance difference matter to you?

## 📜 License

MIT License — see [LICENSE](LICENSE) for details.

## 🙏 Acknowledgments

- Game built by AI agents (Amp Ultra & Claude Code), both using Claude Fable 5
- Benchmark conducted July 2026
- Amp: https://ampcode.com
- Claude Code: https://claude.ai
