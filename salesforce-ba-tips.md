# Salesforce BA Tips

*By Sahely Banerjee · [bsahely.github.io](https://bsahely.github.io)*

*Hard-won lessons from 11+ years across Sales Cloud, 
Service Cloud, CPQ, Agentforce, and GTM integrations.*

---

## Before You Write a Single Requirement

**Understand the data model first.**  
Salesforce is built around Accounts, Contacts, Opportunities, 
and Products. Every customisation you design will live on top 
of this structure. Know what standard objects exist before 
proposing custom ones.

**Key standard objects to know:**
| Object | What it stores |
|---|---|
| Account | Company / customer record |
| Contact | Individual person at that company |
| Opportunity | A potential deal |
| Product | What you're selling |
| Quote | Priced proposal for an opportunity |
| Contract | Signed agreement |
| Case | Support ticket / customer issue |
| Task / Activity | Calls, emails, actions logged |

---

## Sales Cloud Tips

**Lead-to-Opportunity conversion is a one-way door.**  
Once a Lead is converted, you can't unconvert it. 
Define your conversion criteria clearly before go-live.

**Opportunity stages need exit criteria, not just names.**  
"Proposal Sent" is a stage name. The exit criterion is 
"Customer has confirmed receipt and agreed to review by [date]." 
Without exit criteria, stages become meaningless.

**Validation rules run before triggers.**  
If you're defining field requirements, know the order of operations 
or you'll spend a sprint debugging why data isn't saving.

**Required field ≠ important field.**  
Making every field required trains users to enter junk data 
just to save a record. Be selective. Protect data quality 
by making fields required only where the business truly 
cannot function without them.

---

## CPQ Tips

**CPQ complexity compounds fast.**  
One pricing rule affects another. A product option blocks 
a bundle. An approval rule conflicts with a discount tier.
Map your rules in a spreadsheet before configuring anything.

**Test with real-world deals, not clean ones.**  
Always ask sales ops for their 3 most complex deals 
from the past year. If your CPQ can't handle those, 
it won't handle production.

**Price waterfall documentation is non-negotiable.**  
Document every step: List Price → Partner Discount → 
Volume Discount → Manual Discount → Special Approval → 
Net Price. Everyone — Finance, Legal, Sales — must agree 
on this before build starts.

**Renewal quoting is always an afterthought. Don't let it be.**  
Define renewal logic during the initial CPQ build.
Retrofitting it later is a full project in itself.

---

## Service Cloud Tips

**Case assignment rules need a default.**  
Always define what happens when no rule matches. 
Unassigned cases are invisible cases.

**SLA / Entitlements setup is underestimated.**  
It looks simple in demos. In practice, defining 
business hours, holiday calendars, and escalation 
paths takes significant stakeholder alignment.

**Knowledge Base is only useful if someone owns it.**  
Build the governance model before the articles. 
Who approves? Who retires outdated content? 
Without this, it becomes a graveyard within 6 months.

---

## Integration Tips (Gainsight, Gong, Intelagree, Workato)

**Field mapping is the most underestimated requirement.**  
For every integration, create a field mapping document with:
- Source system field name
- Data type
- Destination system field name  
- Transformation logic (if any)
- What happens when the source field is blank

**Error handling is a requirement, not an afterthought.**  
What happens when the API call fails? 
What happens when a record doesn't exist in the target system?
Define this explicitly or it gets built inconsistently.

**Bi-directional syncs need a tiebreaker.**  
If both systems can update the same field, 
define which system "wins" in a conflict. 
Salesforce-first is common, but it must be explicit.

**Build integration tests with production-like data volume.**  
A Workato recipe that handles 10 records beautifully 
may timeout at 10,000. Test at scale before go-live.

---

## Agentforce / AI Tips

**Prompt design is a BA skill.**  
The quality of an AI bot's response is directly tied 
to the quality of the prompt. Treat prompt writing 
like requirements writing — specific, testable, with 
defined success criteria.

**Define what the bot should NOT do.**  
Guardrails are as important as capabilities. 
Document the out-of-scope scenarios and how the bot 
should handle them (handoff to human, fallback message, etc.)

**Measure deflection rate, not just usage.**  
A bot that's used but doesn't resolve anything 
is not a success. Define your success metric 
(case deflection, lead qualification rate, etc.) 
before launch, not after.

---

## Universal Salesforce BA Rules

1. **Never say "just a config change."**  
   Everything in Salesforce touches something else.

2. **Get sandbox sign-off before production.**  
   Always. No exceptions.

3. **Document your validation rules.**  
   Future-you and future-admins will thank you.

4. **Involve the System Admin early.**  
   They know where the bodies are buried.

5. **Data migration is its own project.**  
   Never let it be the last item on the plan.

6. **Training is a requirement, not a nice-to-have.**  
   A perfectly built system used incorrectly delivers 
   zero business value.

---

*Part of the [BA Resources](README.md) collection · 
Star the repo if this helped ⭐*
