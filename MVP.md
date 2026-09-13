# Compliance Security Risk Heatmap — MVP 1

## 1. Purpose

Build and deploy an SAP LeanIX Custom Report that provides an executive-level view of application portfolio compliance readiness and application risk.

This MVP combines available LeanIX application signals with five compliance-status fields and presents them in a visual, clickable and explainable report.

> **Core purpose:** Turn existing architecture data into an explainable business decision view.

---

# 2. MVP Scope

## In Scope

```text
Application Portfolio
        |
        +-- Compliance Status
        |
        +-- Application Risk
        |
        +-- Coverage / Data Quality
        |
        +-- Executive Heatmap
        |
        +-- Clickable Application Drill-down
        |
        +-- Explainable Risk Calculation
        |
        +-- LeanIX Fact Sheet Navigation
```

Supported compliance frameworks:

1. GDPR
2. PCI-DSS
3. SOX
4. HIPAA
5. ISO 27001

Supported application-risk dimensions:

1. Business Criticality
2. Functional Suitability
3. Technical Suitability
4. Obsolescence Risk
5. SixR Risk / Time Priority
6. AI Risk
7. SSO Availability

## Explicitly Out of Scope

This MVP does **not** implement:

- Country-level compliance management
- Global regulatory catalogues
- Regulatory requirements
- Controls and control testing
- Evidence management
- Regulatory-change management
- Exception/remediation workflows
- Legal applicability determination
- 100+ country regulatory coverage
- Enterprise-wide compliance governance

These capabilities belong to the separate **Global Compliance Architecture** program.

---

# 3. Business Architecture and TOGAF Relevance

This MVP is an **Enterprise Architecture decision-support capability**, not merely a technical dashboard.

## TOGAF relevance

The report supports the practical Enterprise Architecture objective of connecting business concerns, architecture information, risk, governance and transformation decisions.

It contributes particularly to:

- **Business Architecture** — making business-critical applications and their risk visible in business terms.
- **Application Architecture** — exposing functional/technical suitability, lifecycle exposure and SixR direction.
- **Technology Architecture** — highlighting technical suitability and obsolescence-related exposure.
- **Security and governance** — placing SSO and compliance readiness alongside portfolio risk.
- **Architecture Governance** — creating evidence for prioritization, rationalization, remediation and investment decisions.
- **Transformation planning** — using risk signals and SixR information to identify applications needing attention.

The MVP does not claim to implement the full TOGAF ADM. It provides a focused analytical capability that supports architecture governance and stakeholder decision-making.

## Business Architecture Guild / BIZBOK relevance

Business architecture provides a holistic view of capabilities, value delivery, information, organization, strategy, initiatives and stakeholder concerns. The MVP applies this principle at the application-risk decision layer by connecting business criticality and application characteristics to risk and compliance readiness.

Conceptually:

```text
Business Need / Criticality
          ↓
       Application
          ↓
 Risk + Compliance Readiness
          ↓
      Prioritization
          ↓
Transformation / Remediation / Investment Decision
```

The report therefore acts as a communication and analytical bridge between architecture information and business action.

---

# 4. Business Problem

Organizations may already have application inventory, business criticality, technical-fit, functional-fit, lifecycle, SixR, AI, SSO and compliance data in LeanIX. The business challenge is that these signals can remain distributed across fields, screens and reports.

The decision-maker needs to answer:

- Which applications are most risky?
- Which business-critical applications need attention?
- Which applications have compliance concerns?
- Why did an application receive a particular risk score?
- Which dimensions are driving the score?
- How complete is the underlying risk data?
- Can I drill from a portfolio-level insight to the individual application?
- Can I understand the calculation rather than simply trust a number?

The MVP is designed around these questions.

---

# 5. Why Standard SAP LeanIX Reports and Fields Alone Are Not Enough

SAP LeanIX provides important standard application attributes and standard reports. Those capabilities are the foundation of the MVP and should not be viewed as inadequate in themselves.

The gap addressed by this MVP is a **cross-dimensional analytical use case**.

Standard LeanIX data can provide individual signals such as:

- business criticality
- functional suitability
- technical suitability
- lifecycle / obsolescence information
- SixR information
- AI-related attributes
- SSO-related information
- application inventory and standard visualizations

