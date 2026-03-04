# Acceptance Criteria Guide

*By Sahely Banerjee · [bsahely.github.io](https://bsahely.github.io)*

---

## What Acceptance Criteria Actually Are

Acceptance Criteria (AC) define the conditions that must be true 
for a story to be considered done. They are the contract between 
the BA/PO and the development team.

**Good AC answers the question:**  
*"How will we know, without ambiguity, that this story is complete?"*

---

## Format 1: Given / When / Then (BDD Style)

Best for: functional behaviour, user interactions, integrations
```
Given [a starting context or precondition],
When [an action or event occurs],
Then [an observable, testable outcome happens].
```

### Example — Gainsight CTA trigger
```
Given a customer's health score in Gainsight is updated,
When the score drops below 60,
Then a CTA is automatically created in Gainsight 
     and the assigned CSM receives a Salesforce task 
     within 15 minutes.
```

### Example — Contract generation
```
Given a Salesforce Opportunity is in "Negotiation" stage,
When the Sales rep clicks "Generate NDA",
Then Intelagree creates a pre-populated NDA 
     using the Account name, legal entity, and contract value
     and sends it to the contact's email on file.
```

---

## Format 2: Rules-Based (Checklist Style)

Best for: business rules, validation logic, permissions
```
- [ ] Rule 1
- [ ] Rule 2
- [ ] Edge case handled
- [ ] Error state defined
```

### Example — Renewal quoting rules
```
- [ ] Renewal quote is auto-generated 30 days before contract end date
- [ ] Quote defaults to flat renewal (same price, same SKUs)
- [ ] If ARR change > 10%, quote requires VP approval before sending
- [ ] System displays error if contract end date field is blank
- [ ] Quote PDF uses the latest approved template
```

---

## Format 3: Definition of Done (Team-Level)

These apply to every story — not just one. Agree on these 
with your team at sprint start and don't repeat them per story.

### Example DoD
```
A story is Done when:
- [ ] Code reviewed and approved by at least one peer
- [ ] Unit tests written and passing
- [ ] UAT completed and signed off by BA
- [ ] No open P1/P2 bugs related to the story
- [ ] Documentation updated (if applicable)
- [ ] Deployed to staging environment
```

---

## Common Mistakes

### ❌ Vague AC
```
The dashboard should load quickly.
```
**Fix:**
```
The dashboard loads within 3 seconds for datasets up to 10,000 rows
on a standard broadband connection.
```

### ❌ AC that tests implementation, not behaviour
```
The SQL query runs in under 200ms.
```
**Fix:**
```
The report data refreshes within 5 seconds of the user clicking 
"Refresh" — regardless of the underlying query method used.
```

### ❌ Missing error states
Most ACs describe the happy path only. Always ask:
- What happens if the data is missing?
- What happens if the integration call fails?
- What does the user see if they don't have permission?

---

## AC Checklist — Before You Sign Off a Story

- [ ] At least 3 criteria written (happy path, edge case, error state)
- [ ] Every criterion is testable — QA can write a test case from it
- [ ] No ambiguous words: "fast", "easy", "should", "may"
- [ ] Negative cases covered (what should NOT happen)
- [ ] Dev team has read and agreed — no surprises
- [ ] PO has signed off

---

*Part of the [BA Resources](README.md) collection · 
Star the repo if this helped ⭐*
