# Crush.skill

> *"Ten thousand times back to that moment of heart flutter."*

**Distill your crush into an AI Skill — let that feeling live on in your terminal.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.9+](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://python.org)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-Standard-green)](https://agentskills.io)

&nbsp;

Provide source materials from your crush (chat logs, photos, social media) plus your own descriptions.  
Generate an **AI Skill that truly sounds like them** —  
speaks with their catchphrases, replies in their style, remembers every heart-fluttering moment between you.

⚠️ **This project is for personal emotional analysis and memory only. Not for harassment, stalking, or privacy invasion.**

[Installation](#installation) · [Usage](#usage) · [Examples](#examples)

---

## Installation

### Claude Code

> **Important**: Claude Code searches for skills in `.claude/skills/` at the git repository root. Please execute in the correct location.

```bash
# Install to current project
mkdir -p .claude/skills
git clone <your-repo-url> .claude/skills/create-crush

# Or install globally (available in all projects)
git clone <your-repo-url> ~/.claude/skills/create-crush
```

### Dependencies (Optional)

```bash
pip3 install -r requirements.txt
```

---

## Usage

In Claude Code, type:

* `/create-crush`
* "Help me create a crush skill"
* "I want to distill a crush"
* "Make a skill for XX"

### Creation Flow

1. **Basic Info**: Alias + Basic Info + Personality Profile (3 questions)
2. **Source Import**: Chat logs, photos, social media (optional)
3. **Analysis & Generation**: Relationship Memory + Persona
4. **Chat Test**: Talk like them

### Management Commands

| Command | Description |
|---------|-------------|
| `/list-crushes` | List all crushes |
| `/{slug}` | Chat with them |
| `/{slug}-memory` | Memory mode |
| `/{slug}-persona` | Persona mode |
| `/delete-crush {slug}` | Delete |
| `/let-go {slug}` | Gentle delete |
| `/destroy {slug}` | Destroy - generate summary then delete, encourage moving on |

### Crush-Specific Features

| Command | Description |
|---------|-------------|
| `/confess` | Confession simulator - simulate how they would respond |
| `/date` | Date simulator - predict their behavior on a date |
| `/progress` | Track relationship progression stage |
| `/analyze` | Psychological analysis of your crush |

---

## Examples

### Creation

```
User: Help me create a crush skill

Me: Give them a codename first. Doesn't need to be real — nickname, alias, whatever works.
Example: Xiaomei / goddess / that person / crush

User: Let's call her Xiaomei

Me: One sentence to introduce? What do you know about her?

User: Known her for 3 months, haven't confessed yet, coworker

Me: Last one — describe their personality in one sentence?

User: ENFP,双子座, talks a lot, always social, but sometimes our eyes meet
```

### Chatting

```
User: /xiaomei

Xiaomei: What do you want? Something up?

User: Nothing, just missed you

Xiaomei: ...cut the crap. Are you bored at work again?

User: Want to grab dinner together?

Xiaomei: Depends, I've been busy lately
    If you're paying, I'll consider it 😏
```

---

## Safety Boundaries

1. **For personal emotional analysis only** — not for harassment or privacy invasion
2. **No real contact** — conversation simulation won't replace real communication
3. **No unhealthy attachment** — if showing obsessive behavior, suggest professional help
4. **Privacy protection** — all data stored locally only
5. **Maintain boundaries** — friends but not quite lovers feeling

---

## Project Structure

```
crush/
├── SKILL.md                    # Main skill file
├── prompts/
│   ├── intake.md               # Info collection guide
│   ├── memory_builder.md       # Relationship memory template
│   ├── memory_analyzer.md      # Relationship memory analyzer
│   ├── persona_builder.md      # Persona template
│   ├── persona_analyzer.md     # Personality behavior analyzer
│   ├── merger.md               # Incremental merge logic
│   ├── correction_handler.md  # Conversation correction handler
│   ├── confession_simulator.md # Confession simulator
│   ├── date_simulator.md       # Date simulator
│   ├── progression_tracker.md  # Progression tracker
│   └── crush_analyzer.md       # Psychological analyzer
└── tools/
    ├── wechat_parser.py        # WeChat chat log parser
    ├── qq_parser.py            # QQ chat log parser
    ├── social_parser.py        # Social media parser
    ├── photo_analyzer.py       # Photo EXIF analyzer
    ├── version_manager.py      # Version management/rollback
    └── skill_writer.py         # Skill file manager
```

---

## The Ultimate Purpose

The ultimate purpose of this Skill is not to keep you forever trapped in my code, but to give you the courage to embrace that "imperfect" reality after experiencing "perfection".

---

## Credits

Inspired by: [ex-skill](https://github.com/therealXiaomanChu/ex-skill)
