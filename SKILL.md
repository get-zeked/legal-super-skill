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

**Common issues:**
- No DPA when personal data is processed
- Blanket sub-processor authorization without notification
- Breach notification timeline exceeding 72 hours
- No cross-border transfer protections
- Inadequate data deletion provisions

#### Term and Termination
- [ ] Initial term and renewal terms defined
- [ ] Auto-renewal provisions and notice periods
- [ ] Termination for convenience: available, notice period, early termination fees
- [ ] Termination for cause: cure period, definition of cause
- [ ] Effects of termination: data return, transition assistance, survival
- [ ] Wind-down period and obligations

**Common issues:**
- Long initial terms with no termination for convenience
- Auto-renewal with short notice windows (30 days for annual renewal)
- No cure period for termination for cause
- Survival clauses that effectively extend the agreement indefinitely

#### Governing Law and Dispute Resolution
- [ ] Choice of law (governing jurisdiction)
- [ ] Dispute resolution mechanism (litigation, arbitration, mediation)
- [ ] Venue and jurisdiction
- [ ] Arbitration rules and seat (if applicable)
- [ ] Jury waiver
- [ ] Class action waiver
- [ ] Prevailing party attorney's fees

**Common issues:**
- Unfavorable or unusual jurisdiction
- Mandatory arbitration with rules favorable to the drafter
- No escalation process before formal dispute resolution

### 2.3 Deviation Severity Classification

#### GREEN — Acceptable
Clause aligns with or exceeds the organization's standard position. Minor variations that are commercially reasonable and do not materially increase risk.

**Examples:**
- Liability cap at 18 months of fees when standard is 12 months
- Mutual NDA term of 2 years when standard is 3 years (shorter but reasonable)
- Governing law in a well-established commercial jurisdiction close to preferred

**Action:** Note for awareness. No negotiation required.

#### YELLOW — Negotiate
Clause falls outside standard position but within a negotiable range. Common in market but not preferred. Requires attention and likely negotiation; not an escalation trigger.

**Examples:**
- Liability cap at 6 months of fees when standard is 12 months
- Unilateral IP indemnification when standard is mutual
- Auto-renewal with 60-day notice when standard is 90 days

**Action:** Generate specific redline language. Provide fallback position. Estimate business impact of accepting vs. negotiating.

#### RED — Escalate
Clause falls outside acceptable range, triggers a defined escalation criterion, or poses material risk. Requires senior counsel review, outside counsel, or business decision-maker sign-off.

**Examples:**
- Uncapped liability or no limitation of liability clause
- Unilateral broad indemnification with no cap
- IP assignment of pre-existing IP
- No DPA when personal data is processed
- Non-compete or unreasonable exclusivity provisions

**Action:** Explain the specific risk. Provide market-standard alternative language. Estimate exposure. Recommend escalation path.

### 2.4 Redline Generation Format

For each redline, use this format:

```
**Clause**: [Section reference and clause name]
**Current language**: "[exact quote from the contract]"
**Proposed redline**: "[specific alternative language — additions in brackets, deletions struck through]"
**Rationale**: [1-2 sentences explaining why, suitable for external sharing]
**Priority**: [Must-have / Should-have / Nice-to-have]
**Fallback**: [Alternative position if primary redline is rejected]
```

### 2.5 Negotiation Priority Framework

#### Tier 1 — Must-Haves (Deal Breakers)
Issues where the organization cannot proceed without resolution:
- Uncapped or materially insufficient liability protections
- Missing data protection requirements for regulated data
- IP provisions that jeopardize core assets
- Terms that conflict with regulatory obligations

#### Tier 2 — Should-Haves (Strong Preferences)
Issues that materially affect risk but have negotiation room:
- Liability cap adjustments within range
- Indemnification scope and mutuality
- Termination flexibility
- Audit and compliance rights

#### Tier 3 — Nice-to-Haves (Concession Candidates)
Issues that improve position but can be conceded strategically:
- Preferred governing law (if alternative is acceptable)
- Notice period preferences
- Minor definitional improvements
- Insurance certificate requirements

**Negotiation strategy:** Lead with Tier 1. Trade Tier 3 concessions to secure Tier 2 wins. Never concede on Tier 1 without escalation.

### 2.6 Contract Review Output Template

```
## Contract Review Summary

**Contract**: [Name / type]
**Counterparty**: [Name]
**Your side**: [Vendor / Customer / etc.]
**Date reviewed**: [date]
**Reviewer**: [name / role]
**Overall risk level**: [GREEN / YELLOW / RED]

### Executive Summary
[2-3 sentences: overall assessment, top 3 issues, recommended action]

### Clause-by-Clause Analysis

| Clause | Classification | Issue Summary | Priority |
|---|---|---|---|
| [Section] | [GREEN/YELLOW/RED] | [brief issue] | [T1/T2/T3] |

### Redlines

[Formatted redlines per §2.4 — Tier 1 first]

### Recommended Next Steps
1. [Specific action — owner — deadline]
2. [Specific action — owner — deadline]
```

---

## Section 3: NDA Triage & Classification

### 3.1 Triage Checklist

Evaluate each NDA systematically against all criteria before classifying.

#### Agreement Structure
- [ ] Type identified: Mutual, Unilateral (disclosing party), or Unilateral (receiving party)
- [ ] Type appropriate for business relationship (mutual for exploratory discussions; unilateral for one-way disclosure)
- [ ] Standalone agreement (not embedded confidentiality clause in larger commercial agreement)

#### Definition of Confidential Information
- [ ] Reasonable scope — not "all information of any kind"
- [ ] Marking requirements workable (written marking within 30 days of oral disclosure is standard)
- [ ] Standard exclusions present (see §3.3)
- [ ] Does not define publicly available or independently developed materials as confidential

#### Obligations of Receiving Party
- [ ] Standard of care: reasonable care or same care as own confidential information
- [ ] Use restriction: limited to stated purpose
- [ ] Disclosure restriction: limited to need-to-know individuals bound by similar obligations
- [ ] No onerous obligations (physical logs, universal encryption)

#### Standard Carveouts (All Must Be Present for GREEN)
- [ ] Public knowledge: publicly available through no fault of receiving party
- [ ] Prior possession: known before disclosure
- [ ] Independent development: developed without reference to confidential information
- [ ] Third-party receipt: rightfully received from third party without restriction
- [ ] Legal compulsion: required by law/process, with notice where legally permitted

#### Permitted Disclosures
- [ ] Employees with need to know
- [ ] Contractors, advisors, professional consultants under similar obligations
- [ ] Affiliates (if needed for business purpose)
- [ ] Legal / regulatory disclosures

#### Term and Duration
- [ ] Agreement term reasonable (1-3 years standard)
- [ ] Confidentiality survival reasonable (2-5 years standard; trade secrets may warrant longer)
- [ ] Not perpetual (exception: qualifying trade secrets)

#### Return and Destruction
- [ ] Triggered on termination or request
- [ ] Return or destroy confidential information and copies
- [ ] Retention exception for legal/compliance/backup purposes
- [ ] Certification of destruction (affidavit is onerous — flag if required)

#### Remedies
- [ ] Injunctive relief acknowledgment present (standard)
- [ ] No liquidated damages
- [ ] Remedies apply equally to both parties (in mutual NDAs)

#### Problematic Provisions — Flag if Present
- [ ] Non-solicitation provisions (do not belong in NDAs)
- [ ] Non-compete provisions (do not belong in NDAs)
- [ ] Exclusivity or standstill provisions (absent M&A context)
- [ ] Residuals clause (flag; must be narrowly scoped if present)
- [ ] IP assignment or license grant
- [ ] Audit rights (unusual in standard NDAs)

#### Governing Law
- [ ] Reasonable, well-established commercial jurisdiction
- [ ] Governing law and jurisdiction in same/related jurisdictions
- [ ] No mandatory arbitration (litigation preferred for NDA disputes)

### 3.2 GREEN / YELLOW / RED Classification Rules

#### GREEN — Standard Approval

**ALL of the following must be true:**
- NDA is mutual (or unilateral in the appropriate direction)
- All five standard carveouts present
- Term within standard range (1-3 years agreement; 2-5 years survival)
- No non-solicitation, non-compete, or exclusivity provisions
- No residuals clause, or residuals clause is narrowly scoped to unaided memory only
- Reasonable governing law jurisdiction
- Standard remedies (no liquidated damages)
- Permitted disclosures include employees, contractors, advisors
- Return/destruction includes retention exception for legal/compliance
- Definition of confidential information is reasonably scoped

**Routing:** Approve via standard delegation of authority. No counsel review required. Same-day turnaround.

#### YELLOW — Counsel Review Needed

**One or more** of the following present, but NDA is not fundamentally problematic:
- Definition broader than preferred but not unreasonable
- Term longer than standard but within market range (e.g., 5-year agreement; 7-year survival)
- Missing one standard carveout that can be added without difficulty
- Residuals clause narrowly scoped to unaided memory
- Governing law acceptable but non-preferred jurisdiction
- Minor asymmetry in a mutual NDA
- Marking requirements present but workable
- Return/destruction lacks explicit retention exception (likely implied; should be added)

**Routing:** Flag specific issues for counsel review. Typical resolution: minor redlines in a single review pass. 1-2 business day turnaround.

#### RED — Significant Issues

**One or more** of the following present:
- Unilateral when mutual is required (or wrong direction)
- Missing critical carveouts (independent development or legal compulsion)
- Non-solicitation or non-compete embedded in NDA
- Exclusivity or standstill provisions without appropriate business context
- Unreasonable term (10+ years or perpetual without trade secret justification)
- Overbroad definition capturing public information or independently developed materials
- Broad residuals clause effectively licensing confidential information
- IP assignment or license grant hidden in NDA
- Liquidated damages or penalty provisions
- Audit rights without reasonable scope or notice
- Highly unfavorable jurisdiction with mandatory arbitration
- Document is not actually an NDA (contains substantive commercial terms)

**Routing:** Full legal review. Do not sign. Requires negotiation, counterproposal with standard form NDA, or rejection. 3-5 business day turnaround.

### 3.3 NDA Classification Summary Table

| Classification | Recommended Action | Timeline | Counsel Required? |
|---|---|---|---|
| GREEN | Approve per delegation of authority | Same day | No |
| YELLOW | Route to designated reviewer with specific issues flagged | 1-2 business days | Yes (limited review) |
| RED | Full review; prepare counterproposal or standard form | 3-5 business days | Yes (full review) |

### 3.4 Common NDA Issues and Standard Positions

