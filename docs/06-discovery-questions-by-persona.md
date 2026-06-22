# 06 — Discovery Questions by Persona

> Open-ended questions that surface pain, qualify the deal, and let each persona talk themselves into the need. Ask, then listen. Pair with [07 — Objection Handling](07-objection-handling-by-persona.md).

---

## Universal opener (works in any room)

> **"Today, if an attacker compromises one workload in your environment, how far can they move — and how would you know?"**

Almost no one can answer this with confidence. The silence is your opening.

---

## CISO / VP Security
- When you brief the board on ransomware, what's the hardest question to answer?
- Can you demonstrate — not assert — least-privilege segmentation to an auditor today?
- Has cyber-insurance asked about lateral-movement controls or segmentation at renewal?
- Have you attempted segmentation before? What stopped it?
- Which 3–5 applications, if encrypted, would be a board-level event?

## CIO / VP Infrastructure
- Who owns segmentation today — network or security? How's that working?
- How long does it take to securely stand up segmentation for a new app or cloud?
- How many overlapping tools touch east-west control right now?
- What does an M&A integration or data-center consolidation do to your security model?

## CTO / Chief Architect
- What does your 3-year Zero Trust / segmentation reference architecture look like?
- How do you keep policy consistent across on-prem, multicloud, and Kubernetes?
- Where do you worry about lock-in or dead-end designs?

## CFO / Finance & Risk
- How do you currently quantify the financial exposure of a ransomware event?
- Are segmentation controls affecting your cyber-insurance premium or eligibility?
- How do you evaluate ROI on a risk-reduction investment vs a revenue one?

## Security Architect / Zero Trust lead
- How do you discover application dependencies today — interviews, spreadsheets, guesswork?
- What's your biggest fear when flipping a policy from monitor to enforce?
- Do you manage policy as code and review it, or click it in a console?
- Where does your current segmentation effort stall?

## SOC / IR / Threat
- How would you detect lateral movement between two servers today?
- During an incident, how fast can you contain a single scope or segment?
- What workload-level forensic evidence do you have for an investigation?
- How does east-west data reach your SIEM today?

## GRC / Compliance / Audit
- Which frameworks drive your segmentation requirements (PCI, HIPAA, SOX, NIST…)?
- How long does it take to produce segmentation evidence for an audit today?
- Could segmentation shrink your regulated scope (e.g., the PCI CDE)?
- Do auditors accept your current segmentation evidence, or push back?

## Network Architect / Engineering
- What enforces east-west policy today — ACI contracts, firewalls, VLANs, a mix?
- Can you see *intra*-tier (same-EPG / same-VLAN) workload-to-workload traffic?
- Where do agents need an agentless alternative (legacy, appliances, OT)?
- How much of your firewall rule base exists just for internal east-west traffic?

## Cloud / Platform / DevOps
- How consistent is segmentation across AWS / Azure / GCP / on-prem today?
- Is your segmentation API-driven and in your pipeline, or manual?
- How do you handle policy for autoscaling / ephemeral / Kubernetes workloads?

## Server / Virtualization / Endpoint
- What's your current agent footprint and support-matrix tolerance?
- Which OSes or appliances *can't* take an agent?
- How do you handle non-persistent VDI / golden images?
- What's your change-control process for installing/upgrading agents?

## Identity team
- Do you use Cisco ISE / pxGrid? How healthy is that integration?
- Would user/device identity as policy context be valuable for admin-path control?

## Application Owner / App Dev
- Do you have a current, accurate map of everything your application talks to?
- What's the blast radius to *you* if a segmentation rule blocks a legitimate flow?
- Who gets paged when this app has a connectivity problem?
- Would an accurate dependency map help you with migrations or troubleshooting?

## Operations / Change Management
- What's your change/CAB process for a policy enforcement change?
- How do you catch out-of-band changes (drift) today?
- What does an acceptable rollback look like to you?

## Procurement / Sourcing
- Are you comparing alternatives? Which ones?
- How do you weigh platform breadth and consolidation vs a point tool's price?
- What's the paper-process timeline and approval chain?

---

## Qualifying checklist (after discovery)

- [ ] Can I name the **economic buyer** (who funds it)?
- [ ] Can I name the **champion** (who runs it internally)?
- [ ] Have I identified the **blocker** (usually network or app owner) — and started disarming them?
- [ ] Do I know the **compelling event** (audit, breach, insurance, M&A, cloud move)?
- [ ] Is there a **Phase-2 outcome** the customer agrees is worth a POV?
