# 🧧 Huat Board: a Business Advisory Board for Claude

> Say **"huat ask board"** to any business decision and get five functional leaders: Innovator, CFO, COO, General Counsel, and Growth Lead (plus a conditional Dealmaker seat for partnership/expansion decisions) to independently argue it out, review each other's blind spots, and hand you one clear verdict.

You ask one AI a question, you get one answer. It might be great. It might be mid. You have no way to tell, because you only saw one perspective.

The Huat Board fixes that. It's a [Claude Skill](https://docs.claude.com) that runs your decision through five board seats with deliberately competing mandates, has them peer-review each other's work anonymously, then synthesizes everything into a single, direct recommendation: the kind you'd want from an actual advisory board, minus the scheduling headache.

---

## Why *these* seats

Most multi-agent "council" tools just ask the same question five times and staple the answers together. That's not disagreement, it's noise. The Huat Board is built so the seats structurally collide:

| Seat | Mandate | Clashes with |
|---|---|---|
| 🚀 **The Innovator** | Push for the bold, category-defining move | COO (feasibility) |
| 💰 **The CFO** | Is this worth funding (resource steward, not a hard ROI gate) | Growth Lead (spend vs. runway) |
| ⚙️ **The COO** | Can this actually ship with the team we have today | Innovator |
| ⚖️ **General Counsel** | Legal, compliance, and reputational exposure | Growth Lead (speed vs. risk) |
| 📈 **The Growth Lead** | Market share, positioning, upside everyone's missing | CFO, Legal |
| 🤝 **The Dealmaker** *(conditional, see below)* | Doors, not funnels: partnerships, distribution, capital, warm intros | CFO (equity/cost), Legal (handshake vs. contract) |

A board where everyone agrees isn't a board. It's a rubber stamp. This one is built to argue.

**The Dealmaker only joins for decisions where "who do you know" is a real lever**: market entry, partnerships, distribution deals, fundraising. A pricing or hiring decision runs as the standard 5-seat board.

---

## Install

1. Download [`business-advisory-board.skill`](./business-advisory-board.skill) (or just grab `SKILL.md`).
2. Upload it to Claude (claude.ai → Skills, or drop it in your Claude Code / project skills folder).
3. Say the magic word.

## Use it

```
huat ask board: should we expand into Malaysia next quarter, or double down on Singapore first?
```

Other ways in: `huat ask advisory board`, `huat advice`, `convene the board`, or just present a real decision with stakes ("I'm torn between X and Y...").

It deliberately does **not** trigger on trivial or one-right-answer questions. That's not what a board is for.

## What you get

One file, dropped into your workspace:
- `board-transcript-[timestamp].md`: the chair's verdict up top (agreement, clashes, blind spots, recommendation, one thing to do first, and what would sharpen the next verdict), full board reasoning below it.

---

## ⭐ If this helped you make a call you were stuck on, star the repo

It genuinely helps more than you'd think. It's the main way people like you find this over the thousand other "AI council" repos out there.

---

## Want more systems like this for your business?

I build AI-powered decision tools and workflows like this one. If you want to go deeper on using AI to actually run parts of your business (not just chat with it), check out the course at **[xiohooai.com](https://xiohooai.com)**.

---

Inspired by [Andrej Karpathy's LLM Council](https://x.com/karpathy) methodology: dispatch to multiple models, anonymous peer review, chairman synthesis, restructured here as real business functions instead of abstract thinking styles.