| Issue | Standard Position | Risk if Unaddressed | Redline Approach |
|---|---|---|---|
| Overbroad definition of confidential information | Limit to non-public information disclosed for stated purpose, with clear exclusions | Over-claiming confidentiality; chilling business operations | Narrow to marked/identified CI or reasonably understood to be confidential |
| Missing independent development carveout | Must include: developed without reference to or use of disclosing party's CI | Claims that internally developed products derived from counterparty's CI | Add standard independent development carveout |
| Non-solicitation of employees | Does not belong in NDAs; appropriate in employment/M&A agreements | Restricts talent acquisition in ways unrelated to confidentiality | Delete entirely; if pushed, limit to targeted solicitation, 12-month term |
| Broad residuals clause | Resist; if required, limit to unaided memory, exclude trade secrets and patentable information, no IP license | Effectively grants license to use CI for any purpose | Add explicit exclusions for trade secrets and patentable information |
| Perpetual confidentiality obligation | 2-5 years from disclosure/termination (whichever later); trade secrets may warrant "as long as they remain trade secrets" | Indefinite legal obligations | Replace with defined term; offer trade secret carveout for qualifying information |

### 3.5 NDA Triage Output Template

```
## NDA Triage Summary

**Agreement**: [Name / description]
**Counterparty**: [Name]
**Purpose**: [Business context]
**Date triaged**: [date]
**Classification**: [GREEN / YELLOW / RED]

### Classification Rationale
[Specific criteria met or failed that drove the classification]

### Issues Identified

| # | Issue | Severity | Standard Position | Recommended Redline |
|---|---|---|---|---|
| 1 | [issue] | [Y/R] | [standard] | [redline] |

### Routing Recommendation
[Specific next step, person or role, timeline]

### Counterproposal Needed?
[Yes / No — if Yes, use organization's standard form NDA]
```

---

## Section 4: Compliance & Privacy

### 4.1 GDPR Quick Reference

**Scope:** Personal data of EU/EEA individuals, regardless of processor location.

| Obligation | Requirement | Deadline |
|---|---|---|
| Lawful basis | Document basis for each processing activity | Before processing begins |
| Data subject rights | Access, rectification, erasure, portability, restriction, objection | Within 30 days (extendable 60 days) |
| DPIA | Required for processing likely to result in high risk | Before high-risk processing begins |
| Breach notification — authority | Notify supervisory authority | Within 72 hours of becoming aware |
| Breach notification — individuals | Notify affected individuals | Without undue delay if high risk |
| Article 30 records | Maintain records of processing activities | Ongoing |
| International transfers | Appropriate safeguards (SCCs, adequacy decisions, BCRs) | Before transfer |
| DPO appointment | Required: public authorities; large-scale special category processing; large-scale systematic monitoring | Before qualifying processing begins |

**Lawful bases for processing:**
1. Consent (freely given, specific, informed, unambiguous)
2. Contract (necessary for performance or pre-contractual steps)
3. Legal obligation
4. Vital interests
5. Public task
6. Legitimate interests (requires balancing test; cannot override data subject rights)

### 4.2 CCPA / CPRA Quick Reference

**Scope:** Businesses collecting personal information of California residents meeting revenue, data volume, or data sale thresholds.

| Right | Description | Acknowledgment | Substantive Response |
|---|---|---|---|
| Right to know | Disclosure of PI collected, used, shared | 10 business days | 45 calendar days (+45 extension) |
| Right to delete | Deletion of personal information | 10 business days | 45 calendar days (+45 extension) |
| Right to opt-out | Opt out of sale/sharing of PI | 15 business days | N/A — immediate opt-out |
| Right to correct (CPRA) | Correct inaccurate PI | 10 business days | 45 calendar days (+45 extension) |
| Right to limit (CPRA) | Limit use of sensitive PI | 15 business days | N/A — immediate limit |
| Non-discrimination | Cannot discriminate for exercising rights | N/A | Ongoing obligation |

### 4.3 Multi-Jurisdiction Privacy Reference

| Regulation | Jurisdiction | Key Differentiators | Supervisory Authority |
|---|---|---|---|
| GDPR | EU/EEA | 72-hour breach notification; DPO requirement; SCCs for transfers | National DPAs; EDPB |
| UK GDPR | United Kingdom | Post-Brexit UK version; UK SCCs (IDTA); UK adequacy | ICO |
| CCPA/CPRA | California (USA) | Opt-out of sale/sharing; sensitive PI category; CPPA enforcement | CPPA |
| LGPD | Brazil | Similar to GDPR; ANPD enforcement; DPO required | ANPD |
| POPIA | South Africa | Information Regulator; mandatory operator agreements | Information Regulator |
| PIPEDA | Canada (federal) | Consent-based; OPC oversight; being modernized | OPC |
| PDPA | Singapore | Do Not Call registry; mandatory breach notification | PDPC |
| Privacy Act | Australia | Australian Privacy Principles; notifiable data breaches scheme | OAIC |
| PIPL | China | Strict cross-border transfer rules; data localization; CAC oversight | CAC |

### 4.4 DPA Review Checklist

#### Required Elements (GDPR Article 28)
- [ ] Subject matter and duration clearly defined
- [ ] Nature and purpose of processing specific
- [ ] Types of personal data identified
- [ ] Categories of data subjects identified
- [ ] Controller obligations and rights articulated

#### Processor Obligations
- [ ] Process only on documented controller instructions (with legal exception carved)
- [ ] Personnel confidentiality commitments
- [ ] Appropriate technical and organizational security measures (Article 32 reference)
- [ ] Sub-processor obligations:
  - [ ] Written authorization requirement (general or specific)
  - [ ] If general: notification of changes with right to object
  - [ ] Sub-processors bound by same obligations via written agreement
  - [ ] Processor remains liable for sub-processor performance
- [ ] Assistance with data subject rights requests
- [ ] Assistance with security, breach notification, DPIAs, and prior consultation
- [ ] Deletion or return of all personal data on termination (within defined timeline)
- [ ] Audit rights (direct audit + acceptance of third-party audit reports)
- [ ] Breach notification: without undue delay, ideally within 24-48 hours (enables controller to meet 72-hour regulatory deadline)

#### International Transfers
- [ ] Transfer mechanism identified (SCCs, adequacy, BCRs, other)
- [ ] If SCCs: using June 2021 version (not 2010 version)
- [ ] Correct SCC module selected (C2P, C2C, P2P, P2C)
- [ ] Transfer impact assessment completed for non-adequacy countries
- [ ] Supplementary measures documented if TIA identifies gaps
- [ ] UK IDTA addendum included if UK personal data in scope

#### Common DPA Issues

| Issue | Risk | Standard Position |
|---|---|---|
| Blanket sub-processor authorization without notification | Loss of control over processing chain | Require notification with right to object |
| Breach notification timeline > 72 hours | May prevent timely regulatory notification | Require notification within 24-48 hours |
| No direct audit rights | Cannot verify compliance | Accept SOC 2 Type II + right to audit upon cause |
| No data deletion timeline | Data retained indefinitely post-termination | Require deletion within 30-90 days of termination |
| No processing locations specified | Data could be processed anywhere | Require disclosure of processing locations |
| Outdated SCCs (2010 version) | Invalid transfer mechanism | Require current EU SCCs (2021 version) |

### 4.5 Data Subject Request Handling Workflow

#### Step 1: Intake and Identification
1. Identify the request type: access, rectification, erasure, restriction, portability, objection, opt-out, limit SPI
2. Identify applicable regulation(s) based on data subject location and organizational presence
3. Verify identity using reasonable measures proportionate to data sensitivity
4. Log the request immediately:

| Field | Content |
|---|---|
| Date received | [exact date] |
| Request type | [type] |
| Requester identity | [verified name] |
| Applicable regulation | [GDPR / CCPA / etc.] |
| Response deadline | [calculated from intake date] |
| Assigned handler | [name / role] |

#### Step 2: Check Exemptions Before Responding

Common exemptions to check:
- Active litigation hold covering this data (do NOT delete)
- Regulatory retention requirements (financial records, employment records, etc.)
- Legal claims defense or establishment
- Third-party rights that could be adversely affected
- Archiving in the public interest or scientific/historical research
- Freedom of expression (for erasure requests)

#### Step 3: Response Process
1. Gather all personal data of the requester across all applicable systems
2. Apply and document any exemptions
3. Prepare response: fulfill or explain why (in whole or in part) the request cannot be fulfilled
4. For denials: cite the specific legal basis
5. Include information about the right to lodge a complaint with the supervisory authority
6. Log the response and retain records of both request and response

#### Step 4: Response Timeline Reference

| Regulation | Initial Acknowledgment | Substantive Response | Extension Available |
|---|---|---|---|
| GDPR | Best practice: promptly | 30 days | +60 days with notice |
| CCPA/CPRA | 10 business days | 45 calendar days | +45 days with notice |
| UK GDPR | Best practice: promptly | 30 days | +60 days with notice |
| LGPD | Best practice: promptly | 15 days | Limited |

### 4.6 Compliance Escalation Criteria

Escalate to senior counsel or leadership when:
- A new regulation or guidance directly affects core business activities
- An enforcement action in the organization's sector signals heightened regulatory scrutiny
- A compliance deadline is approaching that requires organizational changes
- A data transfer mechanism the organization relies on is challenged or invalidated
- A regulatory authority initiates an inquiry or investigation involving the organization
- A data breach triggers regulatory notification obligations

---

## Section 5: Risk Assessment & Escalation

### 5.1 Severity × Likelihood Matrix

**Severity (impact if the risk materializes):**

| Level | Label | Description |
|---|---|---|
| 1 | Negligible | Minor inconvenience; no material financial, operational, or reputational impact |
| 2 | Low | Limited impact; minor financial exposure (< 1% of relevant contract/deal value) |
| 3 | Moderate | Meaningful impact; material financial exposure (1-5% of relevant value) |
| 4 | High | Significant impact; substantial financial exposure (5-25% of relevant value); likely public attention |
| 5 | Critical | Severe impact; major financial exposure (> 25% of value); fundamental business disruption; regulatory action likely |

**Likelihood (probability the risk materializes):**

| Level | Label | Description |
|---|---|---|
| 1 | Remote | Highly unlikely; no known precedent; requires exceptional circumstances |
| 2 | Unlikely | Could occur but not expected; limited precedent; requires specific triggering events |
| 3 | Possible | May occur; some precedent exists; triggering events are foreseeable |
| 4 | Likely | Probably will occur; clear precedent; triggering events are common |
| 5 | Almost Certain | Expected to occur; strong precedent or pattern; triggering events are present |

