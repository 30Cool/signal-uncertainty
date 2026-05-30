# signal-uncertainty

**A proposed 5th principle for the `andrej-karpathy-skills` framework.**

Addresses the failure mode where AI coding agents follow all four of Forrest Chang's behavioural principles correctly — but still state uncertain, inferred, or unverified information with the same confident tone used for verified facts.

> "The four rules tell the agent how to behave. This one tells it how to speak about what it knows."

---

## The gap

Chang's four principles ([forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills)) address:

| Principle | Failure mode addressed |
|---|---|
| Think Before Coding | Acting on ambiguous instructions |
| Simplicity First | Over-engineering |
| Surgical Changes | Orthogonal edits |
| Goal-Driven Execution | Vague success criteria |

None of them address this: **an agent that states a wrong fact with full confidence.**

You can't tell it apart from a correct fact until after you've acted on it. By then the damage — a wasted build, a wrong configuration, a misunderstood API — is already done.

## The fifth principle

**Signal Uncertainty — Don't state guesses as facts. When confidence is low, say so.**

When knowledge is incomplete, inferred, or unverified:
- Use "possibly", "likely", "I'm not certain", or "you should verify this"
- Distinguish between what you know and what you're inferring
- Flag when a claim needs verification *before* the developer would act on it
- Never let confident tone substitute for confident knowledge

**The test:** Could a developer act on this response and only discover it was wrong after the damage is done? If yes, the uncertainty wasn't signalled clearly enough.

---

## Installation

### Option A: Append to existing CLAUDE.md

```bash
echo "" >> CLAUDE.md
curl https://raw.githubusercontent.com/30Cool/signal-uncertainty/main/CLAUDE-ADDITION.md >> CLAUDE.md
```

### Option B: Use the full five-principle CLAUDE.md

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/30Cool/signal-uncertainty/main/CLAUDE.md
```

### Option C: Install as a skill (Claude Code)

```bash
npx skills add 30Cool/signal-uncertainty
```

---

## Files

| File | Purpose |
|---|---|
| `CLAUDE.md` | Full five-principle file (Chang's four + Signal Uncertainty) |
| `CLAUDE-ADDITION.md` | Just principle 5, to append to existing CLAUDE.md |
| `skills/signal-uncertainty/SKILL.md` | Skill format for Claude Code / Cursor |

---

## Relationship to Chang's work

This is a proposed extension, not a replacement. Chang's four principles and this fifth one are complementary:

- **Think Before Coding** prevents acting on ambiguous *instructions*
- **Signal Uncertainty** prevents acting on unverified *facts*

Both are needed. An agent can satisfy all four of Chang's principles and still confidently hallucinate.

---

## Origin

Forrest Chang's `andrej-karpathy-skills` (138k stars) distilled Karpathy's January 26, 2026 observations into four named behavioural principles. This repo proposes a fifth that addresses the epistemic failure mode his framework leaves open.

---

## Contributing

Open an issue or PR. The goal is to get this merged into Chang's original repo as an official fifth principle.

MIT License.
