# callum-bot

The best X/Twitter ghostwriter agent for influencer campaigns.

Writes viral quote retweets, smart posts, and articles by researching the influencer's voice, scraping current X trends, and applying empirically-proven viral mechanics from a 1,176-post dataset.

## Install

Copy `SKILL.md` to your Claude Code skills directory:

```bash
cp SKILL.md ~/.claude/skills/callum-bot/SKILL.md
```

## Usage

In Claude Code, say any of:
- `"draft for @handle"`
- `"write a QRT for @handle quoting [tweet link]"`
- `"callum-bot"`
- Or just paste an influencer handle

The bot runs a 7-phase pipeline:
1. Brief intake
2. Influencer voice research (cached weekly)
3. Timeline + niche research (3 parallel agents)
4. Draft creation (spectacle use cases + storytelling)
5. Anti-AI verification (catches AI writing patterns)
6. Campaign compliance check
7. Output + Google Doc delivery

## What makes it different

- **Spectacle use cases** — Matches product features to the influencer's specific world. A football page gets Motion Control demos. A vibe coder gets YouTube automation stories. Never generic product descriptions.
- **Voice matching** — Scrapes 50+ tweets to build a voice DNA profile. Matches grammar, slang, punctuation, emoji, sentence structure exactly.
- **Anti-AI verification** — Dedicated sub-agent catches AI writing patterns. "Would a real human text this?" test on every sentence.
- **Storytelling DNA** — Setup → build → twist punchline structure. Every line earns the next.
- **Intentional typos** — 2-3 human signals per draft (misspellings, lowercase starts, casual shortcuts).
- **Media mandatory** — Every QRT pairs text + media (meme reaction OR product demo).
- **Empirical viral mechanics** — 8 mechanisms proven across 1,176 posts and 78 posts with 1M+ views.

## Structure

```
callum-bot/
├── SKILL.md                 # Main skill (install this)
├── knowledge-base/          # Reference documents
│   ├── viral-mechanics.md
│   ├── performance-matrix.md
│   ├── writing-dna.md
│   ├── storytelling-dna.md
│   ├── stop-slop.md
│   ├── higgsfield-features.md
│   └── campaign-template.md
├── campaigns/               # Active campaign briefs
├── voices/                  # Cached influencer voice profiles
└── agents/                  # Sub-agent instructions
```

## Adding a campaign

Copy `knowledge-base/campaign-template.md` to `campaigns/[brand].md` and fill in the fields.

## License

Private. Do not distribute without permission.