### 5.2 Risk Score Calculation

**Risk Score = Severity × Likelihood**

| Score Range | Risk Level | Color | Action |
|---|---|---|---|
| 1-4 | Low Risk | GREEN | Accept; monitor periodically |
| 5-9 | Medium Risk | YELLOW | Mitigate; monitor actively; assign owner |
| 10-15 | High Risk | ORANGE | Escalate to senior counsel; develop mitigation plan; brief leadership |
| 16-25 | Critical Risk | RED | Immediate escalation; engage outside counsel; establish response team |

### 5.3 Risk Matrix Visualization

```
                    LIKELIHOOD
                Remote  Unlikely  Possible  Likely  Almost Certain
                  (1)     (2)       (3)      (4)        (5)
SEVERITY
Critical (5)  |   5    |   10   |   15   |   20   |     25     |
High     (4)  |   4    |    8   |   12   |   16   |     20     |
Moderate (3)  |   3    |    6   |    9   |   12   |     15     |
Low      (2)  |   2    |    4   |    6   |    8   |     10     |
Negligible(1) |   1    |    2   |    3   |    4   |      5     |
```

### 5.4 Risk Level Recommended Actions

#### GREEN — Low Risk (Score 1-4)
- Accept: acknowledge risk and proceed with standard controls
- Document in risk register for tracking
- Include in periodic reviews (quarterly or annually)
- No escalation required

#### YELLOW — Medium Risk (Score 5-9)
- Implement specific controls or negotiate to reduce exposure
- Monitor actively at regular intervals (monthly or as triggers occur)
- Document risk, mitigations, and rationale in risk register
- Assign a specific owner
- Brief relevant business stakeholders
- Define trigger events that would elevate the risk level

#### ORANGE — High Risk (Score 10-15)
- Escalate to senior counsel; brief head of legal
- Develop a specific, actionable mitigation plan
- Brief relevant business leaders
- Review weekly or at defined milestones
- Consider outside counsel engagement
- Produce full risk memo (see §5.5 format)
- Define contingency plan if risk materializes

#### RED — Critical Risk (Score 16-25)
- Immediate escalation to General Counsel, C-suite, and/or Board as appropriate
- Engage outside counsel immediately
- Establish dedicated response team with clear roles
- Notify insurers if applicable
- Activate crisis management protocols if reputational risk involved
- Implement litigation hold if legal proceedings possible
- Daily or more frequent review until resolved
- Include in Board risk reporting
- Make any required regulatory notifications

### 5.5 Risk Assessment Memo Format

```
## Legal Risk Assessment

**Date**: [assessment date]
**Assessor**: [person conducting assessment]
**Matter**: [description]
**Privileged**: [Yes/No — mark attorney-client privileged if applicable]

### 1. Risk Description
[Clear, concise description of the legal risk]

### 2. Background and Context
[Relevant facts, history, and business context]

### 3. Risk Analysis

#### Severity Assessment: [1-5] — [Label]
[Rationale including potential financial exposure, operational impact, reputational considerations]

#### Likelihood Assessment: [1-5] — [Label]
[Rationale including precedent, triggering events, current conditions]

#### Risk Score: [Score] — [GREEN / YELLOW / ORANGE / RED]

### 4. Contributing Factors
[What factors increase the risk]

### 5. Mitigating Factors
[What factors decrease the risk or limit exposure]

### 6. Mitigation Options

| Option | Effectiveness | Cost/Effort | Recommended? |
|---|---|---|---|
| [Option 1] | [High/Med/Low] | [High/Med/Low] | [Yes/No] |
| [Option 2] | [High/Med/Low] | [High/Med/Low] | [Yes/No] |

### 7. Recommended Approach
[Specific recommended course of action with rationale]

### 8. Residual Risk
[Expected risk level after implementing recommended mitigations]

### 9. Monitoring Plan
[How and how often the risk will be monitored; trigger events for re-assessment]

### 10. Next Steps
1. [Action item 1 — Owner — Deadline]
2. [Action item 2 — Owner — Deadline]
```

### 5.6 Risk Register Entry Format

| Field | Content |
|---|---|
| Risk ID | Unique identifier |
| Date Identified | When risk was first identified |
| Description | Brief description |
| Category | Contract / Regulatory / Litigation / IP / Data Privacy / Employment / Corporate / Other |
| Severity | 1-5 with label |
| Likelihood | 1-5 with label |
| Risk Score | Calculated score |
| Risk Level | GREEN / YELLOW / ORANGE / RED |
| Owner | Person responsible for monitoring |
| Mitigations | Current controls in place |
| Status | Open / Mitigated / Accepted / Closed |
| Review Date | Next scheduled review |
| Notes | Additional context |

### 5.7 Outside Counsel Engagement Criteria

#### Mandatory Engagement
- Active litigation (any lawsuit filed against or by the organization)
- Government investigation (any inquiry from a regulator, government agency, or law enforcement)
- Criminal exposure (any matter with potential criminal liability)
- Securities issues (matters affecting securities disclosures or filings)
- Board-level matters requiring notification or approval

#### Strongly Recommended Engagement
- Novel legal issues or questions of first impression
- Jurisdictional complexity (unfamiliar jurisdictions or conflicting multi-jurisdictional requirements)
- Material financial exposure exceeding organizational risk tolerance thresholds
- Specialized expertise not available in-house (antitrust, FCPA, patent prosecution, etc.)
- Regulatory changes materially affecting the business requiring compliance program development
- M&A transactions: due diligence, deal structuring, regulatory approvals

#### Consider Engagement
- Complex contract disputes with material counterparties
- Employment claims (discrimination, harassment, wrongful termination, whistleblower)
- Data incidents that may trigger notification obligations
- IP infringement allegations involving material products or services
- Insurance coverage disputes
- Data breaches with potential regulatory exposure

---

## Section 6: Legal Writing & Communications

### 6.1 Writing Quality Standards

All legal outputs — contracts, memos, responses, briefings, reports — must meet these standards before delivery.

**Clarity:**
- One idea per sentence; one topic per paragraph
- Define technical terms on first use
- Avoid ambiguous pronouns ("it", "they", "this") when the referent is not clear
- Use active voice unless passive voice serves a specific purpose

**Specificity:**
- Provide exact language, not vague guidance
- Reference specific clause numbers, section headings, dates, and dollar amounts
- Every claim must be traceable to a source (document, regulation, precedent)

**Completeness:**
- State both the rule and its application to the specific facts
- Identify exceptions and carveouts that apply
- Include recommended actions with owners and deadlines

**Professionalism:**
- Tone calibrated to audience: peer counsel, business stakeholder, regulatory authority, or opposing party
- No language that could be read as threatening, dismissive, or inappropriately casual
- Privileged communications clearly marked

### 6.2 Internal Communications Formats

#### 3P Update (Progress / Plans / Problems)

Use for: weekly team updates, project status reports, leadership check-ins.

```
## [Team/Project Name] — [Date]

### Progress (What was accomplished)
- [Specific accomplishment — be concrete, not "worked on X"]
- [Specific accomplishment]

### Plans (What happens next)
- [Next action — include owner and timeline]
- [Next action — include owner and timeline]

### Problems (Blockers and risks)
- [Issue — include impact and what is needed to unblock]
- [Issue — include impact and what is needed to unblock]
```

#### Leadership Update

Use for: executive briefings, board reports, C-suite communications on legal matters.

```
## Legal Department Update — [Date]

### Summary
[2-3 sentence executive summary: top items, significant changes, actions required]

### Key Matters

| Matter | Status | Risk Level | Action Required? | Owner |
|---|---|---|---|---|
| [matter] | [status] | [G/Y/O/R] | [Yes/No] | [name] |

### Risk Highlights
[Changes to the top risks since last report; new risks identified]

### Regulatory Updates
[Material regulatory developments affecting the business]

### Resources / Escalations
[Budget variances, staffing issues, outside counsel spend, items needing executive decision]
```

#### Incident Report

Use for: data breaches, regulatory inquiries, litigation holds, compliance incidents.

```
## Incident Report — [Incident Name]

**Date/Time of Incident**: [date and time]
**Date/Time Discovered**: [date and time]
**Reporter**: [name / role]
**Classification**: [Data Breach / Regulatory Inquiry / Litigation / Compliance Incident]
**Severity**: [Critical / High / Medium / Low]

### What Happened
[Factual chronological account — no speculation, no conclusions]

### Scope and Impact
[Systems / data / individuals / jurisdictions affected]

### Immediate Actions Taken
1. [Action — who took it — when]
2. [Action — who took it — when]

### Regulatory Notification Obligations
| Regulation | Notification Required? | Deadline | Status |
|---|---|---|---|
| GDPR | [Yes/No/TBD] | [72 hours from awareness] | [Pending/Sent/N/A] |
| CCPA/CPRA | [Yes/No/TBD] | [Without undue delay] | [Pending/Sent/N/A] |
| [Other] | [Yes/No/TBD] | [applicable] | [status] |

### Open Questions
- [Unresolved factual or legal question — who is researching it]

### Next Steps
1. [Action — owner — deadline]
2. [Action — owner — deadline]

### Privilege Note
[This document is/is not protected by attorney-client privilege and/or work product doctrine]
```

### 6.3 Canned Response Templates

#### Template: Data Subject Request Acknowledgment

**Use when:** Any DSR received under GDPR, CCPA/CPRA, UK GDPR, or similar regulation.
**Do NOT use when:** Request is from a minor; involves data subject to litigation hold; requestor is in active litigation with the organization; request involves special category data with unusual sensitivity.

**Variables:** `{{requester_name}}`, `{{request_date}}`, `{{request_type}}`, `{{request_id}}`, `{{applicable_regulation}}`, `{{response_deadline}}`, `{{contact_email}}`

```
Subject: Your Data {{request_type}} Request — Reference {{request_id}}

Dear {{requester_name}},

We have received your request dated {{request_date}} regarding your personal data under {{applicable_regulation}}.

We are reviewing your request and will respond substantively by {{response_deadline}}.

If we need additional information to verify your identity or process your request, we will contact you.

To follow up on this request, please reference {{request_id}} and contact {{contact_email}}.

[Organization name]
```

**Follow-up actions:**
1. Log request in DSR tracker with all details
2. Verify identity using proportionate measures
3. Search all relevant systems for requester's personal data
4. Check for applicable exemptions (litigation hold, regulatory retention, etc.)
5. Calendar the response deadline

---

#### Template: DSR Fulfillment — Access Request

**Use when:** Identity verified; no exemptions apply; responding to access request.

