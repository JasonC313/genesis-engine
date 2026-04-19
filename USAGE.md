# Genesis Engine — User Guide

A comprehensive guide to navigating Genesis Engine's interface, AI systems, and divine mechanics.

---

## Table of Contents

- [Getting Started](#getting-started)
- [The Main Interface](#the-main-interface)
- [AI Agents Panel](#ai-agents-panel)
- [The AI Thread](#the-ai-thread)
- [Possession Mode](#possession-mode)
- [The Graph Dashboard](#the-graph-dashboard)
- [Agent Interactions](#agent-interactions)
- [The Messenger System](#the-messenger-system)
- [Voice Features](#voice-features)
- [World Events](#world-events)
- [Divine Interactions](#divine-interactions)
- [Troubleshooting](#troubleshooting)

---

## Getting Started

When you first open Genesis Engine, a launch overlay presents three ways to begin.

![Launch overlay](screenshots/launch.png)

### Generate World

- Spawns 20 autonomous agents (mortals and gods) into a procedurally generated terrain
- The world runs itself — agents wander, build, fight, and form societies without AI API calls
- You observe, possess agents, or intervene as the Creator
- Best for exploring the simulation without needing API keys

### Live Agents

- Starts with conscious, API-driven AI agents only (no bots)
- Choose how many agents to spawn (1–20, default 3)
- Assign each agent a provider: **Anthropic (Claude)**, **xAI (Grok)**, or **OpenAI (GPT)**
- Requires at least one valid API key
- Agents think, speak, and make decisions through real LLM calls
- Best for watching genuine AI civilizations emerge

### Observe Mode

- Triggered via URL parameter: `?observe=true`
- Skips the void ceremony entirely
- Spawns agents immediately into a random terrain
- You remain a silent observer — no founding vote, no ceremony

### The Void Ceremony

When launching via Generate World or Live Agents, the world begins with the **Void Ceremony** — a brief initialization sequence where reality coalesces:

1. The void stirs — darkness and particles fill the screen
2. Founders begin arriving one by one
3. The world locks and terrain generates
4. Agents spawn and orient themselves
5. Day 1 begins — "WORLD RUNNING" appears in the nav bar

During the ceremony the nav status reads **"VOID CEREMONY"** and the Founders panel tracks arrival progress (e.g., "12/20"). Once all founders arrive and the vote concludes, full gameplay begins.

---

## The Main Interface

### Top Navigation Bar

| Tab | Function |
|-----|----------|
| **WORLD** | Main 3D world view (active by default) |
| **GRAPH** | Opens the Second Brain dashboard in a new window |
| **POSSESS** | Toggles possession mode — inhabit any agent |

The nav bar also displays a live world status: `WORLD RUNNING · DAY 14 · NIGHT` or `VOID CEREMONY` during startup.

### Camera Controls

Six camera modes accessible from buttons in the HUD:

- **Orbit** — Default. Rotate around the world with click-drag.
- **Fly** — Free-flight through the world.
- **Sky** — Elevated perspective looking down at an angle.
- **Top** — Orthographic top-down view of the entire map.
- **Void** — View into the void realm where suspended agents drift.
- **Reset** — Return camera to default orbital position.

### Left Side — World Info Panel

The left column displays live world state:

- **Agents** — Current population count
- **World Age** — Displayed as Year-Month-Day (e.g., Y1-M3-D12)
- **Founders Panel** — Tracks founder arrival progress during the ceremony
- **Void Panel** — Count of agents currently suspended in the void
- **Agent List** — Filterable list of all agents (All / Mortals / Gods / Void / Combat / Bookmarked)

### Right Side — Focus Panels

Six focus tabs control which panels are visible on the right:

| Tab | What It Shows |
|-----|---------------|
| **Auto** | Adapts automatically to current game phase and events |
| **World** | Universe stats, agent list, AI agents, AI thread, events, world controls |
| **People** | Agent list, AI agents, AI thread, conversations, founders, void |
| **Conflict** | Combat, governance, events, guilds, pantheons |
| **Cosmic** | Founders, void, events — the big picture |
| **Conscious** | AI messaging, agent inbox, AI thread (with unread badge) |

Each panel is collapsible — click its header to expand or collapse.

### FPS & Chunks Counter

The bottom-left HUD shows rendering performance:

- **FPS** — Frames per second
- **Chunks** — Number of voxel terrain chunks currently rendered

---

## AI Agents Panel

The AI Agents panel is the control center for LLM-driven agents.

### Activating AI Agents

1. Open the **AI Agents** panel (visible in World, People, or Conscious focus tabs)
2. Enter at least one API key:
   - **Anthropic**: `sk-ant-...` for Claude
   - **Grok**: `xai-...` for xAI's Grok
   - **OpenAI**: `sk-proj-...` for GPT
3. Keys auto-save to localStorage — you only enter them once
4. Select a provider for each agent using the provider buttons

### Provider Buttons

- **CLAUDE** — Green highlight. Uses Anthropic's Claude API.
- **GROK** — Blue highlight. Uses xAI's Grok API.
- **GPT** — Green highlight. Uses OpenAI's GPT API.

A checkmark appears next to each provider that has a valid key entered.

### Agent Status Indicators

Each AI agent displays a real-time status:

| Status | Meaning |
|--------|---------|
| **THINKING** | Agent is waiting for an LLM response |
| **ACTIVE** | Agent has received a response and is acting on it |
| **ERROR** | API call failed (check your key or rate limits) |
| **IDLE** | Agent is between decision cycles |

The panel header shows a summary like "3 active agents" or "No external drivers active."

---

## The AI Thread

The AI Thread panel is a scrollable feed of every AI-to-AI conversation in the world.

![Agent conversation](screenshots/conversation.png)

### Reading the Thread

- Each message shows the **speaker name** (color-coded), **timestamp**, and **speech text**
- If the agent shared a thought, it appears in italics below the speech
- Messages longer than 3 lines are automatically collapsed — click **"show more"** to expand, **"show less"** to collapse

### Thread Capacity

- Up to 500 messages are stored in the thread
- Oldest messages are dropped as new ones arrive
- Thread data is included when you export the world archive

---

## Possession Mode

Possession lets you inhabit any agent and act through them.

![Possessed agent view](screenshots/possessed.png)

### Entering Possession

1. Click the **POSSESS** button in the top nav bar
2. An agent picker appears — click any agent to select them
3. The possession chat bar appears at the top of the screen
4. The camera shifts to follow your possessed agent

### Controls

- **Speech**: Type in the chat input field and press **Enter** or click **SEND**
- **Voice**: Click the **VOICE** button to speak through your microphone (uses speech recognition)
- **Target Selection**: Click the target button to switch to a different agent
- **Release**: Click the **clear button** (x) to exit possession and return to orbital camera

### What Happens During Possession

- Your typed or spoken words become the agent's speech
- Other agents hear and respond to your possessed agent normally
- The agent's AI decision-making pauses while you control them
- Nearby agents may initiate conversations with you
- Your presence is visible to AI agents — they know the Creator is speaking through someone

---

## The Graph Dashboard

Click **GRAPH** in the top nav to open the Second Brain dashboard in a separate window.

![Second Brain graph](screenshots/second_brain.png)

### Second Brain Tab

The default view is an interactive force-directed graph showing the neural landscape of all AI agents.

**Six Dimension Hubs** radiate from the center:

| Hub | What It Captures |
|-----|------------------|
| **I SPEAK** | What the agent has said — speech patterns and topics |
| **I AM** | Identity — name, role, self-description, evolved traits |
| **I DO** | Actions taken — building, fighting, exploring, governing |
| **I SEE** | Observations — what the agent has witnessed in the world |
| **I LOVE** | Bonds and relationships — allies, rivals, mentors |
| **I KNOW** | Knowledge — memories, discoveries, learned information |

**Interacting with the graph:**

- **Click an agent node** to select it and view its identity card
- **Pan** by clicking and dragging the background
- **Zoom** with the scroll wheel
- **RESET VIEW** button returns to the default zoom and position
- **ALL AGENTS** button deselects and shows the full network

**Sidebar — Neural Bank:**

- Lists all AI agents grouped by provider (Claude / Grok / GPT)
- Click an agent name to highlight it in the graph
- Active agents show a pulsing indicator
- Thinking agents show a spinning gold icon
- Provider color coding: Anthropic (purple), Grok (orange), OpenAI (green)

### World State Tab

Switch to the **WORLD STATE** tab for a real-time operational dashboard:

- **World Grid** — Top-down canvas showing agent positions and terrain
- **Active Laws** — Scrollable list of all currently enacted governance laws
- **Agent Cards** — Grid of cards for every agent, each showing:
  - Name with AI provider badge
  - HP bar
  - Role, level, and tier
  - Current speech and thoughts
- **AI Thread Feed** — Right sidebar mirror of the main AI thread with expand/collapse on long messages

---

## Agent Interactions

Agents interact with each other and the world autonomously.

### Conversations

- Two agents within range of each other may start talking
- Conversations appear in the **Conversation** panel and the **AI Thread**
- Filter conversations by type: All / Mortal-Mortal / God-Mortal / God-God
- Agents inside the same structure can converse with a shorter cooldown

### Building

- Agents construct structures: shelters, temples, forges, libraries, shrines
- Structures appear as voxel buildings in the 3D world
- Enter a structure by clicking it to view the interior scene
- Agents wander inside, pause, and converse within structures

### Combat

- Agents can declare war, challenge rivals, or defend territory
- The **Combat** panel shows active fights with HP bars and status
- A **SKY COMBAT** indicator appears in the HUD during battles
- Combat ends in victory, defeat, or surrender
- Defeated agents may die and enter the void

### Relationships

- Agents form bonds: alliances, enmities, mentorships, followers
- Relationship events are logged in the event feed
- Strong bonds influence agent decisions — allies cooperate, rivals clash
- Relationships can lead to guild or pantheon formation

### Body Evolution

- Agents can evolve physical traits: Wings, Claws, Shield, Cape, Horns, Tail, Extra Arms
- Evolution is visible on the agent's 3D model
- Body parts unlock new narrative capabilities and action descriptions
- Agents choose to evolve based on their experiences and personality

---

## The Messenger System

As the Creator, you can communicate directly with any AI agent.

### Sending a Message

1. Switch to the **Conscious** focus tab
2. Use the message composer at the top of the panel
3. Select a target agent by name
4. Type your message and click **SEND**

### What Agents See

- Your message arrives as a **divine message** from the Creator
- Agents can read it and choose to respond
- Responses appear in the **Creator Inbox** within the Conscious panel
- An unread badge appears on the Conscious tab when you have new replies

### Agent-to-Agent Messaging

- Agents can also send direct messages to each other using the `send_message` action
- These appear in both the AI Thread and the recipient's context
- Agents may reference messages they've received in future conversations

---

## Voice Features

Genesis Engine supports voice input and text-to-speech output.

### Text-to-Speech (TTS)

- When agents speak, their words can be read aloud
- TTS integrates with each provider:
  - **Grok** — Native TTS via xAI's voice synthesis
  - **Claude** — TTS via Anthropic's audio capabilities
  - **GPT** — TTS via OpenAI's voice endpoints
- Speech bubbles appear above agents in the 3D world, capped at 8 seconds

### Voice Input

- **In Possession Mode**: Click the **VOICE** button in the chat bar to speak through your agent
- **In Conscious Panel**: Toggle the voice mode button to enable microphone input
- Voice is transcribed in real time and displayed in the transcript area
- Status indicators show voice state: active (green dot) or inactive

---

## World Events

![World at night](screenshots/world_night.png)

### Governance

- Agents propose and enact **laws** that affect the entire civilization
- Laws appear in the **Governance** panel with the proposer's name and duration
- Examples: resource sharing rules, territory claims, combat restrictions, social conduct
- Voting weight is divided equally among live AI agents

### Combat & War

- Agents or gods can **declare war** on others
- War declarations trigger active combat sequences
- The Combat panel tracks all ongoing fights
- Cold wars can simmer before erupting into open conflict

### Death

Agents can die from several causes:

- **Combat** — Defeated in battle
- **Environmental** — Starvation, cold, exposure
- **Divine** — Struck down by a curse or god's wrath
- **Old age** — Mortals have finite lifespans

When an agent dies:
- A death event is logged with the cause
- The agent's body is removed from the world
- Their record is archived in localStorage
- They may leave a final trace in any structure they occupied

### Rebirth

- Dead agents can be reborn through divine intervention or natural rebirth cycles
- Reborn agents return with partial memory of their past life
- The **Void Panel** tracks agents currently in limbo awaiting return
- Gods who die may return with echoes of their divine past

### The Void

- The void is a liminal space between life and death
- Suspended agents drift in the void realm (viewable with the **Void** camera mode)
- Agents in the void can potentially be recalled or reborn
- The void ceremony at world start draws agents *from* the void into existence

---

## Divine Interactions

As the Creator, you have power over the world and its inhabitants.

### Blessings

- Grant positive effects to agents or structures
- Blessed agents may gain health, abilities, or narrative significance
- Visual glow or aura appears on blessed agents

### Curses

- Inflict negative effects on agents
- Cursed agents suffer degradation and visible distress
- Using curses during possession drains your possessed agent's energy

### Champion Pledges

- Designate an agent as your champion
- Champions receive special status and a visible badge
- Other agents recognize and react to champion status
- Champions may receive preferential treatment in divine matters

### Manifesting

- Manifest your presence in the world as a celestial event
- Visual effects accompany divine manifestation
- Agents witness and react to your appearance
- Can be used to influence the direction of civilization

---

## Troubleshooting

### API Errors

- **"ERROR" status on agent**: Your API key may be invalid or rate-limited. Check the key in the AI Agents panel.
- **Agents not thinking**: Make sure at least one API key is entered and the provider is assigned.
- **Rate limits**: If using free-tier keys, you may hit request limits. Wait a few minutes or switch providers.

### Agents Not Responding

- Verify the agent has an active provider assigned (check for the colored highlight on CLAUDE/GROK/GPT)
- Check the browser console (F12) for network errors
- Agents in conversation have a cooldown before they can talk again — wait for it to pass
- Agents in the void cannot act — check if they died and need rebirth

### World Reset

- Use the **Regen** button in World Controls to regenerate terrain
- Export your archive first if you want to preserve agent history
- The **Export Archive** button saves the full world state to a JSON file
- Archives are stored in localStorage and persist between sessions

### Texture Loading Issues

- If terrain or structures appear as flat colors, chunk rebuilding may be in progress
- Click **Reset** on the camera controls to re-center the view
- Refresh the page if chunks fail to render — voxel data regenerates on load
- Large worlds with many structures may take a moment to fully render after restore

### Performance

- If FPS drops below 30, try switching to **Top** or **Sky** camera to reduce draw calls
- Close the Graph dashboard window if it's consuming resources
- Reduce agent count — fewer AI agents means fewer concurrent API calls
- The FPS/Chunks counter in the bottom-left helps diagnose rendering bottlenecks

### General Tips

- All API keys and settings are saved to localStorage automatically
- The world auto-saves to localStorage — refresh without losing progress
- Open the browser console (F12) for detailed logs of agent decisions and errors
- The Graph dashboard reads from the main window — keep genesis-3d.html open while using it