But the business requirement is to combine those signals with compliance status into one explainable decision model.

The MVP adds an analytical layer:

```text
Business Criticality
        +
Functional Suitability
        +
Technical Suitability
        +
Obsolescence
        +
SixR
        +
AI Risk
        +
SSO
        +
Compliance Readiness
        ↓
Calculated Application Risk
        ↓
Executive Heatmap
        ↓
Clickable Drill-down
        ↓
Explainable Calculation
```

Therefore the differentiator is not simply another visualization of an existing field. It is the combination of:

1. multi-dimensional aggregation;
2. explicit weighting;
3. normalized scoring;
4. risk-level classification;
5. data-quality / coverage measurement;
6. compliance-readiness presentation;
7. interactive drill-down;
8. transparent calculation explanation.

This is why a custom report is justified for this use case.

---

# 6. Business Benefits

## 6.1 Executive visibility

A single heatmap makes portfolio risk and compliance-readiness patterns easier to understand and communicate.

## 6.2 Clickable drill-down

A stakeholder can move from:

```text
Portfolio
   ↓
Application
   ↓
Risk Score
   ↓
Risk Dimensions
   ↓
Compliance Status
   ↓
Explanation
   ↓
LeanIX Fact Sheet
```

This shortens the path from a portfolio observation to an actionable investigation.

## 6.3 Explainable scoring

The report explains why an application received its score instead of presenting a black-box number.

For example:

```text
Risk Score: 64
Risk Level: High

Business Criticality      70
Technical Suitability     30
Obsolescence              90
SixR                      60
AI Risk                   30
SSO                         0
```

The detail view can explain the populated contributors and their relative weights.

## 6.4 Transparent mathematical calculation

The report exposes:

```text
Input
  ↓
Normalized Score
  ↓
Weight
  ↓
Weighted Contribution
  ↓
Weighted Total
  ↓
Available Weight
  ↓
Normalized Result
  ↓
Final Risk Score
  ↓
Risk Level
```

Example:

```text
(30 × 15 + 0 × 5) / (15 + 5)
= 22.5
→ 23
→ Low
```

This makes the result auditable and easy for stakeholders to challenge or understand.

## 6.5 Better prioritization

The business can focus attention on applications where risk, criticality and compliance readiness create the greatest concern.

Potential decisions include:

- modernization
- remediation
- further assessment
- rationalization
- SixR transformation planning
- security review
- compliance follow-up

## 6.6 Reduced analysis effort

Instead of opening multiple LeanIX reports and manually synthesizing the information, users can start with the combined view and drill down only where needed.

## 6.7 Common stakeholder language

The same application and score can be discussed by Enterprise Architecture, Business Architecture, application teams, security, risk, compliance and business stakeholders.

## 6.8 Faster architecture governance

The conversation moves from:

> What does this application look like?

to:

> Why is this application high risk, what is driving the score, and what should we investigate next?

## 6.9 Better communication

The report clearly communicates:

```text
What is risky?
Why is it risky?
How complete is the risk data?
What compliance status exists?
Where should we drill down?
```

## 6.10 Foundation for transformation

The MVP can support a chain such as:

```text
Risk
  ↓
Prioritization
  ↓
SixR Strategy
  ↓
Transformation Roadmap
  ↓
Investment / Remediation Decision
```

---

# 7. Product Positioning

## Report Name

**Compliance Security Risk Heatmap**

## Report ID

```text
compliance-security-risk-heatmap
```

## Current MVP Version

```text
0.0.1
```

## Platform

SAP LeanIX Custom Report

---

# 8. Core Architecture

```text
                    SAP LEANIX
                        |
                        v
              Application Portfolio
                        |
          +-------------+-------------+
          |             |             |
          v             v             v
     Application     Compliance     Risk Signals
      Attributes       Statuses
          |             |             |
          +-------------+-------------+
                        |
                        v
                Risk Scoring Engine
                        |
                        v
              Executive Heatmap
                        |
              +---------+---------+
              |                   |
              v                   v
       Portfolio View       Application Detail
                              Side Panel
```

---

# 9. LeanIX Application Data

## Native attributes used by the MVP

```text
id
displayName
businessCriticality
functionalSuitability
technicalSuitability
aggregatedObsolescenceRisk
lxSixRClassification
lxSixRRiskClassification
lxSixRTimePriority
lxAiRisk
lxHostingType
lxStatusSSO
```

