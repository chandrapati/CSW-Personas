# Cisco Secure Workload — Customer Personas & Engagement Playbook

![Visitors](https://visitor-badge.laobi.icu/badge?page_id=chandrapati.CSW-Personas&left_text=visitors)

**Who you actually meet in a Cisco Secure Workload (CSW) deal — and how to win each of them.**

> **Disclaimer:** This repository is **not** official Cisco product documentation, and it is **not** legal, audit, or insurance/underwriting advice. It is a vendor-neutral **field enablement** aid for Cisco SEs/SAs, account teams, and partners — and a structure customers can reuse internally — to identify segmentation stakeholders, tailor the message, and run a cleaner discovery and POV. Validate all product claims against your tenant's in-product documentation and Cisco Secure Workload product documentation before production decisions.

Every microsegmentation conversation is really **several conversations at once**. The CISO is buying risk reduction; the network architect is protecting the fabric; the application owner is terrified you will break production; the SOC wants evidence; procurement wants a number. If you pitch all of them the same way, you lose most of them.

This repo maps the **personas** you encounter in a CSW engagement, what each one cares about, how to approach them, **which areas of CSW to focus on for each**, the questions to ask, and the objections to expect.

> **In one sentence:** Sell the *outcome* each persona owns — blast-radius reduction to the CISO, "we won't break your app" to the app owner, "this complements your fabric" to the network team, "every blocked flow is evidence" to the SOC — all powered by the same CSW platform.

---

## Contents

- [Who This Repo Is For](#who-this-repo-is-for)
- [How Personas Show Up in a Deal](#how-personas-show-up-in-a-deal)
- [The CSW Persona Map](#the-csw-persona-map)
- [Persona ↔ MEDDPICC Roles](#persona--meddpicc-roles)
- [The Engagement Flow](#the-engagement-flow)
- [Persona Pages (Deep Dives)](#persona-pages-deep-dives)
- [Golden Rules of a Multi-Persona Deal](#golden-rules-of-a-multi-persona-deal)
- [Related Cisco Secure Workload Resources](#related-cisco-secure-workload-resources)

---

## Who This Repo Is For

- **Cisco SEs / SAs and account teams** preparing for discovery calls, briefings, and POVs who need to walk into the room knowing who they will face and what each person needs to hear.
- **Partners** running their own CSW / microsegmentation practice.
- **Customer champions** who have to sell segmentation *internally* across security, network, app, and executive teams.

It is intentionally vendor-neutral in tone — no specific customer names, no marketing fluff — so it is reusable across deals.

---

## How Personas Show Up in a Deal

Segmentation touches more teams than almost any other security project, because it sits **between** the network and the workload and **across** every application. That breadth is why CSW deals stall — not on price, but on **organizational friction**: the network team and the security team each think the other owns it, and the app teams were never consulted.

Three things follow from that:

1. **You will sell to a committee, not a person.** Map every persona early and find the one who owns the *outcome* (usually security risk) and the one who owns the *fabric* (usually network).
2. **The blocker is rarely the buyer.** The application owner who fears an outage, or the network architect who feels CSW overlaps with ACI/firewalls, can quietly kill a deal the CISO already wants. Disarm them directly.
3. **Each persona needs a different proof.** The same POV produces different evidence for different people — a blast-radius story for the CISO, an ADM map for the app owner, an audit export for compliance, a forensic trail for the SOC.

---

## The CSW Persona Map

| # | Persona | Title clues | Primary motivation | Their role in the deal | Deep dive |
|---|---------|-------------|--------------------|------------------------|-----------|
| 1 | **CISO / VP Security** | CISO, VP InfoSec, Head of Cyber | Reduce risk, survive audit & ransomware, satisfy the board | **Economic buyer / sponsor** | [Executive](docs/01-executive-and-economic-buyers.md) |
| 2 | **CIO / VP Infrastructure** | CIO, VP IT, Head of Infrastructure | Agility, consolidation, operational risk, cost | **Economic buyer / sponsor** | [Executive](docs/01-executive-and-economic-buyers.md) |
| 3 | **CTO / Chief Architect** | CTO, Chief/Distinguished Architect | Long-term architecture, platform strategy | **Influencer / visionary** | [Executive](docs/01-executive-and-economic-buyers.md) |
| 4 | **CFO / Finance / Risk** | CFO, Controller, Risk Officer | ROI, TCO, cyber-insurance premiums | **Approver / economic gatekeeper** | [Executive](docs/01-executive-and-economic-buyers.md) |
| 5 | **Security Architect / Zero Trust lead** | Security Architect, ZTA lead | Designing least-privilege that actually ships | **Technical champion** | [Security & Compliance](docs/02-security-and-compliance-personas.md) |
| 6 | **SOC / IR / Threat** | SOC Manager, IR lead, Threat Hunter | Detection, forensics, dwell-time, evidence | **Influencer / champion** | [Security & Compliance](docs/02-security-and-compliance-personas.md) |
| 7 | **GRC / Compliance / Audit** | GRC, Compliance Manager, Internal Audit | Framework evidence, documented segmentation | **Influencer / coach** | [Security & Compliance](docs/02-security-and-compliance-personas.md) |
| 8 | **Network Architect / Engineering** | Network Architect, NetEng, DC fabric | Protect the fabric; avoid overlap with ACI/firewall | **Technical buyer or blocker** | [Infrastructure & Platform](docs/03-infrastructure-and-platform-personas.md) |
| 9 | **Cloud / Platform / DevOps** | Cloud Architect, Platform Eng, SRE, K8s | Multicloud consistency, automation, no friction | **Technical buyer / champion** | [Infrastructure & Platform](docs/03-infrastructure-and-platform-personas.md) |
| 10 | **Server / Virtualization / Endpoint** | Wintel, VMware, EUC/VDI, Server team | Agent footprint, OS support, golden images | **Technical buyer or blocker** | [Infrastructure & Platform](docs/03-infrastructure-and-platform-personas.md) |
| 11 | **Identity team** | IAM, AD, Cisco ISE owners | Identity context, ISE/pxGrid integration | **Influencer** | [Infrastructure & Platform](docs/03-infrastructure-and-platform-personas.md) |
| 12 | **Application Owner / App Dev** | App owner, Dev lead, DBA, product team | "Do not break my application" | **Blocker → champion** | [Application & Operations](docs/04-application-and-operations-personas.md) |
| 13 | **Operations / Change Management** | IT Ops, NOC, Change/Problem Mgmt | Stability, change windows, run-book burden | **Blocker / influencer** | [Application & Operations](docs/04-application-and-operations-personas.md) |
| 14 | **Procurement / Sourcing** | Procurement, Vendor Mgmt, Sourcing | Price, terms, competitive bake-off | **Gatekeeper** | [Application & Operations](docs/04-application-and-operations-personas.md) |

---

## Persona ↔ MEDDPICC Roles

Use this to translate personas into qualification language:

| MEDDPICC element | Who usually fills it |
|------------------|----------------------|
| **M**etrics | CISO, GRC (risk/blast-radius/audit metrics); CFO (TCO, insurance) |
| **E**conomic buyer | CISO or CIO (sometimes CFO sign-off) |
| **D**ecision criteria | Security Architect + Network Architect jointly |
| **D**ecision process | Procurement + the sponsoring exec |
| **P**aper process | Procurement / Vendor Management |
| **I**dentified pain | CISO (ransomware/audit), App owner (outage risk if *not* segmented) |
| **C**hampion | Security Architect or Zero Trust lead (most common) |
| **C**ompetition | Network Architect's incumbent (ACI-only, firewall-only, Illumio/Guardicore, cloud-native SGs) |

> If you cannot name your **champion** and your **economic buyer** from the persona map, you are not yet in a qualified CSW deal.

---

## The Engagement Flow

A healthy CSW deal usually moves through the personas in this order:

```
Executive sponsor (CISO/CIO)         → owns the "why now" and the budget
   → Security Architect (champion)   → owns the design and the POV
      → Network + Cloud + Server     → own the "where it runs" / dispel overlap fears
         → Application owners         → own "don't break my app" (turn fear into ADM value)
            → SOC + GRC              → own the evidence (forensics + audit)
               → Procurement         → owns the paper
```

Each handoff is a place a deal can stall. The persona pages tell you how to keep momentum at each step.

---

## Persona Pages (Deep Dives)

| Page | Covers |
|------|--------|
| [01 — Executive & Economic Buyers](docs/01-executive-and-economic-buyers.md) | CISO, CIO, CTO, CFO — risk, strategy, ROI, cyber insurance |
| [02 — Security & Compliance Personas](docs/02-security-and-compliance-personas.md) | Security Architect / ZTA, SOC / IR, GRC / Audit |
| [03 — Infrastructure & Platform Personas](docs/03-infrastructure-and-platform-personas.md) | Network, Cloud / DevOps, Server / Virtualization / VDI, Identity |
| [04 — Application & Operations Personas](docs/04-application-and-operations-personas.md) | Application owners, Operations / Change, Procurement |
| [05 — Quick-Reference Cheat Sheet](docs/05-quick-reference-cheat-sheet.md) | One-page "what to say / what to show" per persona |
| [06 — Discovery Questions by Persona](docs/06-discovery-questions-by-persona.md) | Open-ended questions that surface pain and qualify the deal |
| [07 — Objection Handling by Persona](docs/07-objection-handling-by-persona.md) | The objection each persona raises and how to answer it |

---

## Golden Rules of a Multi-Persona Deal

1. **Lead with the outcome the person owns**, not the feature list. CSW is a platform; the *value* is persona-specific.
2. **Name the blocker out loud.** The app owner and the network architect can sink a CISO-sponsored deal. Engage them first, not last.
3. **Map "macro vs micro" to the audience.** Executives and network teams buy macro (prod/non-prod, ransomware fan-out) fast; app teams and GRC buy micro (per-app least privilege) once trust is earned. See the phased roadmap in [CSW-User-Education](https://github.com/chandrapati/CSW-User-Education).
4. **"Discovery-first" is the universal disarmer.** Monitor mode → simulate → enforce is what lets you tell *every* persona "we observe before we block."
5. **One POV, many proofs.** Plan the POV so it produces a blast-radius story, an ADM map, an audit export, and a forensic trail — one each for the CISO, app owner, GRC, and SOC.
6. **Position with the fabric, not against it.** CSW complements ACI / Secure Firewall / cloud SGs — it does not replace them. This single message wins over the network persona (the most common blocker).

---

## Related Cisco Secure Workload Resources

| Repository | Description | Best for |
|------------|-------------|----------|
| [User Education](https://github.com/chandrapati/CSW-User-Education) | Onboarding guide, value story, 80+ video library | New CSW users, POV prep |
| [Compliance Mapping](https://github.com/chandrapati/CSW-Compliance-Mapping) | CSW controls mapped to NIST, PCI, HIPAA, CIS, and more | GRC / Compliance / Audit persona |
| [Agent Installation](https://github.com/chandrapati/CSW-Agent-Installation-Guide) | Deploy agents on Linux / Windows / cloud | Server / Virtualization persona |
| [Policy Lifecycle](https://github.com/chandrapati/CSW-Policy-Lifecycle) | Discovery → simulate → enforce workflow | Security Architect persona |
| [ISE / pxGrid](https://github.com/chandrapati/csw-ise-integration) | Identity-aware microsegmentation | Identity persona |
| [ServiceNow CMDB](https://github.com/chandrapati/csw-servicenow-integration) | CMDB label enrichment | Ops / CMDB-driven policy |
| [Secure Firewall](https://github.com/chandrapati/CSW-Secure-Firewall-Integration-Guide) | NSEL ingest + FMC enforcement | Network persona (agentless) |
| [Splunk Integration](https://github.com/chandrapati/csw-splunk-integration) | CSW alerts → Splunk SIEM | SOC / IR persona |

> **Suggested customer journey:** Personas (this repo, for the account team) → User Education → Compliance Mapping → Agent Installation → Policy Lifecycle → Operations Toolkit.