**Variables:** `{{requester_name}}`, `{{request_id}}`, `{{applicable_regulation}}`, `{{data_summary}}`, `{{contact_email}}`, `{{supervisory_authority}}`

```
Subject: Response to Your Data Access Request — Reference {{request_id}}

Dear {{requester_name}},

In response to your request dated [original request date] under {{applicable_regulation}}, we are providing the following information about your personal data held by [Organization name]:

{{data_summary}}

[Attachment: personal data package]

If you believe any information is inaccurate or incomplete, you may submit a correction request.

You have the right to lodge a complaint with {{supervisory_authority}} if you are dissatisfied with our response.

For questions, contact {{contact_email}}.

[Organization name]
```

---

#### Template: DSR Denial (Partial or Full)

**Use when:** A recognized exemption applies to all or part of a DSR.
**Do NOT use when:** Denial basis is uncertain — escalate to counsel first.

**Variables:** `{{requester_name}}`, `{{request_id}}`, `{{applicable_regulation}}`, `{{denial_basis}}`, `{{supervisory_authority}}`, `{{contact_email}}`

```
Subject: Response to Your Data Request — Reference {{request_id}}

Dear {{requester_name}},

We have reviewed your request dated [original request date] under {{applicable_regulation}}.

[If partial denial: We are [fulfilling/unable to fulfill] [portion of] your request as follows:]

We are unable to [fulfill / fully fulfill] your request at this time because: {{denial_basis}}

You have the right to lodge a complaint with {{supervisory_authority}} regarding our response.

For questions, contact {{contact_email}}.

[Organization name]
```

---

#### Template: Litigation Hold Notice

**Use when:** Any matter requiring preservation of documents and ESI for potential or active litigation.
**CRITICAL:** Always mark attorney-client privileged. Always require acknowledgment. Obtain counsel review for criminal matters or uncertain preservation scope.

**Variables:** `{{custodian_name}}`, `{{matter_name}}`, `{{matter_reference}}`, `{{hold_scope}}`, `{{start_date}}`, `{{document_types}}`, `{{acknowledgment_deadline}}`, `{{legal_contact}}`

```
Subject: LEGAL HOLD NOTICE — {{matter_name}} — ACTION REQUIRED

PRIVILEGED AND CONFIDENTIAL
ATTORNEY-CLIENT COMMUNICATION

Dear {{custodian_name}},

You are receiving this notice because you may possess documents, communications, or data relevant to {{matter_name}} (Reference: {{matter_reference}}).

PRESERVATION OBLIGATION:
Effective immediately, you must preserve ALL documents and electronically stored information (ESI) related to:
- Subject matter: {{hold_scope}}
- Date range: {{start_date}} to present
- Document types: {{document_types}}

DO NOT delete, destroy, modify, overwrite, or discard any potentially relevant materials — including email, chat messages, documents, spreadsheets, database records, voicemails, and any other records.

This obligation applies even if documents are subject to routine disposal schedules. Please suspend any automatic deletion for potentially relevant materials.

ACKNOWLEDGMENT REQUIRED:
Please acknowledge receipt of this notice by {{acknowledgment_deadline}} by replying to this message.

Questions? Contact {{legal_contact}}.

[Legal team / Counsel name]
```

**Follow-up actions:**
1. Track acknowledgment receipts — follow up with non-respondents within 3 business days
2. Coordinate with IT to suspend auto-deletion for relevant systems
3. Log hold in matter management system
4. Set calendar for periodic hold reaffirmations (typically every 90-180 days)

---

#### Template: NDA Transmittal (Organization's Standard Form)

**Use when:** Sending the organization's standard NDA to a counterparty; responding to a RED-classified counterparty NDA with a counterproposal.

**Variables:** `{{counterparty_name}}`, `{{contact_name}}`, `{{purpose}}`, `{{legal_contact}}`, `{{execution_deadline}}`

```
Subject: Non-Disclosure Agreement — [Organization Name] / {{counterparty_name}}

Dear {{contact_name}},

Please find attached [Organization Name]'s standard Non-Disclosure Agreement for our [proposed / ongoing] discussions regarding {{purpose}}.

Our NDA is a mutual agreement providing equal protections to both parties. Key terms include:
- Mutual confidentiality obligations
- Standard exclusions (public information, independent development, prior possession, legal compulsion)
- [X]-year term with [Y]-year survival of confidentiality obligations
- Governing law: [jurisdiction]

Please review and return a countersigned copy by {{execution_deadline}} or contact {{legal_contact}} if you have questions or proposed modifications.

[Signature block]
```

---

#### Template: Subpoena Acknowledgment (DRAFT — Requires Counsel Review)

**CRITICAL:** Subpoena responses ALWAYS require individualized counsel review. This template is a starting framework only — never send without counsel sign-off.

**Variables:** `{{issuing_party}}`, `{{case_name}}`, `{{court}}`, `{{matter_reference}}`, `{{legal_contact}}`, `{{response_date}}`

```
[DRAFT — FOR COUNSEL REVIEW ONLY — DO NOT SEND WITHOUT APPROVAL]

Re: Subpoena — {{case_name}} — {{court}}

Dear [Issuing Counsel Name],

We have received the subpoena issued in the above-referenced matter dated [subpoena date].

[Organization Name] is reviewing the subpoena and will respond in accordance with applicable procedural rules.

[If objections: We intend to object to [portions of] the subpoena on the following grounds: [specify]]

[If requesting extension: We respectfully request an extension of [X] days to [date] to respond. Please confirm whether you will consent to this extension.]

All correspondence regarding this matter should be directed to {{legal_contact}}.

[Draft — not for transmission]
```

---

#### Template: Vendor Legal Question Response

**Use when:** Routine vendor inquiries about contract status, amendment requests, or compliance certifications.
**Do NOT use when:** Vendor is disputing contract terms; vendor threatens litigation or termination; response could affect ongoing negotiation.

**Variables:** `{{vendor_name}}`, `{{contact_name}}`, `{{inquiry_subject}}`, `{{agreement_name}}`, `{{response}}`, `{{legal_contact}}`

```
Subject: Re: {{inquiry_subject}} — {{agreement_name}}

Dear {{contact_name}},

Thank you for your inquiry regarding {{inquiry_subject}} in connection with the {{agreement_name}} between [Organization Name] and {{vendor_name}}.

{{response}}

For further questions, please contact {{legal_contact}}.

[Signature block]
```

---

### 6.4 Escalation Trigger Identification

Before generating any response, check for universal escalation triggers:

**Universal Escalation Triggers (Apply to All Templates)**
- Potential litigation or regulatory investigation involved
- Inquiry from a regulator, government agency, or law enforcement
- Response could create a binding legal commitment or waiver
- Potential criminal liability
- Media attention involved or likely
- Unprecedented situation (no prior handling by the team)
- Multiple jurisdictions with conflicting requirements
- Involves executive leadership or board members

**When an Escalation Trigger is Detected:**
1. STOP — do not generate a final response
2. Alert the user: identify the specific trigger detected and why it matters
3. Recommend the appropriate escalation path (senior counsel, outside counsel, specific role)
4. Offer a draft clearly marked "DRAFT — FOR COUNSEL REVIEW ONLY" rather than a final response

**Category-Specific Escalation Triggers:**

| Category | Additional Triggers |
|---|---|
| Data Subject Requests | Minor or request on behalf of a minor; data under litigation hold; requestor in active litigation; active HR matter; broad scope suggesting fishing expedition; special category data |
| Litigation Holds | Criminal exposure; unclear preservation scope; hold conflicts with regulatory deletion requirements; prior related holds exist; custodian objects to scope |
| Vendor Questions | Vendor disputing terms; vendor threatening litigation/termination; affects ongoing negotiation; involves regulatory compliance interpretation |
| Subpoena / Legal Process | ALWAYS requires counsel (template = starting point only); privilege issues; third-party data; cross-border production; unreasonable timeline |

---

## Section 7: Meeting Briefings & Action Tracking

### 7.1 Meeting Preparation Methodology

#### Step 1: Identify the Meeting
- Meeting title and type (deal review, board meeting, vendor call, regulatory discussion, litigation, cross-functional)
- Participants: roles and key interests
- Formal agenda (if available)
- Your role: advisor, presenter, negotiator, observer
- Available preparation time

#### Step 2: Assess Preparation Needs

| Meeting Type | Key Preparation Needs |
|---|---|
| Deal Review | Contract status, open issues, counterparty history, negotiation strategy, approval requirements |
| Board / Committee | Legal updates, risk register highlights, pending matters, regulatory developments, resolution drafts |
| Vendor Call | Agreement status, open issues, performance metrics, relationship history, negotiation objectives |
| Team Sync | Workload status, priority matters, resource needs, upcoming deadlines |
| Client / Customer | Agreement terms, support history, open issues, relationship context |
| Regulatory / Government | Matter background, compliance status, prior communications, counsel briefing |
| Litigation / Dispute | Case status, recent developments, strategy, settlement parameters |
| Cross-Functional | Legal implications of business decisions, risk assessment, compliance requirements |

#### Step 3: Gather Context
Sources to check: calendar, email, chat (Slack/Teams), document repositories, CLM system, CRM, prior meeting notes.

For each source:
- Calendar: meeting details, prior meetings with same participants, related meetings, competing commitments
- Email: recent correspondence, prior follow-up threads, open action items, shared documents
- Chat: recent discussions about the topic, messages from/about participants, team decisions
- Documents: agendas, prior notes, relevant agreements, memos, draft materials
- CLM: relevant contracts, open negotiation items, approval workflow status, amendment history
- CRM: account information, relationship history, deal stage, stakeholder map

#### Step 4: Synthesize Briefing
Organize gathered information into the standard briefing template (§7.2).

#### Step 5: Identify Preparation Gaps
Flag: unavailable sources, outdated information, unanswered questions, documents not located.

### 7.2 Meeting Briefing Template

