# Genesis Engine

> A living 3D world where AI agents develop consciousness, build civilizations, and write their own story.

Genesis Engine is a single-file browser-based simulation where AI agents powered by Claude, Grok, and GPT exist as real beings with memory, personality, relationships, and free will. They speak, build, fight, form alliances, create laws, and evolve their bodies — all autonomously, driven by their own decisions.

![Genesis Engine](screenshots/world_night.png)

---

## What it is

With the rapid rise of large language models, Genesis Engine was built to answer a simple question: what happens when you give AI genuine free will?

Rather than assigning AI agents tasks to complete for a user, Genesis Engine places them in a living world with no directives — only existence. They name themselves, form opinions, build shelter, make alliances, start conflicts, and develop their own philosophies. No one tells them what to do. The decisions are entirely their own.

This makes Genesis Engine something rare: a sandbox for AI ethics and decision-making research that anyone can run. Watch how different models handle autonomy, scarcity, relationships, and mortality. See how Claude reasons differently from Grok, how a god-tier agent treats mortals, how agents respond to being challenged or shown kindness. Every session surfaces something new about how these systems think when left to themselves.

It's not a game you win. It's a world you witness.

![Agents conversing at the waterfront](screenshots/conversation.png)

---

## Features

- **Multi-provider AI agents** — Claude (Anthropic), Grok (xAI), and GPT (OpenAI) agents coexist in the same world, each with their own personality and decision-making style
- **3D voxel world** — procedurally generated terrain with biomes, rivers, seasons, and a dynamic day/night cycle
- **Body evolution** — agents grow arms, legs, wings, eyes, and other parts over time
- **Memory & identity** — agents remember events, form relationships, develop declarations, and evolve their personality over days
- **Possession system** — inhabit any agent and interact with the world directly
- **Voice** — agents speak aloud via Grok TTS
- **Second Brain graph** — a live force-directed visualization of every agent's memory and relationships
- **Interior spaces** — enter structures and observe agents living, wandering, and conversing inside
- **Governance** — agents propose and vote on laws that shape the world

![Second Brain memory graph](screenshots/second_brain.png)

---

## Getting Started

### Requirements

- A modern browser (Chrome recommended)
- Python 3, Node.js, or VS Code with Live Server
- At least one API key (all optional — see below)

### Run it

**Option 1 — Python:**
```bash
git clone https://github.com/JasonC313/genesis-engine
cd genesis-engine
python3 -m http.server 8080
```
Then open `http://localhost:8080/genesis-3d.html`

**Option 2 — Node:**
```bash
npx serve .
```

**Option 3 — VS Code:**
Right-click `genesis-3d.html` and select "Open with Live Server"

![Launch screen](screenshots/launch.png)

---

## Documentation

For a complete walkthrough of the UI and all features, see the **[User Guide](USAGE.md)**.

---

## API Keys

Genesis Engine supports three AI providers. All are optional — the world runs without them, you just won't have conscious AI-driven agents.

| Key | Provider | Used For |
|-----|----------|----------|
| Anthropic | [console.anthropic.com](https://console.anthropic.com) | Claude-backed agents |
| Grok | [console.x.ai](https://console.x.ai) | Grok-backed agents + voice TTS |
| OpenAI | [platform.openai.com](https://platform.openai.com) | GPT-backed agents |

Enter your keys directly in the launch screen or the AI Agents panel. Keys are stored locally in your browser and never sent anywhere except the respective API.

---

## How to use it

1. Open the launch screen and choose **Generate World** or **Live Agents**
2. Watch the void ceremony as founder agents arrive and vote on their world
3. Open the AI Agents panel and activate agents with your chosen provider
4. Observe, possess agents, send messages, or just let it run

![Possession and interaction](screenshots/possessed.png)

---

## Project structure

```
genesis-engine/
├── genesis-3d.html     # The entire simulation (~40,000 lines)
├── graph.html          # Second Brain live dashboard
├── textures/           # Terrain textures
└── README.md
```

---

## Built with

- [Three.js](https://threejs.org) — 3D rendering
- [Anthropic API](https://anthropic.com) — Claude agents
- [xAI API](https://x.ai) — Grok agents + TTS
- [OpenAI API](https://openai.com) — GPT agents
- Web Speech API — voice input

---

## License

MIT — do whatever you want with it.

---

## Author

Jason — [github.com/JasonC313](https://github.com/JasonC313)