## Compliance attributes

```text
GDPR
PCIDSS
SOX
HIPAA
ISO27001
```

The report must not fabricate compliance results. Missing data is displayed as `Not Assessed` rather than being treated as non-compliance.

---

# 10. Compliance Status Model

Normalized display states include:

```text
Compliant
Partially Compliant
Non-Compliant
Exception / Risk Accepted
Assessment in Progress
Assessment Completed
Not Applicable
Applicable - Not Assessed
Not Assessed
```

The presentation layer normalizes capitalization and formatting so source values such as `COMPLIANT`, `Compliant`, and `compliant` display consistently.

---

# 11. Compliance Semantics

Always distinguish:

```text
Not Applicable
        ≠
Not Assessed
```

`Not Applicable` means the framework does not apply to the application.

`Not Assessed` means the assessment information is unavailable or has not been completed.

---

# 12. Risk Scoring Model

## Risk weights

```text
Business Criticality       25%
Functional Suitability     10%
Technical Suitability      15%
Obsolescence Risk          20%
SixR Risk                  15%
AI Risk                    10%
SSO Availability             5%
                           -----
                           100%
```

Only populated dimensions participate in the calculation.

> **Missing risk data is excluded from the denominator rather than treated as zero risk.**

---

# 13. Risk Score Inputs

## Business Criticality

```text
administrativeService = 10
businessOperational   = 30
businessCritical      = 70
missionCritical       = 100
```

## Functional Suitability

```text
perfect       = 0
appropriate   = 25
insufficient  = 70
unreasonable  = 100
```

## Technical Suitability

```text
fullyAppropriate = 0
adequate         = 30
unreasonable     = 70
inappropriate    = 100
```

## Obsolescence

```text
unaddressedEndOfLife  = 100
unaddressedPhaseOut   = 90
missingLifecycle      = 70
missingItComponent    = 60
riskAccepted          = 40
riskAddressed         = 10
noRisk                = 0
```

## SixR

Where both SixR risk and SixR time priority are available:

```text
SixR Score = MAX(SixR Risk, SixR Time Priority)
```

## AI Risk

```text
minimal       = 0
limited       = 30
high          = 70
unacceptable  = 100
```

## SSO Availability

```text
supported     = 0
notSupported  = 100
```

---

# 14. Risk Formula

For populated dimensions:

```text
Weighted Risk =
  SUM(normalizedScore × dimensionWeight)
  /
  SUM(weights for populated dimensions)
```

This normalization ensures that incomplete data does not automatically depress the score.

---

# 15. Risk Levels

```text
0–24    Low
25–49   Medium
50–74   High
75–100  Critical
```

If no meaningful risk dimensions are available, the application is shown as `Not Assessed`.

---

# 16. Risk Coverage

The report shows how many of the seven risk dimensions are populated.

Example:

```text
Coverage: 5/7
```

Coverage is a data-quality indicator and is not equivalent to compliance coverage.

---

# 17. Executive Heatmap

Primary columns:

```text
Application
GDPR
PCI-DSS
SOX
HIPAA
ISO 27001
Risk Score
Risk Level
Coverage
```

Compliance status cells use semantic colors while retaining readable text.

Recommended semantics:

```text
Green     = Compliant
Yellow    = Partially Compliant / Applicable but not assessed
Red       = Non-Compliant
Orange    = Exception / Risk Accepted
Blue      = Assessment in Progress
Gray      = Not Applicable / Not Assessed
```

Color is a visual aid; status text remains visible so meaning is not dependent on color alone.

---

# 18. Application Detail Panel

Clicking an application opens a custom LeanIX side panel containing:

### Header

```text
Application Name
Risk Level + Score
```

### Coverage

```text
5 of 7 risk dimensions populated
```

### Risk Breakdown

For each dimension:

- LeanIX value
- normalized score
- weight
- weighted contribution when available

### Score Calculation

Show:

```text
Weighted total
Available weight
Normalized score
Final score
Risk classification
```

### Why this score?

Provide a dynamic explanation based on the application's populated risk dimensions.

### Compliance Readiness

Display:

```text
GDPR
PCI-DSS
SOX
HIPAA
ISO 27001
```

