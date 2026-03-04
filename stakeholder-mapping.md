# Stakeholder Mapping

*By Sahely Banerjee · [bsahely.github.io](https://bsahely.github.io)*

---

## Why Stakeholder Mapping Matters

Bad requirements are rarely a writing problem.  
They're almost always a **people problem** — the wrong person 
wasn't consulted, the right person wasn't aligned, or someone 
with veto power was discovered too late.

Map your stakeholders before you write a single requirement.

---

## Step 1: The Influence / Interest Grid

Plot every stakeholder on this 2x2:
```
HIGH INFLUENCE
      │
      │  MANAGE CLOSELY     │   KEY PLAYERS
      │  (keep satisfied)   │   (engage deeply)
      │                     │
      │─────────────────────│────────────────────
      │                     │
      │  MONITOR            │   KEEP INFORMED
      │  (minimal effort)   │   (regular updates)
      │                     │
LOW INFLUENCE
      └─────────────────────────────────────────
         LOW INTEREST            HIGH INTEREST
```

### Practical example — Salesforce CRM migration
| Stakeholder | Influence | Interest | Quadrant | Approach |
|---|---|---|---|---|
| VP of Sales | High | High | Key Player | Weekly syncs, early previews |
| Legal Lead | High | Low | Manage Closely | Loop in on contract workflows only |
| Sales Ops Analyst | Low | High | Keep Informed | Share release notes, gather feedback |
| IT Security | High | Low | Manage Closely | Early sign-off on data handling |
| End-user Sales Reps | Low | High | Keep Informed | UAT participation, training |

---

## Step 2: RACI Matrix

For every key decision or deliverable, assign one of:

| Letter | Stands for | Meaning |
|---|---|---|
| **R** | Responsible | Does the work |
| **A** | Accountable | Signs it off — only ONE person |
| **C** | Consulted | Input required before decision |
| **I** | Informed | Told after the decision is made |

### Example RACI — CPQ Release Delivery
| Task | BA | PO | Dev Lead | QA | Sales Ops |
|---|---|---|---|---|---|
| Requirements sign-off | R | A | C | I | C |
| Solution design | C | A | R | I | I |
| UAT test cases | R | A | I | C | R |
| Go/No-Go decision | C | A | C | C | I |
| Release comms | R | A | I | I | C |

> ⚠️ Common mistake: Multiple people in the A column.  
> There can only ever be ONE accountable person per task.

---

## Step 3: Communication Plan

| Stakeholder Group | What they need | Frequency | Format | Owner |
|---|---|---|---|---|
| Executive sponsors | Progress, risks, decisions needed | Bi-weekly | 5-slide deck | PO |
| Core delivery team | Requirements, priorities, blockers | Daily standup | Verbal + Jira | BA |
| SMEs / consultees | Specific questions, design reviews | As needed | Workshop | BA |
| End users | What's changing, training | Pre-launch | Email + demo | BA + Change Mgmt |
| IT / Security | Technical dependencies | Milestone-based | Written spec | BA |

---

## Stakeholder Interview — Starter Questions

Use these in discovery workshops or 1:1s:

**Understanding current state:**
- Walk me through how you do this today, step by step.
- Where do things break down or slow you down?
- What workarounds have you built that shouldn't exist?

**Understanding desired state:**
- What would "great" look like for you in 6 months?
- What's the one thing that, if fixed, would make the biggest difference?
- What would make you unwilling to adopt the new solution?

**Understanding constraints:**
- What can't change, even if it's inefficient?
- Who else needs to be part of this decision?
- What's failed before when this was attempted?

---

## Watch-outs

- 🚩 **The ghost stakeholder** — someone powerful who never attends 
  meetings but blocks decisions at the last minute. Find them early.
- 🚩 **The proxy problem** — a manager attends "on behalf of" the real 
  user. Their requirements may not reflect reality. Get to the end user.
- 🚩 **HIPPO effect** — Highest Paid Person's Opinion overrides 
  evidence. Name the data, not the opinion.
- 🚩 **Late legal/security** — Always loop in compliance early. 
  They have veto power and long review cycles.

---

*Part of the [BA Resources](README.md) collection · 
Star the repo if this helped ⭐*
