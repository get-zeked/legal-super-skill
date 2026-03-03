---
name: legal-super-skill
description: Comprehensive legal operations skill merging Perplexity Computer's 6 legal skills with Claude Code's writing, communications, and planning skills. Covers contract review, NDA triage, compliance (GDPR/CCPA), risk assessment, meeting briefings, canned responses, legal writing, internal communications, and structured planning. Use for contract analysis, NDA screening, compliance reviews, risk assessments, legal meeting prep, response drafting, or any legal operations work.
license: MIT
metadata:
  author: get-zeked
  version: '1.0'
---

# Legal Super-Skill

## Overview

This skill is the unified legal operations reference for in-house legal teams. It merges six Perplexity Computer legal skills (contract review, NDA triage, compliance, risk assessment, meeting briefings, canned responses) with Claude Code's writing quality, internal communications, structured planning, and verification-before-completion disciplines.

**Core principle:** Every legal output — contract redline, NDA classification, risk memo, compliance response, or meeting brief — must meet the same bar: specific, evidence-backed, actionable, and verifiable before it is delivered.

**Use this skill for:**
- Contract review and redline generation
- NDA screening and classification (GREEN / YELLOW / RED)
- GDPR, CCPA, and multi-jurisdictional privacy compliance
- Legal risk assessment and escalation decisions
- Meeting briefings and action item tracking
- Drafting templated and custom legal responses
- Internal legal communications (status reports, leadership updates, incident reports)
- Legal writing quality assurance and verification

---

## Section 1: Gap Analysis — Capability Coverage Table

The table below maps every major legal operations capability to its primary source skill and this document's section.

| Capability | Source Skill(s) | Section |
|---|---|---|
| Contract clause-by-clause review | legal-contract-review | §2 |
| Redline generation with rationale | legal-contract-review + writing-skills | §2 |
| Negotiation priority tiering | legal-contract-review | §2 |
| NDA structural screening | legal-nda-triage | §3 |
| NDA GREEN/YELLOW/RED classification | legal-nda-triage | §3 |
| NDA routing recommendations | legal-nda-triage | §3 |
| GDPR obligations and breach response | legal-compliance | §4 |
| CCPA/CPRA consumer rights handling | legal-compliance | §4 |
| DPA review checklist | legal-compliance | §4 |
| Data subject request (DSR) workflow | legal-compliance + legal-canned-responses | §4, §6 |
| Cross-border data transfer mechanisms | legal-compliance | §4 |
| Severity × Likelihood risk matrix | legal-risk-assessment | §5 |
| Risk register documentation | legal-risk-assessment | §5 |
| Outside counsel engagement criteria | legal-risk-assessment | §5 |
| Meeting briefing template | legal-meeting-briefing | §7 |
| Action item tracking | legal-meeting-briefing + writing-plans | §7 |
| Canned response templates (DSR, holds, NDA, subpoena) | legal-canned-responses | §6 |
| Escalation trigger identification | legal-canned-responses + legal-risk-assessment | §5, §6 |
| Internal comms (3P, newsletters, status) | internal-comms | §6 |
| Legal writing quality standards | writing-skills | §6 |
| Structured implementation planning | writing-plans | §7 |
| Verification before completion | verification-before-completion | §8 |
| Perplexity Computer-specific capabilities | All | §9 |

---

## Section 2: Contract Review & Redlining

### 2.1 Review Methodology

Before reviewing any contract:
1. **Identify contract type**: SaaS agreement, professional services, license, partnership, procurement, etc.
2. **Determine your side**: Vendor, customer, licensor, licensee, partner — this changes the entire analysis.
3. **Check for a playbook**: If the organization has a configured negotiation playbook, load it. If not, use commercially accepted standards as the baseline.
4. **Read the full contract before flagging issues.** Clauses interact. An uncapped indemnity may be partially offset by a broad limitation of liability.
5. **Analyze each material clause** against the playbook or baseline.
6. **Assess holistically**: Is the overall risk allocation balanced for the relationship?

