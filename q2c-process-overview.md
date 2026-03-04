# Quote-to-Cash (Q2C) Process Overview

*By Sahely Banerjee · [bsahely.github.io](https://bsahely.github.io)*

---

## What is Q2C?

Quote-to-Cash covers every step from a sales rep creating a quote 
to the company receiving and recognising payment. It cuts across 
Sales, Legal, Finance, and CS — which is exactly why it breaks 
down so often and why BAs are critical to getting it right.

---

## The End-to-End Process
```
Lead → Opportunity → Quote → Proposal → Contract → 
Order → Fulfilment → Invoice → Payment → Revenue Recognition
```

### Stage-by-stage breakdown

| Stage | What happens | Systems typically involved |
|---|---|---|
| **Opportunity** | Deal qualified, value estimated | Salesforce CRM |
| **Configuration** | Products selected, bundles built | Salesforce CPQ |
| **Pricing** | Discounts applied, approval triggered | CPQ + Approval Workflows |
| **Quote** | Quote document generated | CPQ + DocGen |
| **Proposal** | Sent to customer for review | Email / DocuSign |
| **Negotiation** | Legal redlines, contract terms agreed | CLM (e.g. Intelagree) |
| **Signature** | Contract signed electronically | DocuSign / Intelagree |
| **Order** | Order created in system | ERP / Billing Platform |
| **Fulfilment** | Product/service provisioned | Internal ops systems |
| **Invoicing** | Invoice generated and sent | Billing Platform |
| **Payment** | Customer pays | Finance / ERP |
| **Revenue Rec** | Revenue recognised per accounting rules | Finance systems |

---

## Where Q2C Breaks Down — Most Common Failure Points

### 1. Configuration errors upstream
Incorrect product bundling or pricing in CPQ creates downstream 
billing errors that are expensive to fix post-signature.

**BA fix:** Define validation rules in CPQ. Build guided selling 
to prevent invalid combinations at source.

### 2. Manual handoffs between teams
Sales → Legal → Finance handoffs done via email create version 
control issues and lost context.

**BA fix:** Automate stage transitions with Salesforce workflows. 
Trigger tasks to the right team automatically.

### 3. Contract data doesn't flow to billing
Contract terms agreed in CLM don't sync to the billing system, 
causing invoicing errors.

**BA fix:** Map data fields end-to-end before build. 
Every field in the contract must have a destination system.

### 4. Approval bottlenecks
Large deals stall waiting for VP approval with no visibility 
on status.

**BA fix:** Build approval chain visibility into Salesforce. 
Automated reminders after 24hrs of inaction.

### 5. Renewal quoting done manually
Renewal team manually recreates quotes from scratch every cycle.

**BA fix:** Auto-generate renewal quotes 30-60 days before 
contract end. Default to flat renewal, flag exceptions.

---

## Key Metrics to Track

| Metric | What it tells you |
|---|---|
| **Quote-to-Close rate** | % of quotes that become won deals |
| **Average sales cycle length** | Time from opportunity to signature |
| **Quote turnaround time** | Time from request to quote sent |
| **Contract cycle time** | Time from quote sent to contract signed |
| **Order processing time** | Time from signature to fulfilment |
| **Invoice accuracy rate** | % of invoices with no errors |
| **Days Sales Outstanding (DSO)** | Time from invoice to payment |

---

## BA/PO Checklist for a Q2C Project

**Discovery phase:**
- [ ] Map the current state end-to-end — don't assume
- [ ] Identify every system involved and data owner
- [ ] Document all approval rules and thresholds
- [ ] Capture all exception handling (what breaks the happy path?)

**Requirements phase:**
- [ ] Define field-level data mapping across all systems
- [ ] Document all pricing rules, discount tiers, and approval logic
- [ ] Agree revenue recognition rules with Finance upfront
- [ ] Define integration error handling (what happens when sync fails?)

**UAT phase:**
- [ ] Test happy path end-to-end
- [ ] Test every approval threshold boundary
- [ ] Test failed payment and error recovery scenarios
- [ ] Have Finance validate revenue recognition output

---

*Part of the [BA Resources](README.md) collection · 
Star the repo if this helped ⭐*