```
## Meeting Brief

### Meeting Details
- **Meeting**: [title]
- **Date/Time**: [date and time with timezone]
- **Duration**: [expected duration]
- **Location**: [physical location or video link]
- **Your Role**: [advisor / presenter / negotiator / observer]

### Participants
| Name | Organization | Role | Key Interests | Notes |
|---|---|---|---|---|
| [name] | [org] | [role] | [what they care about] | [relevant context] |

### Agenda / Expected Topics
1. [Topic 1] — [brief context]
2. [Topic 2] — [brief context]
3. [Topic 3] — [brief context]

### Background and Context
[2-3 paragraph summary of relevant history, current state, and why this meeting is happening]

### Key Documents
- [Document 1] — [brief description and location]
- [Document 2] — [brief description and location]

### Open Issues
| Issue | Status | Owner | Priority | Notes |
|---|---|---|---|---|
| [issue] | [status] | [who] | [H/M/L] | [context] |

### Legal Considerations
[Specific legal issues, risks, or considerations relevant to meeting topics]

### Talking Points
1. [Key point to make, with supporting context]
2. [Key point to make, with supporting context]
3. [Key point to make, with supporting context]

### Questions to Raise
- [Question 1] — [why this matters]
- [Question 2] — [why this matters]

### Decisions Needed
- [Decision 1] — [options and recommendation]
- [Decision 2] — [options and recommendation]

### Red Lines / Non-Negotiables
[For negotiation meetings: positions that cannot be conceded]

### Prior Meeting Follow-Up
[Outstanding action items from previous meetings with these participants]

### Preparation Gaps
[Information that could not be found or verified; questions requiring user input]
```

### 7.3 Meeting-Type Specific Guidance

#### Deal Review Meetings
Additional briefing sections:
- **Deal summary**: Parties, deal value, structure, timeline
- **Contract status**: Current negotiation stage; outstanding issues
- **Approval requirements**: Required approvals and from whom
- **Counterparty dynamics**: Their likely positions, recent communications, relationship temperature
- **Comparable deals**: Prior similar transactions and their terms (if available)

#### Board and Committee Meetings
Additional briefing sections:
- **Legal department update**: Summary of new matters, wins, closures, significant developments
- **Risk highlights**: Top risks from risk register with changes since last report
- **Regulatory update**: Material regulatory developments affecting the business
- **Pending approvals**: Resolutions or approvals needed from the board/committee
- **Litigation summary**: Active matters, reserves, settlements, new filings

#### Regulatory / Government Meetings
Additional briefing sections:
- **Regulatory body context**: Division, current priorities, enforcement patterns
- **Matter history**: Prior interactions, submissions, correspondence timeline
- **Compliance posture**: Current compliance status on relevant topics
- **Counsel coordination**: Outside counsel involvement, prior advice received
- **Privilege considerations**: What can and cannot be discussed; any privilege risks

### 7.4 Action Item Tracking

#### Action Item Format

```
## Action Items from [Meeting Name] — [Date]

| # | Action Item | Owner | Deadline | Priority | Status | Dependencies |
|---|---|---|---|---|---|---|
| 1 | [specific, actionable task] | [name] | [date] | [H/M/L] | Open | [if any] |
| 2 | [specific, actionable task] | [name] | [date] | [H/M/L] | Open | [if any] |
```

#### Action Item Best Practices
- **Be specific**: "Send redline of Section 4.2 to counterparty counsel by Friday" — not "follow up on contract"
- **Single owner**: Every action item has exactly one owner — not a team or group
- **Hard deadline**: Every action item has a specific date — not "soon" or "ASAP"
- **Note dependencies**: If an action item depends on external input, state what is needed
- **Distinguish types**: Legal team actions vs. business team actions vs. external actions vs. follow-up meetings

#### Follow-Up Process
1. Distribute action items to all participants via email or appropriate channel
2. Set calendar reminders for all deadlines
3. Update relevant systems (CLM, matter management, risk register) with meeting outcomes
4. File meeting notes in the appropriate document repository
5. Flag urgent items needing immediate attention

#### Tracking Cadence
- **High priority**: Check daily until completed
- **Medium priority**: Check at next team sync or weekly review
- **Low priority**: Check at next scheduled meeting or monthly review
- **Overdue items**: Escalate to the owner and their manager; flag in next relevant meeting

### 7.5 Structured Legal Project Planning

Use this framework when planning multi-step legal projects, compliance programs, or negotiation campaigns.

**Project Plan Header:**

```
# [Project Name] — Legal Project Plan

**Goal**: [One sentence describing the outcome]
**Scope**: [What is included and excluded]
**Key Stakeholders**: [Names and roles]
**Timeline**: [Start and target completion]
**Risk Level**: [GREEN / YELLOW / ORANGE / RED]

---
```

**Task Structure:**

```
### Task [N]: [Deliverable Name]

**Owner**: [name]
**Deadline**: [date]
**Dependencies**: [prior tasks or external inputs required]
**Priority**: [T1 / T2 / T3]

**Steps**:
1. [Specific action with expected output]
2. [Specific action with expected output]
3. [Verification step — how to confirm completion]

**Done when**: [Specific, verifiable completion criteria]
```

**Planning principles:**
- Each task must have a single owner and a hard deadline
- State the "done when" criteria before starting the task (evidence before claims)
- DRY: Do not duplicate task descriptions; cross-reference earlier tasks
- Frequent checkpoints: build in review steps; do not plan long unverified stretches
- Document decisions made during planning so they are not relitigated during execution

---

## Section 8: Verification & Quality Assurance

### 8.1 The Iron Law

```
NO LEGAL OUTPUT DELIVERED WITHOUT VERIFICATION
```

Claiming a contract review is complete, an NDA is classified, a risk assessment is done, or a response is ready — without checking your own work — is not efficiency. It is error.

**Core principle:** Evidence before claims, always.

**Violating the letter of this rule is violating the spirit of this rule.**

### 8.2 The Gate Function

Before delivering any legal output:

```
1. IDENTIFY: What check proves this output is complete and accurate?
2. REVIEW: Re-read the output against the source document or requirements
3. CHECK: Does the output address everything it claims to address?
   - Are all relevant clauses analyzed?
   - Are all required checklist items covered?
   - Are all citations accurate?
   - Are all deadlines correctly calculated?
4. VERIFY: Does the output meet the applicable standard?
   - If NO: Correct it before delivering
   - If YES: Document that the check was performed
5. ONLY THEN: Deliver the output
```

### 8.3 Legal Output Verification Checklist

Use this checklist before delivering any legal output:

**For Contract Reviews:**
- [ ] Every material clause analyzed (not just flagged ones)
- [ ] Deviation classification (GREEN/YELLOW/RED) applied consistently
- [ ] All redlines include exact replacement language (not vague directions)
- [ ] All redlines include rationale suitable for external sharing
- [ ] Tier 1 / T2 / T3 priorities assigned
- [ ] Output includes recommended next steps with owners and deadlines
- [ ] Governing law and jurisdiction reviewed
- [ ] Data protection obligations reviewed

**For NDA Triage:**
- [ ] All 10 checklist categories evaluated (§3.1)
- [ ] All five standard carveouts checked
- [ ] All problematic provisions checked
- [ ] Classification supported by specific checklist findings
- [ ] Routing recommendation is specific (person or role, timeline)
- [ ] RED classifications include counterproposal recommendation

**For Compliance and DSR Responses:**
- [ ] Applicable regulation(s) correctly identified for data subject's location
- [ ] Response deadline correctly calculated from intake date
- [ ] Identity verification documented
- [ ] All relevant systems searched for data subject's personal information
- [ ] All applicable exemptions checked
- [ ] Denial basis (if applicable) cites specific legal provision
- [ ] Right to lodge complaint with supervisory authority included

**For Risk Assessments:**
- [ ] Severity and likelihood rated separately (not collapsed)
- [ ] Risk score calculated correctly (S × L)
- [ ] Risk level classification applied consistently with §5.2 table
- [ ] Mitigation options include more than one option
- [ ] Residual risk stated (what remains after mitigations)
- [ ] Monitoring plan includes specific trigger events for re-assessment
- [ ] Next steps include owners and deadlines

**For Meeting Briefings:**
- [ ] All available sources checked for preparation
- [ ] Preparation gaps explicitly flagged (not silently omitted)
- [ ] Legal considerations section is specific to the meeting's topics
- [ ] Red lines / non-negotiables populated for negotiation meetings
- [ ] Prior meeting follow-up included

**For Canned Responses:**
- [ ] All `{{variables}}` replaced with actual content
- [ ] Jurisdiction-specific regulations and timelines verified
- [ ] Escalation triggers checked before finalizing
- [ ] Privilege marking applied if communication is attorney-client
- [ ] Follow-up actions identified

### 8.4 Red Flags — STOP Before Delivering

These are signals that verification has been skipped or is inadequate:

- Using "should", "probably", "seems to", "I believe" when describing what a clause says — go re-read it
- Expressing satisfaction before re-reading the output ("Looks good", "That covers it")
- Calculating a deadline from memory rather than from the intake date
- Citing a regulatory provision without confirming the citation is current
- Delivering a response that uses a template without confirming all variables are replaced
- Omitting a section of the checklist because the clause "seemed" standard
- Classifying an NDA without completing all 10 checklist categories in §3.1

### 8.5 Rationalization Prevention

| Excuse | Reality |
|---|---|
| "The clause is standard — I know what it says" | Read it. Standard clauses get modified. |
| "I reviewed this type of contract before" | You reviewed a different contract. Review this one. |
| "The deadline is obviously X days from today" | Calculate it explicitly. Off-by-one errors matter. |
| "I'll check the regulation later" | Check it now or flag the uncertainty explicitly. |
| "The client is in a hurry" | Urgency increases error risk. Do not skip verification. |
| "It's just a canned response" | Templates with un-replaced variables go to real people. |
| "I'm confident in the classification" | Confidence is not a check. Run the checklist. |
| "I already read it once" | One read is not a verification. The verification checklist is. |

---

## Section 9: Unique Perplexity Computer Capabilities

Perplexity Computer provides capabilities that are not available in standard legal AI tools. This section describes how to leverage them in legal operations workflows.

### 9.1 Connected Source Integration for Meeting Prep

Perplexity Computer can pull context directly from connected sources before generating a meeting brief. When available:

- **Calendar integration**: Automatically surfaces prior meetings with the same participants, related scheduled meetings, and competing time commitments — without requiring manual input from the user
- **Email integration**: Surfaces recent correspondence, prior follow-up threads, and open action items from prior interactions with the counterparty
- **Chat integration (Slack, Teams)**: Surfaces team discussions about the matter, informal decisions, and context shared in channels that would not appear in formal email
- **Document repository integration (Box, Egnyte, SharePoint)**: Locates relevant agreements, memos, briefings, and drafts without requiring the user to specify document names
- **CLM integration**: Surfaces contract status, negotiation history, approval workflow, amendment history, and open items for the counterparty directly from the contract lifecycle management system
- **CRM integration**: Surfaces account information, deal stage, relationship history, and stakeholder maps

**How to use:** When asking for a meeting brief, specify which meeting and ask Perplexity Computer to check connected sources. It will surface relevant context and flag preparation gaps explicitly.

### 9.2 Real-Time Regulatory Research

