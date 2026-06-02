# Gossip Digest Skill

中文说明: [README.md](README.md)

`gossip-digest` is a Codex Skill for evidence-driven relationship and incident summarization. It helps turn messy chat screenshots, copied group chats, online disputes, abstract conversations, gossip/expose materials, PDFs, Word files, PPT decks, and multi-file bundles into a concise summary, relationship graph, timeline, uncertainty notes, and optional shareable files.

Its core goal is not to decide who is right or wrong. It helps clarify:

> what happened, who is involved, how people relate, what is supported by the material, and what remains uncertain.

## What It Does

- Summarizes messy materials into a short, readable explanation.
- Extracts people, aliases, roles, stances, and supported gender information.
- Builds a simple Mermaid relationship graph.
- Organizes key events into a timeline when useful.
- Separates direct material claims, model inference, disputes, and evidence gaps.
- Uses memorable neutral pseudonyms such as `小黄`, `小红`, `小蓝`, `小绿`.
- Redacts sensitive information such as phone numbers, ID numbers, addresses, private accounts, schools/classes, workplaces, and minors' identifying details.
- Supports quick-share outputs such as Word summaries and PNG relationship/summary cards when requested.

## Best Fit

- QQ/WeChat/Discord/Telegram group chat screenshots after OCR.
- Copied chat logs or exported conversation text.
- Online incidents with multiple speakers or confusing relationships.
- Abstract chats, group arguments, project/social communication reviews.
- Gossip/expose documents where claims need to be phrased carefully.
- PPT/PDF/DOCX/TXT/Markdown materials that need structured reading.

## Output Modes

- **Quick chat mode**: short intro, relationship graph, key people, key points, uncertainty notes.
- **Incident mode**: summary, graph, compact timeline, disputed points, evidence limits.
- **Full dossier mode**: full report, people table, relationship table, timeline, dispute analysis, privacy note, optional Word/PNG deliverables.

## Safety Style

The Skill avoids turning allegations into facts. It prefers wording such as:

- "材料显示..."
- "聊天记录中出现..."
- "群聊截图看起来是在讨论..."
- "目前无法确认..."

It does not output insulting labels, doxxing details, or unsupported claims of wrongdoing.

## Install

Copy the `gossip-digest` folder into your Codex skills directory:

```powershell
Copy-Item -Recurse .\gossip-digest $env:USERPROFILE\.codex\skills\
```

On macOS/Linux:

```bash
cp -R ./gossip-digest ~/.codex/skills/
```

Then start a new Codex session and ask for `$gossip-digest`, or describe a matching task such as:

```text
用 gossip-digest 帮我快速梳理这些 QQ 群聊天截图，给我简介和人物关系图。
```

## Repository Contents

```text
gossip-digest/
├── SKILL.md
└── agents/
    └── openai.yaml
```

The Skill is intentionally lightweight and does not bundle OCR or document parsing scripts. Codex should use available tools or other skills to extract text first, then apply this Skill's analysis workflow.
