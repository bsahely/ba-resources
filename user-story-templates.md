# User Story Templates

*By Sahely Banerjee · [bsahely.github.io](https://bsahely.github.io)*

---

## The Standard Format
```
As a [type of user],
I want to [do something],
So that [I get some value / outcome].
```

### ✅ Good example
```
As a Renewal Specialist,
I want to see a customer's health score directly in Salesforce,
So that I can prioritise at-risk accounts before the renewal date.
```

### ❌ Anti-pattern — too vague
```
As a user,
I want the system to be better,
So that my work is easier.
```
**Why it fails:** No specific user, no specific action, no measurable outcome.

### ❌ Anti-pattern — solution in the story
```
As a Sales Manager,
I want a Power BI dashboard with a bar chart showing pipeline by region,
So that I can track performance.
```
**Why it fails:** The story dictates the solution (bar chart, Power BI). 
Leave the how to the team — your job is to define the what and why.

---

## Formats for Different Contexts

### Job Story Format (when context matters more than role)
```
When [situation/trigger],
I want to [do something],
So I can [achieve outcome].
```

**Example:**
```
When a contract is sent for signature,
I want Legal to receive an automatic Salesforce notification,
So I can eliminate manual follow-up emails during deal close.
```

### Technical Story Format (for platform/system work)
```
As the [system/platform],
I need to [perform action],
So that [downstream outcome].
```

**Example:**
```
As the Salesforce-Gainsight integration,
I need to trigger a CTA when a customer's health score drops below 60,
So that the CSM receives an alert within 15 minutes of the score change.
```

---

## Story Sizing Reference

| Size | Story Points | What it means |
|---|---|---|
| XS | 1 | Trivial change, well understood |
| S | 2 | Small, clear scope, no unknowns |
| M | 3 | Some complexity, mostly clear |
| L | 5 | Complex, some unknowns to resolve |
| XL | 8 | Large — consider splitting |
| Epic | 13+ | Must be broken down before sprint |

---

## Epic → Feature → Story Hierarchy
```
Epic: Salesforce GTM Stack Integration
│
├── Feature: Gainsight Integration
│   ├── Story: Sync account health scores to Salesforce daily
│   ├── Story: Trigger CTA when health score < 60
│   └── Story: Display Gainsight health widget on Account page
│
├── Feature: Gong Integration  
│   ├── Story: Pull Gong call data into Salesforce activity feed
│   └── Story: Enable MEDDPICC field population from Gong transcript
│
└── Feature: Intelagree Integration
    ├── Story: Generate NDA from Salesforce opportunity in one click
    └── Story: Auto-update contract status field on signature completion
```

---

## Story Splitting Patterns

When a story is too big, split it using one of these patterns:

| Pattern | How to split |
|---|---|
| **By workflow step** | Onboarding step 1, step 2, step 3 as separate stories |
| **By user type** | Admin can do X / Standard user can do X |
| **By data type** | Handle PDF contracts / Handle Word contracts |
| **By happy path first** | Happy path story → edge cases as follow-up stories |
| **By interface** | Desktop version → Mobile version |

---

## Red Flags in a User Story

- 🚩 No acceptance criteria attached
- 🚩 "As a user" — which user exactly?
- 🚩 The word "and" in the "I want" clause — likely two stories
- 🚩 Story references a specific UI element or technology
- 🚩 No one on the team can estimate it confidently

---

*Part of the [BA Resources](README.md) collection · 
Star the repo if this helped ⭐*