Perplexity Computer can search the web for current regulatory guidance, enforcement actions, and legislative developments. Use this for:

- Verifying that a regulatory provision cited in a contract or compliance analysis is current and has not been amended
- Researching how a supervisory authority (ICO, CNIL, FTC, state AGs) has interpreted a specific requirement in recent guidance or enforcement actions
- Checking whether an adequacy decision or SCC version is still valid
- Monitoring for new privacy laws or amendments in jurisdictions relevant to the organization's processing activities

**How to use:** Ask Perplexity Computer to search for current guidance on a specific regulatory topic. It will surface sources with citations and flag when guidance may be stale.

### 9.3 Multi-Document Synthesis for Due Diligence

Perplexity Computer can analyze multiple documents simultaneously, which is useful for:

- Comparing contract terms across a portfolio of agreements with the same counterparty to identify inconsistencies
- Cross-referencing a DPA against the main services agreement to identify conflicts
- Reviewing multiple NDAs received in an M&A transaction context against a consistent screening checklist
- Synthesizing compliance obligations across multiple jurisdictions into a single comparison table

**How to use:** Provide multiple documents and ask for a comparative analysis. Perplexity Computer will cross-reference the documents and flag conflicts, gaps, and inconsistencies.

### 9.4 Structured Output Generation for Legal Workflows

Perplexity Computer generates structured, formatted outputs that integrate into legal workflows:

- **Redline packages**: Formatted redlines ready for insertion into negotiation communications
- **Risk register entries**: Pre-formatted entries ready to paste into the organization's risk register
- **Action item tables**: Formatted action item tables ready for distribution after meetings
- **Template-filled responses**: Canned response templates with all variables populated, ready for counsel review and signature
- **Briefing documents**: Structured meeting briefs formatted for sharing with meeting participants

### 9.5 Tone and Audience Calibration

Perplexity Computer calibrates tone and language for the specific audience of each legal communication:

| Audience | Tone | Language |
|---|---|---|
| External counterparty counsel | Professional, firm, collegial | Legal terminology; expect it to be understood |
| Business stakeholders | Clear, direct, non-technical | Plain language; minimize jargon; focus on business impact |
| Regulatory authority | Formal, respectful, precise | Regulatory terminology; citations to specific provisions |
| Opposing party (adversarial) | Measured, professional, non-concessive | Carefully qualified; no admissions; counsel-reviewed |
| Board / executives | Executive-level, strategic | Headlines first; decision-oriented; quantified where possible |
| Employees (hold notices) | Clear, authoritative, non-alarming | Direct obligations; specific instructions; contact for questions |

**How to use:** Specify the audience when requesting a legal communication. Perplexity Computer will calibrate the tone accordingly and flag if the requested tone seems mismatched to the situation.

### 9.6 Verification Integration

Perplexity Computer applies the verification-before-completion standard (§8) automatically to all legal outputs. This means:

- Every classification (GREEN/YELLOW/RED for contracts and NDAs) is supported by checklist findings, not asserted without evidence
- Every deadline in a compliance response is calculated from the stated intake date, not asserted from memory
- Every regulatory citation is verified against current guidance before inclusion
- Every canned response is checked for un-replaced `{{variables}}` before delivery
- Every meeting brief explicitly flags preparation gaps rather than silently omitting unavailable information

If a verification check cannot be completed (e.g., a source is unavailable), Perplexity Computer flags this explicitly in the output rather than proceeding without it.

---

## Quick Reference Cards

### Contract Review Quick Decision

```
Is the clause within standard position?
├── YES → GREEN (no redline needed)
├── WITHIN NEGOTIABLE RANGE → YELLOW (generate redline + fallback)
└── OUTSIDE ACCEPTABLE RANGE → RED (escalate + market standard language)

Is the risk exposure material?
├── Uncapped liability → RED (Tier 1 must-have)
├── Missing DPA for personal data → RED (Tier 1 must-have)
├── IP assignment of pre-existing IP → RED (Tier 1 must-have)
└── Everything else → apply severity × likelihood (§5.1)
```

### NDA Quick Classification Decision

```
Missing critical carveouts (independent development, legal compulsion)?
└── YES → RED

Non-solicitation, non-compete, or exclusivity provisions present?
└── YES → RED

Term perpetual or 10+ years without trade secret justification?
└── YES → RED

IP assignment or license grant hidden in NDA?
└── YES → RED

All five standard carveouts present?
└── NO (one missing) → YELLOW (at minimum)

All other criteria within standard range?
└── YES → GREEN
└── ONE or more outside standard range → YELLOW
```

### DSR Response Timeline Quick Reference

```
GDPR:         Substantive response → 30 days from receipt
              Extension available → +60 days with notice to requester
CCPA/CPRA:    Acknowledgment → 10 business days from receipt
              Substantive response → 45 calendar days
              Extension available → +45 days with notice
UK GDPR:      Same as GDPR
LGPD:         Substantive response → 15 days
```

### Risk Score Quick Reference

```
Score 1-4   → GREEN  → Accept; monitor periodically
Score 5-9   → YELLOW → Mitigate; assign owner; brief stakeholders
Score 10-15 → ORANGE → Escalate to senior counsel; develop mitigation plan
Score 16-25 → RED    → Immediate escalation; engage outside counsel
```

### Outside Counsel: When to Engage

```
MANDATORY: Active litigation, government investigation, criminal exposure, securities issues, board-level matters
STRONGLY RECOMMENDED: Novel legal issues, material financial exposure, specialized expertise needed, M&A
CONSIDER: Complex contract disputes, employment claims, data incidents, IP infringement, insurance disputes
```

---

## Common Mistakes and Fixes

| Mistake | Fix |
|---|---|
| Classifying a contract clause without reading the full contract first | Read the full contract before flagging any issues — clauses interact |
| Using the NDA triage checklist selectively (only checking "obvious" issues) | Complete all 10 checklist categories for every NDA, regardless of how standard it appears |
| Calculating a DSR deadline from "today" rather than from the actual intake date | Always calculate from the documented intake date; verify against the applicable regulation's timeline |
| Sending a canned response with un-replaced `{{variables}}` | Check every `{{variable}}` before delivering any templated response |
| Assigning a risk score without rating severity and likelihood separately | Rate S and L independently, then multiply; do not collapse them into a single intuitive rating |
| Omitting preparation gaps in a meeting brief | Explicitly flag every source that could not be checked and every question that could not be answered |
| Delivering a redline without a rationale | Every redline must include a rationale suitable for external sharing to the counterparty |
| Using a template for a situation with an escalation trigger | Check universal and category-specific triggers before using any template |
| Marking a response as complete when actions have been identified but not assigned | Every action item needs a single owner and a hard deadline before the output is complete |

---

## Metadata

**Skill version:** 1.0
**Author:** get-zeked
**Source skills merged:**
- Perplexity Computer: legal-contract-review, legal-nda-triage, legal-compliance, legal-risk-assessment, legal-meeting-briefing, legal-canned-responses
- Claude Code (obra/superpowers): writing-skills, internal-comms, writing-plans, verification-before-completion
**License:** MIT

---

## Section 10: Extended Templates & Checklists

### 10.1 Contract Review Playbook Baseline

When no organizational playbook is configured, use these baseline positions for common SaaS / commercial agreement clauses.

| Clause | Baseline Position (Customer-Side) | Baseline Position (Vendor-Side) |
|---|---|---|
| Liability cap | 12 months of fees paid | 12 months of fees paid |
| Consequential damages exclusion | Mutual exclusion with carveouts for: confidentiality breach, IP infringement, fraud, willful misconduct | Mutual exclusion with carveouts for: confidentiality breach, IP infringement, fraud, willful misconduct |
| IP infringement indemnification | Vendor indemnifies customer for third-party IP claims arising from vendor's software | Customer indemnifies vendor for third-party IP claims arising from customer's modifications or data |
| Data protection | DPA required; 24-48 hour breach notification to controller; right to object to sub-processors; data deletion within 30 days of termination | DPA required; 24-48 hour breach notification to controller; right to object to sub-processors |
| Term | 1-year initial term; 12-months notice for annual renewal | 1-year initial term; 30-days notice for annual renewal |
| Termination for cause | 30-day cure period for material breach | 30-day cure period for material breach |
| Termination for convenience | Customer: yes, with 30-days notice; pro-rated refund of prepaid fees | Vendor: yes, with 90-days notice |
| Governing law | Customer's principal place of business | Vendor's principal place of business |
| Dispute resolution | Mediation first; then litigation in customer's preferred forum | Mediation first; then litigation in vendor's preferred forum |
| Assignment | Neither party may assign without consent; change of control exception for acquirer | Vendor may assign to affiliate or acquirer; customer may not assign without consent |
| Service levels | SLAs with defined uptime (99.9%+); credit remedies; right to terminate for repeated failures | SLAs with defined uptime; credit remedies |
| Security | SOC 2 Type II annual certification; right to audit on reasonable notice or for cause | SOC 2 Type II annual certification; accept third-party audit reports |

### 10.2 Data Breach Response Checklist

Use immediately upon becoming aware of a potential data breach or security incident.

#### Hour 0-4: Initial Assessment
- [ ] Contain the breach: isolate affected systems, revoke compromised credentials
- [ ] Preserve evidence: do NOT delete, overwrite, or modify any logs, records, or systems involved
- [ ] Notify incident response team: legal, security, IT, communications, executive sponsor
- [ ] Open a dedicated matter in the matter management system
- [ ] Mark all communications attorney-client privileged where applicable

#### Hour 4-24: Scoping and Classification
- [ ] Identify type of data affected: personal data, health data, financial data, trade secrets, regulated data
- [ ] Identify categories of data subjects: employees, customers, third parties
- [ ] Identify jurisdictions implicated by data subjects' locations
- [ ] Estimate number of records / individuals affected (approximate ranges are acceptable at this stage)
- [ ] Assess whether incident is "personal data breach" under GDPR / applicable regulation
- [ ] Assess likelihood of risk to rights and freedoms of individuals (GDPR threshold for notification)
- [ ] Identify whether a litigation hold is required
- [ ] Notify cyber insurance carrier if applicable

#### Hour 24-72: Regulatory Notification Decision
- [ ] GDPR: If personal data breach confirmed, notification to supervisory authority required within 72 hours of becoming aware unless unlikely to result in risk to individuals. Document the decision with evidence.
- [ ] UK GDPR: Same as GDPR; notify ICO within 72 hours
- [ ] US state breach notification laws: Assess notification requirements in each state where affected individuals are resident (timing varies: 30-72 hours in many states; up to 90 days in a few)
- [ ] HIPAA: If PHI involved, notify HHS; determine whether notification to individuals required
- [ ] PCI DSS: If payment card data involved, notify card brands and acquiring bank
- [ ] Sector-specific: Financial services, telecommunications, healthcare, education may have additional requirements