### Fact Sheet navigation

Provide a direct action to the LeanIX Application Fact Sheet.

---

# 19. Explainability Requirement

Explainability is a core MVP feature, not an optional enhancement.

Every displayed risk score should be traceable to:

```text
LeanIX Attribute
      ↓
Source Value
      ↓
Mapped Numeric Score
      ↓
Weight
      ↓
Contribution
      ↓
Normalized Calculation
      ↓
Final Score
      ↓
Risk Level
```

Similarly, compliance status should be traceable to the corresponding LeanIX Application field.

---

# 20. Data Quality Principles

1. Missing risk data does not equal zero risk.
2. Missing compliance data does not equal non-compliance.
3. `Not Applicable` and `Not Assessed` remain distinct.
4. Coverage is visible.
5. Risk calculations are explainable.
6. The report never independently claims legal compliance.
7. The displayed status reflects the data available in LeanIX.

---

# 21. Technical Project Structure

```text
compliance-security-risk-heatmap/
│
├── src/
│   ├── config/
│   │   ├── frameworks.ts
│   │   └── riskScoring.ts
│   │
│   ├── types/
│   │   ├── compliance.ts
│   │   └── risk.ts
│   │
│   ├── utils/
│   │   └── riskScoring.ts
│   │
│   ├── App.tsx
│   ├── App.css
│   └── main.tsx
│
├── package.json
├── tsconfig.json
├── vite.config.ts
└── README.md
```

Backup source files should be kept outside `src/` so they are not accidentally compiled as part of the TypeScript project.

---

# 22. Code Organization

### `src/config/frameworks.ts`

Supported compliance frameworks and presentation configuration.

### `src/config/riskScoring.ts`

Risk weights, score maps and thresholds.

### `src/types/risk.ts`

Application risk and compliance signal types.

### `src/utils/riskScoring.ts`

The scoring engine. Keep calculation logic independent from UI rendering.

### `src/App.tsx`

LeanIX data retrieval, application mapping, executive heatmap and interactive side panel.

### `src/App.css`

Presentation and semantic heatmap styling.

---

# 23. LeanIX Data Retrieval

The Application facet explicitly requests required attributes.

Current compliance keys:

```text
GDPR
PCIDSS
SOX
HIPAA
ISO27001
```

The report maps those LeanIX keys into internal normalized properties:

```text
GDPR       → gdpr
PCIDSS     → pcidss
SOX        → sox
HIPAA      → hipaa
ISO27001   → iso27001
```

This separates LeanIX technical keys from human-readable report labels.

---

# 24. Validation Examples

The prototype has been tested with real LeanIX Application records and multiple compliance states.

Example status combinations include:

```text
Compliant
Not Applicable
Assessment in Progress
Partially Compliant
Non-Compliant
Exception / Risk Accepted
```

This verifies that the heatmap is not limited to a single binary compliance state.

---

# 25. Deployment

## Local development

```powershell
npm run dev
```

## TypeScript check

```powershell
npx tsc --noEmit --pretty false
```

Expected: no TypeScript errors.

## Production build

```powershell
npm run build
```

Expected: successful Vite production build.

## LeanIX upload

Increment the version before re-uploading an already-existing version.

Current release:

```json
"version": "0.0.1"
```

Upload:

```powershell
npm run upload
```

---

# 26. GitHub Repository

Recommended repository:

```text
nbnayak88/compliance-security-risk-heatmap
```

Recommended structure:

```text
compliance-security-risk-heatmap/
├── src/
├── public/
├── package.json
├── package-lock.json
├── tsconfig.json
├── vite.config.ts
├── README.md
└── MVP.md
```

The repository should document the MVP and remain focused on this application-level report.

---

# 27. GitHub Security Requirements

Never commit:

```text
.env
.env.*
*.local
lxr.json
API tokens
access tokens
passwords
private credentials
```

Use an appropriate `.gitignore` and review the repository before pushing.

---

# 28. MVP Acceptance Criteria

## Data

- [ ] Application portfolio loads
- [ ] Required LeanIX attributes are retrieved
- [ ] Five compliance attributes are retrieved when available
- [ ] Missing data is handled safely

## Compliance