### 2.2 Clause Analysis Checklist

#### Limitation of Liability
- [ ] Cap amount: fixed dollar, multiple of fees, or uncapped
- [ ] Mutual or asymmetric cap
- [ ] Carveouts from the cap (what remains uncapped)
- [ ] Consequential / indirect / punitive damages exclusion present
- [ ] Exclusion is mutual
- [ ] Carveouts from the exclusion (what remains capable of consequential damages)
- [ ] Cap applies per-claim, per-year, or aggregate

**Common issues:**
- Cap set at a fraction of fees (e.g., "fees paid in prior 3 months" on a low-value contract)
- Asymmetric carveouts favoring the drafter
- Carveouts so broad they eliminate the cap
- No consequential damages exclusion for one party's breaches

#### Indemnification
- [ ] Mutual or unilateral
- [ ] Trigger scope (IP infringement, data breach, bodily injury, warranty breach)
- [ ] Capped or uncapped
- [ ] Procedure: notice, right to control defense, right to settle
- [ ] Indemnitee mitigation obligation
- [ ] Relationship to limitation of liability clause

**Common issues:**
- Unilateral IP indemnification when both parties contribute IP
- Indemnification for "any breach" (converts liability cap to uncapped)
- No right to control defense of claims
- Unlimited survival of indemnification obligations

#### Intellectual Property
- [ ] Pre-existing IP ownership preserved for each party
- [ ] Ownership of IP developed during engagement (work-for-hire scope)
- [ ] License grants: scope, exclusivity, territory, sublicensing
- [ ] Open source considerations
- [ ] Feedback clause scope (grants on suggestions or improvements)

**Common issues:**
- Broad assignment capturing customer's pre-existing IP
- Work-for-hire extending beyond defined deliverables
- Unrestricted feedback clause granting perpetual irrevocable licenses

#### Data Protection
- [ ] DPA required and present
- [ ] Controller vs. processor classification correct
- [ ] Sub-processor rights and notification obligations
- [ ] Breach notification timeline (72 hours for GDPR)
- [ ] Cross-border transfer mechanisms (SCCs, adequacy decisions, BCRs)
- [ ] Data deletion/return obligations on termination
- [ ] Security requirements and audit rights
- [ ] Purpose limitation for processing

### 2.3 Deviation Severity Classification

#### GREEN — Acceptable
Clause aligns with or exceeds the organization's standard position. Minor variations that are commercially reasonable and do not materially increase risk.

**Action:** Note for awareness. No negotiation required.

#### YELLOW — Negotiate
Clause falls outside standard position but within a negotiable range. Requires attention and likely negotiation; not an escalation trigger.

**Action:** Generate specific redline language. Provide fallback position.

#### RED — Escalate
Clause falls outside acceptable range, triggers a defined escalation criterion, or poses material risk. Requires senior counsel review.

**Action:** Explain the specific risk. Provide market-standard alternative language. Estimate exposure.

### 2.4 Redline Generation Format

```
**Clause**: [Section reference and clause name]
**Current language**: "[exact quote from the contract]"
**Proposed redline**: "[specific alternative language]"
**Rationale**: [1-2 sentences explaining why]
**Priority**: [Must-have / Should-have / Nice-to-have]
**Fallback**: [Alternative position if primary redline is rejected]
```

### 2.5 Negotiation Priority Framework

#### Tier 1 — Must-Haves (Deal Breakers)
- Uncapped or materially insufficient liability protections
- Missing data protection requirements for regulated data
- IP provisions that jeopardize core assets
- Terms that conflict with regulatory obligations

#### Tier 2 — Should-Haves (Strong Preferences)
- Liability cap adjustments within range
- Indemnification scope and mutuality
- Termination flexibility
- Audit and compliance rights

