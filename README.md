# Compliance Security Risk Heatmap

An SAP LeanIX Custom Report MVP for visualizing **application compliance readiness and application risk** in one explainable executive heatmap.

## Why this project?

Enterprise Architecture teams often have business criticality, technical suitability, lifecycle, SixR, AI, SSO, and compliance information available in SAP LeanIX, but the decision-maker still has to connect these signals manually.

This MVP creates a focused decision-support layer that combines those signals into a visual, clickable, and explainable application risk view.

## What it provides

- Executive application portfolio heatmap
- GDPR, PCI-DSS, SOX, HIPAA, and ISO 27001 readiness/status
- Seven-dimensional application risk scoring
- Explicit weighted calculation and risk thresholds
- Risk-data coverage indicator
- Clickable application drill-down
- Explainable risk and compliance detail
- Navigation back to the LeanIX Application Fact Sheet
- Safe handling of missing data and `Not Applicable` versus `Not Assessed`

## Risk model

| Dimension | Weight |
|---|---:|
| Business Criticality | 25% |
| Functional Suitability | 10% |
| Technical Suitability | 15% |
| Obsolescence Risk | 20% |
| SixR Risk / Time Priority | 15% |
| AI Risk | 10% |
| SSO Availability | 5% |

Scores are normalized to 0–100. Missing dimensions are excluded from the denominator rather than treated as zero risk.

| Score | Level |
|---:|---|
| 0–24 | Low |
| 25–49 | Medium |
| 50–74 | High |
| 75–100 | Critical |

## Business Architecture relevance

The MVP supports Enterprise Architecture and Business Architecture decision-making by connecting business criticality and application information with risk, compliance readiness, governance, and transformation priorities.

It is informed by TOGAF and Business Architecture Guild/BIZBOK principles around stakeholder-oriented architecture, decision support, risk reduction, alignment, transformation, and effective use of technology.

The report is **not** a complete TOGAF ADM implementation and is **not** a complete compliance management platform.

## Why a custom LeanIX report?

Standard SAP LeanIX fields and reports provide important source information. This MVP addresses a different requirement: combining multiple independent dimensions into a single calculated, visual, and explainable decision view.

The value is the analytical layer: **LeanIX data → calculation → visualization → drill-down → explanation → business decision**.

## Business benefit

The report helps stakeholders answer:

- Which applications are high or critical risk?
- Which applications have compliance readiness concerns?
- Why did an application receive its risk score?
- Which dimensions are driving the score?
- How complete is the risk data?
- Which applications should be prioritized for further assessment, remediation, modernization, or governance review?

A stakeholder can move from portfolio-level visualization to an individual application and inspect the calculation and explanation without losing the underlying LeanIX context.

## Scope boundary

### MVP 1

```text
Application Portfolio
        ↓
Compliance Status + Application Risk
        ↓
Executive Heatmap
        ↓
Clickable / Explainable Drill-down
```

### Future Global Compliance Architecture

```text
Country → Regulation → Applicability → Requirement
→ Control → Evidence → Assessment → Risk → Exception
```

The global compliance architecture is intentionally a separate program and is not implemented in this MVP.

## Project

**Report ID:** `compliance-security-risk-heatmap`  
**Current MVP release:** `0.0.1`  
**Platform:** SAP LeanIX Custom Report  
**Repository:** `nbnayak88/compliance-security-risk-heatmap`

## Local development

```powershell
npm install
npm run dev
```

## Validation

```powershell
npx tsc --noEmit --pretty false
npm run build
```

## LeanIX deployment

Update the version in `package.json` before uploading a version that already exists, then run:

```powershell
npm run upload
```

## Security

Do not commit credentials, API tokens, `.env` files, LeanIX authentication files, or other secrets.

## Documentation

See [`MVP.md`](./MVP.md) for the complete MVP architecture, business rationale, risk methodology, compliance model, technical structure, deployment guidance, acceptance criteria, and future boundary.

## Status

**MVP 1 — deployed as v0.0.1 in SAP LeanIX.**