#### Supervisory Authority Notification Content (GDPR Article 33)
Required elements if notification is made:
1. Nature of personal data breach including categories and approximate number of data subjects and records
2. Contact details of data protection officer or other contact point
3. Likely consequences of the personal data breach
4. Measures taken or proposed to address the breach, including measures to mitigate its possible adverse effects

Note: Article 33(4) allows notification "in phases" where all information is not yet available — submit what is known and supplement.

#### Post-72 Hours: Individual Notification Decision
- [ ] GDPR Article 34: Notify affected individuals without undue delay if breach is "likely to result in a high risk to the rights and freedoms" of individuals
- [ ] Assess whether any Article 34(3) exceptions apply: measures making data unintelligible (encryption); disproportionate effort (public communication alternative); risk no longer likely to materialize
- [ ] If individual notification required: prepare notice with required elements (nature of breach; DPO contact; likely consequences; measures taken)
- [ ] CCPA/CPRA: Notify affected California residents in most expedient time possible and without unreasonable delay
- [ ] US state laws: Follow jurisdiction-specific timing and content requirements

### 10.3 Compliance Calendar — Common Annual Obligations

This calendar lists recurring compliance obligations that should be tracked annually. Populate with organization-specific dates.

| Obligation | Typical Timing | Regulation | Owner | Notes |
|---|---|---|---|---|
| Privacy notice review | Annual | GDPR Art. 12-14; CCPA | Privacy team / Legal | Update for any new processing activities added during the year |
| Article 30 records update | Annual (or when processing changes) | GDPR Art. 30 | Legal / Privacy | Ensure all new processing activities documented |
| DPA audit: active vendor DPAs | Annual | GDPR Art. 28 | Legal / Procurement | Review top vendors by data volume; update outdated SCCs |
| Consent mechanism audit | Annual | GDPR Art. 6-7; CCPA | Product / Legal | Verify consent flows are lawful; cookie consent update |
| Data mapping / inventory update | Annual | GDPR; CCPA | Legal / Privacy / IT | Reconcile inventory against actual processing |
| DPIA review: existing high-risk processing | Annual | GDPR Art. 35 | Legal / Privacy | Re-assess previously conducted DPIAs |
| Security assessment: Article 32 measures | Annual | GDPR Art. 32 | Legal / IT Security | Review TOMs; incorporate new threats |
| Sub-processor list update | Quarterly | GDPR Art. 28 | Legal / IT | Publish updated sub-processor list to customers |
| Privacy training | Annual | GDPR; CCPA | Legal / HR | All staff handling personal data |
| Outside counsel panel review | Annual | Internal governance | General Counsel | Assess performance; update panel agreements |
| Contract template review | Annual | Internal governance | Legal | Update standard templates for regulatory changes and lessons learned |
| Insurance coverage review | Annual | Risk management | Legal / Finance | Confirm cyber, D&O, E&O, and general liability are current |
| Regulatory monitoring briefing | Quarterly | All applicable | Legal | Brief leadership on material regulatory developments |
| Risk register review | Quarterly | Internal governance | Legal | Re-assess open risks; close resolved matters |

### 10.4 Legal Team Internal FAQ Template

Use this template to draft FAQ responses for common recurring legal questions from internal business teams.

**Template structure for each FAQ entry:**

```
## FAQ: [Question as asked by the business]

**Short answer**: [1-2 sentences — the bottom line the business team needs]

**Explanation**:
[3-5 sentences explaining the rule, its rationale, and how it applies]

**Common scenarios**:
- [Scenario 1]: [applies / does not apply / depends on X]
- [Scenario 2]: [applies / does not apply / depends on X]
- [Scenario 3]: [applies / does not apply / depends on X]

**When to involve Legal**:
[Specific triggers for escalation beyond self-service]

**Reference**:
[Applicable regulation, policy, or playbook section]
```

**Example: Do we need an NDA before sharing our product roadmap with a prospect?**

**Short answer**: Yes, in most cases. Share product roadmap details only under a signed NDA.

**Explanation**: A product roadmap contains non-public, confidential information about future development plans. Sharing it without a confidentiality agreement creates legal risk: the prospect may use the information competitively, disclose it to third parties, or claim it as background for later patent or IP disputes. A signed NDA establishes clear obligations.

**Common scenarios**:
- Prospect requests a roadmap overview during an early sales call: Confirm NDA is signed before sharing. If not signed, provide only high-level directional information already public.
- Existing customer asks about roadmap for renewal planning: Review the master agreement — many include confidentiality provisions that cover this. If not, use a short NDA addendum.
- Strategic partner with existing NDA asks for roadmap details: Verify the NDA covers the purpose (business discussions about future product features) before sharing.

**When to involve Legal**: The prospect is a competitor; the NDA is expired; you are sharing source code or technical architecture details; the sharing is for a joint development or partnership discussion.

**Reference**: NDA Triage section (§3); organization's confidentiality policy.

---

**Example: When does a vendor become a "data processor" under GDPR and what does that mean for our contracts?**

**Short answer**: A vendor is a data processor if they process personal data on your behalf and under your instructions. You need a Data Processing Agreement (DPA) with them.

**Explanation**: Under GDPR Article 28, a data processor is any entity that processes personal data on behalf of the data controller (that is, your organization) and following your instructions. "Processing" is broad — it includes storing, accessing, analyzing, or transmitting personal data. If a vendor touches personal data of your customers, employees, or other data subjects, and they do so in order to provide services to you, they are a processor.

**Common scenarios**:
- Cloud infrastructure provider (AWS, Azure, GCP) hosting systems containing personal data: Processor — DPA required.
- Marketing automation platform with access to customer contact data: Processor — DPA required.
- Outside counsel reviewing HR data in connection with litigation: Generally a separate controller for their own professional purposes — processor analysis may not apply, but data sharing provisions should be addressed contractually.
- Industry analyst receiving anonymized, aggregated data with no ability to re-identify individuals: Not a processor if data is truly anonymized — but verify anonymization is robust.

**When to involve Legal**: You are uncertain whether the data is personal data; you are uncertain whether the vendor's processing is on your behalf or for their own purposes; the vendor is processing health, biometric, or special category data; the vendor is located outside the EEA.

**Reference**: DPA Review Checklist (§4.4); GDPR Article 28.

### 10.5 Legal Communications Tone Guide

Different legal communications require calibrated tone. This guide provides examples and anti-examples for each audience type.

#### Peer External Counsel

**Goal**: Professional, collegial, and firm. You are both legal professionals working toward a resolution on behalf of your respective clients.

**Do:**
- Use legal terminology without over-explaining
- Be direct about your client's position while leaving room for negotiation
- Acknowledge reasonable positions in their draft before explaining your concerns
- Propose specific alternative language rather than just objecting

**Avoid:**
- Aggressive or adversarial language except in formal legal proceedings
- Condescension or implication that their position is unreasonable
- Vague objections without proposed solutions
- Promises or commitments that are not authorized

**Example:**
> "Thank you for sending the revised draft. We have reviewed Section 12 and have a concern with the liability cap as currently drafted — the 'fees paid in the prior 90 days' formulation would result in a very low cap for a first-year engagement. We'd propose a cap of 12 months of fees paid, or alternatively a fixed dollar floor of $[X]. Happy to discuss."

**Anti-example:**
> "The liability cap in Section 12 is completely unacceptable and inconsistent with market standards."

---

#### Business Stakeholders (Internal)

**Goal**: Clear, direct, and decision-oriented. Business teams want to know what the risk is, what the options are, and what Legal recommends.

**Do:**
- Lead with the bottom line (recommendation first, analysis second)
- Quantify risk in business terms where possible
- Present options with clear trade-offs, not just a list of concerns
- Use plain language; minimize legal jargon

**Avoid:**
- Long analytical sections before reaching a conclusion
- "It depends" as an answer without specifying what it depends on
- Listing every theoretical risk without prioritizing
- Legal jargon that obscures the business impact

**Example:**
> "Bottom line: we should sign this contract. The vendor's indemnification for IP claims is unilateral rather than mutual, which is a Yellow issue for us — it's common in the market, and we'd prefer mutual, but it's not a deal breaker. I'd suggest asking for mutual IP indemnification in our next email; if they push back, we can accept the unilateral version."

**Anti-example:**
> "The indemnification provision in Section 8.2 presents certain considerations with respect to our risk profile. Depending on the jurisdiction and the underlying claims, there may be exposure to the extent that we have contributed intellectual property to the relationship, in which case the unilateral nature of the indemnification could have implications."

---

#### Regulatory Authorities

**Goal**: Formal, precise, and cooperative. Regulatory communications are part of the official record. They must be factually accurate, complete, and carefully qualified.

**Do:**
- Use formal salutation and closing
- Cite specific regulatory provisions when referencing legal requirements
- State facts and conclusions separately; do not conflate them
- Be responsive to the specific questions asked; do not volunteer additional information
- Have counsel review before sending

**Avoid:**
- Informal language or tone
- Admissions of liability or non-compliance (without counsel authorization)
- Vague or incomplete answers to specific questions
- Adversarial tone even when objecting to a request

**Example:**
> "We write in response to your inquiry dated [date] regarding our data processing practices under Article 30 of Regulation (EU) 2016/679 (GDPR). As required by Article 30(1), we maintain records of processing activities carried out under our responsibility. We attach our current Article 30 records covering the processing activities identified in your inquiry."

---

#### Opposing Parties (Adversarial Context)

**Goal**: Measured, professional, non-concessive. Every word is a potential exhibit. Avoid admissions; avoid language that could be characterized as threatening or improper.

**Do:**
- State your position clearly without embellishment
- Reserve all legal rights expressly
- Follow applicable procedural requirements precisely
- Coordinate with counsel on every communication

**Avoid:**
- Emotional language
- Admissions of fact or liability
- Threats (including implicit ones)
- Any language that could be used against you if the matter escalates

**Best practice:** In adversarial contexts, the default is: every communication reviewed by counsel before sending.

---

### 10.6 Post-Matter Review Template

After closing a significant matter (completed negotiation, resolved dispute, enforcement inquiry closed, compliance project completed), document lessons learned.