#### Tier 3 — Nice-to-Haves (Concession Candidates)
- Preferred governing law
- Notice period preferences
- Minor definitional improvements

---

## Section 3: NDA Triage & Classification

### 3.2 GREEN / YELLOW / RED Classification Rules

#### GREEN — Standard Approval
- NDA is mutual (or unilateral in appropriate direction)
- All five standard carveouts present
- Term within standard range (1-3 years; 2-5 years survival)
- No non-solicitation, non-compete, or exclusivity provisions
- Standard remedies (no liquidated damages)

**Routing:** Approve via delegation of authority. Same-day turnaround.

#### YELLOW — Counsel Review Needed
- Definition broader than preferred but not unreasonable
- Term longer than standard but within market range
- Missing one standard carveout
- Minor asymmetry in a mutual NDA

**Routing:** Flag specific issues for counsel review. 1-2 business day turnaround.

#### RED — Significant Issues
- Missing critical carveouts (independent development or legal compulsion)
- Non-solicitation or non-compete embedded in NDA
- Exclusivity or standstill provisions
- Unreasonable term (10+ years or perpetual)
- IP assignment or license grant hidden in NDA

**Routing:** Full legal review. Do not sign. 3-5 business day turnaround.

---

## Section 4: Compliance & Privacy

### 4.1 GDPR Quick Reference

| Obligation | Requirement | Deadline |
|---|---|---|
| Lawful basis | Document basis for each processing activity | Before processing begins |
| Data subject rights | Access, rectification, erasure, portability | Within 30 days (+60 day extension) |
| Breach notification — authority | Notify supervisory authority | Within 72 hours |
| Breach notification — individuals | Notify affected individuals | Without undue delay if high risk |
| International transfers | SCCs, adequacy decisions, BCRs | Before transfer |

### 4.2 CCPA / CPRA Quick Reference

| Right | Acknowledgment | Substantive Response |
|---|---|---|
| Right to know | 10 business days | 45 calendar days (+45 extension) |
| Right to delete | 10 business days | 45 calendar days (+45 extension) |
| Right to opt-out | 15 business days | Immediate opt-out |
| Right to correct (CPRA) | 10 business days | 45 calendar days (+45 extension) |

---

## Section 5: Risk Assessment & Escalation

### 5.1 Severity × Likelihood Matrix

**Risk Score = Severity × Likelihood**

| Score Range | Risk Level | Action |
|---|---|---|
| 1-4 | Low Risk (GREEN) | Accept; monitor periodically |
| 5-9 | Medium Risk (YELLOW) | Mitigate; monitor actively |
| 10-15 | High Risk (ORANGE) | Escalate to senior counsel |
| 16-25 | Critical Risk (RED) | Immediate escalation; outside counsel |

---

## Section 6: Legal Writing & Canned Responses

Seven canned response templates included:
1. Data Subject Request (DSR) acknowledgment
2. Litigation hold notice
3. NDA routing response
4. Subpoena/legal process response
5. Regulatory inquiry response
6. Third-party data request response
7. Contract execution notice

---

## Section 7: Meeting Briefings & Implementation Planning

Meeting briefing template covers: attendees, agenda, legal context, open issues, action items with owners and deadlines.

---

## Section 8: Verification & QA

Gate function applied before every legal output delivery:
- Claim verification: every factual assertion sourced
- Completeness check: all required elements present
- Consistency check: no contradictions
- Actionability check: clear next steps

---

## Section 9: Perplexity Computer Capabilities

- Live legal research via 400+ integrations
- Real-time regulatory database access
- Document synthesis across multiple sources
- Scheduled monitoring for regulatory changes
- CRM integration for client/matter tracking

---

*Legal Super-Skill v1.0 — Merged from Perplexity Computer legal-contract-review, legal-nda-triage, legal-compliance, legal-risk-assessment, legal-meeting-briefing, legal-canned-responses, and Claude Code writing-skills, internal-comms, writing-plans, verification-before-completion skills.*
