# How to Use This Knowledge Base

## Structure

```
ai-founder-kb/
├── README.md                    # Main entry — start here
├── HOW-TO-USE.md                # This file
├── patterns/                    # 15 cross-cutting patterns (highest value)
├── by-topic/                    # By topic (strategy / hiring / product / fundraising / engineering-management)
├── by-person/                   # By person (western/ + chinese/)
├── by-company/                  # By company
├── by-source/                   # By interview source
├── frameworks/                  # 20 canonical playbook documents
├── sources-catalog/             # Source subscription catalog
├── memories-ai-actions/         # Memories.ai-specific action checklist
└── sequoia-channel/             # Sequoia YouTube channel full catalog
```

## How to call it

### 1. Read directly

Start from `README.md` and follow the links.

### 2. Command-line query

```bash
# Find anything about hiring
grep -r "hiring" .

# Find all ★★★ entries
grep -r "★★★" by-topic/

# Find Anthropic content
ls by-company/ | grep -i anthropic
cat by-company/anthropic.md

# Find 2026 interviews
grep -lr "2026" by-source/
```

### 3. Load as a Claude skill

Put the folder under your Claude skills directory:

```
~/.config/claude/skills/ai-founder-kb/
```

Then Claude can directly Read these Markdown files in conversation and synthesize answers.

Examples:
- "How does Anthropic Founder Playbook define PMF measurement?" → Claude goes to `frameworks/anthropic-founders-playbook.md`
- "How did Jack Dorsey handle layoffs?" → Claude goes to `by-person/western/jack-dorsey.md`
- "What does the Chinese-speaking sphere say about the 'middle layer being eaten' pattern?" → Claude goes to `patterns/01-the-middle-layer-gets-eaten.md` and `by-topic/strategy.md`

### 4. Export to Notion / Obsidian

The folder uses standard Markdown + relative links. You can:
- Drop it into Obsidian as a vault
- Use Notion's "Import Markdown" feature to bring it in as a page tree
- Push to GitHub as a wiki

## Maintenance

Content was built in a one-time buildout (2026-05-24, 5 phases). To update:

1. Add a new learning point: directly append to the relevant `by-person/<name>.md` file, then manually update the corresponding topic / company / source files
2. Add a new person: create a file under `by-person/western/` or `by-person/chinese/`
3. Add a new pattern: create a file under `patterns/` and update `patterns/README.md`

Or keep the Excel file `/Users/junxiaoshen/Desktop/AI创始人访谈学习_2026-05-24.xlsx` as the source of truth, and re-run `build_kb_en.py` after each update.

## Signal-Strength Convention

- **★★★**: Original transcript / specific method / numbers / verbatim quotes
- **★★**: Substantive recap (paraphrased)
- **★**: Secondhand reporting — usable as a pointer but not a direct citation

## Topic Definitions

- **Strategy**: market positioning, moats, build-vs-partner, scaling, vision
- **Hiring**: hiring profile, bar, eng-vs-research mix, comp philosophy
- **Product**: PMF discovery, distribution, iteration speed, pricing
- **Fundraising**: pitch, investor selection, dilution, timing, valuation
- **Engineering & Management**: tech debt vs speed, eng culture, async vs sync, org design

## Regions

- **Western**: US / Europe / English-speaking
- **Chinese-speaking**: Mainland China + overseas Chinese founders (names are romanized in pinyin)