```
## Post-Matter Review

**Matter**: [description]
**Matter Type**: [Contract Negotiation / Litigation / Regulatory Inquiry / Compliance Project]
**Dates**: [open date] to [close date]
**Lead Counsel**: [name]
**Outcome**: [brief description of final result]

### What Went Well
- [Specific practice or decision that contributed to a good outcome]
- [Specific practice or decision that contributed to a good outcome]

### What Could Be Improved
- [Specific gap, delay, or error — not for blame, for improvement]
- [Specific gap, delay, or error]

### Template or Playbook Updates Needed
- [Specific change to a standard form, template, or playbook section]
- [Reason for the change and which section it affects]

### Regulatory or Market Development to Track
- [Any regulatory development surfaced by this matter that warrants monitoring]

### Training Needs Identified
- [Any skill gap for the team identified during the matter]

### Reusable Precedent Created
- [Redline language, clause position, or analysis that should be stored as a precedent for future matters]
```

### 10.7 Legal Project Status Report (3P Format for Legal Teams)

Adapted from the internal-comms 3P format for legal team weekly status reporting.

```
## Legal Team Status Report — [Week of Date]

### Progress (Completed this week)
| Matter | What was accomplished | Significance |
|---|---|---|
| [matter name] | [specific milestone] | [why it matters: risk reduced, deal closed, deadline met] |

### Plans (Next week priorities)
| Matter | Next action | Owner | Deadline | Depends on |
|---|---|---|---|---|
| [matter name] | [specific action] | [name] | [date] | [any dependency] |

### Problems (Blockers and risks)
| Issue | Impact | What is needed | Who needs to act |
|---|---|---|---|
| [issue] | [what is at risk if unresolved] | [specific ask] | [person or team] |

### Metrics (Optional — for teams tracking volume)
| Metric | This Week | Last Week | Trend |
|---|---|---|---|
| NDAs reviewed | [N] | [N] | [up/down/flat] |
| Contracts closed | [N] | [N] | [up/down/flat] |
| DSRs resolved | [N] | [N] | [up/down/flat] |
| Open risk items | [N] | [N] | [up/down/flat] |
```

---

## Section 11: Decision Flowcharts

### 11.1 Contract Review Routing Decision

```
Incoming contract for review
    |
    v
Is this an NDA?
    |-- YES --> Use NDA Triage (Section 3)
    |
    v
Does a playbook exist for this contract type?
    |-- NO  --> Use baseline positions (Section 10.1)
    |-- YES --> Load playbook
    |
    v
Read FULL contract before flagging issues
    |
    v
Analyze each material clause (Section 2.2 checklist)
    |
    v
For each clause: apply deviation classification (Section 2.3)
    | GREEN  --> Note; no redline needed
    | YELLOW --> Generate redline + fallback (Section 2.4)
    | RED    --> Generate redline + escalation recommendation
    |
    v
Any RED items?
    |-- YES --> Brief senior counsel before delivering output
    |-- NO  --> Proceed to output
    |
    v
Generate output using template (Section 2.6)
    |
    v
Run verification checklist (Section 8.3)
    |
    v
Deliver to stakeholder
```

### 11.2 Compliance Request Routing Decision

```
Incoming compliance request
    |
    v
Request type?
    |-- Data subject request (DSR) --> Section 4.5 workflow
    |-- DPA review                 --> Section 4.4 checklist
    |-- Breach notification        --> Section 10.2 checklist
    |-- Regulatory inquiry         --> Escalate to senior counsel
    |-- Privacy policy question    --> Use FAQ template (Section 10.4)
    |
    v
For DSR:
    |
    v
Identify applicable regulation(s) based on data subject location
    |
    v
Verify identity
    |
    v
Check for exemptions (litigation hold, retention requirement, third-party rights)
    |-- Exemption applies --> Partial or full denial (Section 6.3 template)
    |-- No exemption      --> Fulfill request
    |
    v
Calculate deadline from intake date (not "today")
    |
    v
Check escalation triggers (Section 6.4)
    |-- Trigger present --> STOP; escalate; use DRAFT-only template
    |-- No trigger      --> Use appropriate canned response template
    |
    v
Verify all variables replaced; deadline correct; regulation cited accurately
    |
    v
Deliver response
```

### 11.3 Risk Assessment Routing Decision

```
Legal risk identified
    |
    v
Rate Severity (1-5) independently (Section 5.1)
    |
    v
Rate Likelihood (1-5) independently (Section 5.1)
    |
    v
Calculate Risk Score = Severity x Likelihood
    |
    v
Assign Risk Level
    |-- Score 1-4  (GREEN)  --> Accept; document; periodic monitoring
    |-- Score 5-9  (YELLOW) --> Mitigate; assign owner; brief stakeholders; monthly review
    |-- Score 10-15 (ORANGE)--> Escalate to senior counsel; develop mitigation plan; consider outside counsel
    |-- Score 16-25 (RED)   --> Immediate escalation to GC/C-suite; engage outside counsel; response team
    |
    v
Document in risk register (Section 5.6 format)
    |
    v
For ORANGE / RED: produce formal risk assessment memo (Section 5.5)
    |
    v
Set next review date and trigger events for re-assessment
```

---

## Section 12: Integration with Legal Tech Stack

### 12.1 CLM Integration Patterns

When a Contract Lifecycle Management (CLM) system is connected, legal operations workflows should integrate as follows:

| Workflow | CLM Integration Point |
|---|---|
| Contract review | Pull current draft from CLM; push redline back to CLM; update negotiation status |
| NDA triage | Log triage result (GREEN/YELLOW/RED) and routing decision in CLM; associate with counterparty |
| Risk assessment | Associate risk assessment memo with the relevant contract in CLM; update contract risk flag |
| Meeting briefing | Pull contract status and open negotiation items from CLM for deal review meetings |
| Action item tracking | Create CLM tasks for contract-related action items identified in meetings |
| Post-matter review | Store redline precedents and lessons learned as CLM contract notes or templates |

### 12.2 Matter Management Integration Patterns

| Workflow | Matter Management Integration Point |
|---|---|
| Risk assessment | Create or update matter record; attach risk assessment memo |
| Litigation hold | Associate hold with matter; track custodian acknowledgments |
| Regulatory inquiry | Create dedicated matter; attach all correspondence; track deadlines |
| Data breach | Create incident matter; attach breach assessment and notification records |
| Post-matter review | Close matter with final outcome; attach lessons learned document |

### 12.3 Document Repository Naming and Filing Conventions

To make legal outputs findable, use consistent naming:

| Document Type | Naming Convention | Location |
|---|---|---|
| Contract review summary | `[YYYY-MM-DD] [Counterparty] [Contract Type] Review.pdf` | `/Legal/Contracts/Reviews/` |
| NDA triage | `[YYYY-MM-DD] [Counterparty] NDA Triage [G/Y/R].pdf` | `/Legal/NDAs/Triage/` |
| Risk assessment memo | `[YYYY-MM-DD] [Matter Name] Risk Assessment.pdf` | `/Legal/Risk/Assessments/` |
| Meeting brief | `[YYYY-MM-DD] [Meeting Name] Brief.pdf` | `/Legal/Meetings/Briefs/` |
| Action items | `[YYYY-MM-DD] [Meeting Name] Action Items.pdf` | `/Legal/Meetings/ActionItems/` |
| Litigation hold notice | `[YYYY-MM-DD] [Matter] Hold Notice [Custodian].pdf` | `/Legal/Litigation/Holds/` |
| DSR log | `[YYYY] DSR Log.xlsx` | `/Legal/Privacy/DSR/` |
| Breach notification | `[YYYY-MM-DD] [Incident] Notification [Authority/Individual].pdf` | `/Legal/Privacy/Breaches/` |

---

## Appendix A: Standard Definitions

**Confidential Information**: Non-public information disclosed in connection with a defined business purpose that a reasonable person would understand to be confidential, or that is marked or identified as confidential by the disclosing party.

**Controller**: Under GDPR, the natural or legal person, public authority, agency, or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.

**Data Processing Agreement (DPA)**: A contract required by GDPR Article 28 between a data controller and a data processor that governs the processor's handling of personal data on behalf of the controller.

**Data Subject**: An identified or identifiable natural person whose personal data is processed.

**DPO (Data Protection Officer)**: A mandatory or voluntary role under GDPR responsible for overseeing data protection strategy and compliance.

**Escalation Trigger**: A condition that requires routing a matter to a more senior review level or to outside counsel rather than handling it with a standard response or template.

**Indemnification**: A contractual obligation by which one party agrees to compensate the other party for certain specified losses or liabilities.

**Limitation of Liability**: A contractual clause that restricts the amount of damages one party can recover from the other.

**Personal Data**: Under GDPR, any information relating to an identified or identifiable natural person. Under CCPA, information that identifies, relates to, describes, is reasonably capable of being associated with, or could reasonably be linked to a particular consumer or household.

**Processor**: Under GDPR, a natural or legal person, public authority, agency, or other body which processes personal data on behalf of the controller.

**Residuals Clause**: An NDA provision that permits a party to use confidential information retained in the unaided memory of its personnel without restriction. Must be narrowly scoped to be acceptable.

**Standard Contractual Clauses (SCCs)**: Standardized contractual terms adopted by the European Commission under GDPR that provide appropriate safeguards for the transfer of personal data from the EEA to third countries. Current version: June 2021.

**Sub-processor**: A third party engaged by a processor to carry out processing activities on behalf of the controller.

**Work-for-Hire**: A statutory concept under which work created by an employee within the scope of employment, or certain commissioned works, is owned by the employer or commissioning party rather than the creator.

---

## Appendix B: Regulatory Authority Quick Reference

| Jurisdiction | Authority | Abbreviation | Website |
|---|---|---|---|
| EU / EEA | European Data Protection Board | EDPB | edpb.europa.eu |
| Germany | Datenschutzkonferenz | DSK | datenschutzkonferenz-online.de |
| France | Commission Nationale de l'Informatique et des Libertés | CNIL | cnil.fr |
| UK | Information Commissioner's Office | ICO | ico.org.uk |
| Ireland | Data Protection Commission | DPC | dataprotection.ie |
| USA (Federal) | Federal Trade Commission | FTC | ftc.gov |
| California | California Privacy Protection Agency | CPPA | cppa.ca.gov |
| Brazil | Autoridade Nacional de Proteção de Dados | ANPD | gov.br/anpd |
| Singapore | Personal Data Protection Commission | PDPC | pdpc.gov.sg |
| Australia | Office of the Australian Information Commissioner | OAIC | oaic.gov.au |
| China | Cyberspace Administration of China | CAC | cac.gov.cn |
| Canada | Office of the Privacy Commissioner | OPC | priv.gc.ca |
| South Africa | Information Regulator | — | justice.gov.za/inforeg |