- [ ] GDPR displayed
- [ ] PCI-DSS displayed
- [ ] SOX displayed
- [ ] HIPAA displayed
- [ ] ISO 27001 displayed
- [ ] Not Applicable distinguished from Not Assessed
- [ ] Status colors work
- [ ] Status text remains visible
- [ ] Mixed capitalization is normalized

## Risk

- [ ] Seven risk dimensions supported
- [ ] Weighted calculation works
- [ ] Missing dimensions excluded from denominator
- [ ] Risk score is 0–100
- [ ] Risk levels are Low / Medium / High / Critical
- [ ] Coverage is visible
- [ ] Risk explanation is dynamic
- [ ] Mathematical calculation is visible in detail view

## UX

- [ ] Executive heatmap loads
- [ ] Application rows are clickable
- [ ] Side panel opens
- [ ] Risk breakdown is visible
- [ ] Compliance readiness is visible
- [ ] Fact Sheet link works
- [ ] Layout is readable at desktop resolution

## Engineering

- [ ] TypeScript compilation passes
- [ ] Production build passes
- [ ] LeanIX package/security scan is clean
- [ ] No credentials are committed
- [ ] Version is explicitly managed
- [ ] GitHub repository is organized

---

# 29. Known Limitations

This MVP is an analytical visualization of the data available in SAP LeanIX.

A `Compliant` status means the underlying LeanIX assessment/status is `Compliant`; the report does not independently audit legal, technical or control effectiveness.

The MVP should not claim:

```text
100% legally compliant
100% global compliance coverage
All regulations covered
All controls effective
```

---

# 30. Explicit Boundary to Global Compliance Architecture

MVP 1 remains intentionally application-centric.

```text
MVP 1
Compliance Security Risk Heatmap
        ↓
Application Portfolio
        ↓
Compliance Status + Application Risk
        ↓
Visual Heatmap
        ↓
Explainable Drill-down
```

The separate future program will address:

```text
Global Compliance Architecture
        ↓
Geography
        ↓
Country
        ↓
Sector
        ↓
Regulation
        ↓
Applicability
        ↓
Requirement
        ↓
Control
        ↓
Evidence
        ↓
Assessment
        ↓
Risk
        ↓
Exception / Remediation
        ↓
Regulatory Change
        ↓
Application Impact
```

No global regulatory catalogue or country-scale compliance engine should be added to MVP 1.

---

# 31. Reference Basis

The business and architecture rationale is informed by:

- The Open Group / TOGAF Enterprise Architecture guidance.
- Business Architecture Guild / BIZBOK guidance on business architecture, business value, stakeholder alignment, analysis and decision support.
- SAP LeanIX Reporting Library and Custom Report documentation describing tailored reporting capabilities and the use of workspace data for custom visualizations.

The MVP is an applied architecture capability built on top of LeanIX data. It is not presented as a complete implementation of TOGAF, BIZBOK, a regulatory compliance framework, or a legal compliance certification.

---

# 32. MVP Value Proposition

The MVP can be summarized as:

```text
LEANIX DATA
     ↓
MULTI-DIMENSIONAL ANALYSIS
     ↓
CALCULATED RISK + COMPLIANCE READINESS
     ↓
VISUAL HEATMAP
     ↓
CLICKABLE DRILL-DOWN
     ↓
EXPLAINABLE CALCULATION
     ↓
BUSINESS DECISION
```

Its value is the combination of:

- **Visualization** — makes portfolio patterns immediately understandable.
- **Calculation** — derives a consistent risk score from defined inputs.
- **Explainability** — shows why a score exists.
- **Drill-down** — moves from portfolio insight to application-level analysis.
- **Traceability** — links back to the LeanIX Application Fact Sheet.
- **Prioritization** — helps identify applications requiring attention.
- **Governance** — supports architecture and transformation decisions with a common analytical model.

---

# 33. Definition of Done

MVP 1 is complete when:

```text
SAP LeanIX
    ↓
Application Portfolio
    ↓
Compliance Signals + Risk Signals
    ↓
Risk Engine
    ↓
Executive Compliance Heatmap
    ↓
Clickable Application Drill-down
    ↓
Explainable Score + Calculation
```

is running successfully in LeanIX, has passed TypeScript and production builds, has passed the package/security scan, has been uploaded successfully, and is versioned and documented in GitHub.

**Current target release: `v0.0.1`**
