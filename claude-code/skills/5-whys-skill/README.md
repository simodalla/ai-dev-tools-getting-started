# 5-Whys Root Cause Analysis Skill

A Claude Code skill that provides systematic root cause analysis methodology, tracing problems back to their fundamental causes instead of just addressing symptoms.

## What is This?

This is a **skill** for [Claude Code](https://claude.ai/code) that enhances Claude's ability to perform rigorous 5-Whys analysis for debugging, incident investigation, and problem-solving.

## Installation

### Option 1: Copy to your skills directory

```bash
# Clone the repo
git clone https://github.com/tt-a1i/5-whys-skill.git

# Copy to Claude Code skills directory
cp -r 5-whys-skill ~/.claude/plugins/superclaude/skills/5-whys
```

### Option 2: Symlink

```bash
git clone https://github.com/tt-a1i/5-whys-skill.git ~/skills/5-whys-skill
ln -s ~/skills/5-whys-skill ~/.claude/plugins/superclaude/skills/5-whys
```

## Usage

The skill triggers automatically when you use phrases like:

| Language | Trigger Phrases |
|----------|-----------------|
| English | "find the root cause", "why did this happen", "debug this issue", "analyze this bug", "what's causing this", "dig deeper" |
| Chinese | "找根因", "为什么会出现这个问题", "排查问题", "分析这个bug", "问题出在哪", "深挖原因" |

### Example

```
User: 用5-whys分析一下为什么部署后服务变慢了

Claude: [Applies 5-Whys methodology]

## 5-Whys Analysis: Service Performance Degradation

### Problem Statement
**What:** API latency increased from 100ms to 500ms after deployment
**When:** After v2.1.0 deployment
**Impact:** User complaints, increased timeout errors

### Why Chain
| Level | Question | Answer | Evidence |
|-------|----------|--------|----------|
| Why 1 | Why did latency increase? | DB queries slower | Query metrics |
| Why 2 | Why are queries slower? | Full table scan | EXPLAIN ANALYZE |
...
```

## Structure

```
5-whys-skill/
├── SKILL.md                           # Main skill definition (~1170 words)
├── README.md                          # This file
├── LICENSE                            # MIT License
├── references/
│   ├── toyota-origins.md              # Toyota Production System history
│   └── software-patterns.md           # Common root cause patterns
└── examples/
    ├── production-incident.md         # Payment service outage analysis
    └── performance-regression.md      # Latency investigation example
```

## Core Methodology

The skill follows a 5-phase process:

1. **Define the Problem** - State the problem as specific, observable fact
2. **Ask "Why?" Iteratively** - For each answer, ask why it happened
3. **Identify Root Cause** - Actionable, preventable, fundamental
4. **Validate the Chain** - Work backwards to verify causality
5. **Define Countermeasures** - Immediate fix + prevention + detection

## Output Format

```markdown
## 5-Whys Analysis: [Problem Title]

### Problem Statement
**What:** [Specific behavior]
**When:** [Time/conditions]
**Impact:** [Consequence]

### Why Chain
| Level | Question | Answer | Evidence |
|-------|----------|--------|----------|
| Why 1 | ... | ... | ... |
| Why 2 | ... | ... | ... |
...

### Root Cause
**Identified cause:** [Statement]
**Type:** [Process/Design/Knowledge/Resource]

### Countermeasures
| Type | Action | Owner | Timeline |
|------|--------|-------|----------|
| Immediate | ... | ... | ... |
| Preventive | ... | ... | ... |
```

## Key Principles

From the Toyota Production System:

- **Go and See (Genchi Genbutsu)** - Base analysis on facts, not assumptions
- **Respect for People** - Blame processes, not individuals
- **Continuous Improvement** - Every problem is an improvement opportunity
- **Build Quality In** - Prevention over detection over reaction

## Common Pitfalls

| Pitfall | Wrong | Right |
|---------|-------|-------|
| Stopping too early | "Server crashed → Add more memory" | "Server crashed → Fix memory leak → Add cleanup code" |
| Blame instead of cause | "Developer made mistake" | "No code review caught the issue" |
| Unverified assumptions | "I think it was X" | "Logs show X happened at 14:23" |

## Complementary Skills

This skill works well with:

- **[First Principles](https://github.com/tt-a1i/first-principles-skill)** - Question if the problem definition is right
- **Trade-off Analysis** - Choose between countermeasures
- **Hypothesis Testing** - When evidence is uncertain

## Contributing

Contributions welcome! Please feel free to submit issues or pull requests.

## License

MIT License - see [LICENSE](LICENSE) file.

## Author

Created for use with Claude Code's skill system.
