# 01 — Executive & Economic Buyers

> CISO · CIO · CTO · CFO / Finance & Risk
>
> These are the people who fund the program and own the "why now." They do **not** want a feature tour — they want to know what risk goes away, what it costs, and how it shows up to the board, auditors, and insurers. Keep it outcome-first; let the architects go deep later. See the [README](../README.md) for how these personas fit the whole deal.

---

## 1. CISO / VP Security — *the most common economic buyer*

**Titles:** CISO, Deputy CISO, VP Information Security, Head of Cyber, BISO.

**What they care about**
- Reducing **breach impact** — when (not if) one workload is compromised, it must not become 500.
- Surviving **ransomware** — lateral movement is how a single intrusion becomes an enterprise event.
- **Audit and board narrative** — being able to *show* documented least-privilege segmentation.
- **Cyber-insurance** — segmentation is increasingly a renewal/eligibility question.
- Doing all of the above **without a wall of new headcount** or breaking the business.

**What they fear / objections**
- "We tried segmentation before and it broke apps / never finished."
- "Is this another tool my team can't operate?"
- "How is this different from the firewalls and NAC I already bought?"

**How to approach**
- Open with **blast radius**, not features: *"Today, if one server is popped, how far can the attacker move?"* Most CISOs cannot answer with confidence — that's the opening.
- Frame CSW as a **program, not a project** — visibility → macro → micro, value at each phase, no big-bang.
- Tie to their **board language**: ransomware containment, dwell-time, demonstrable least privilege.

**CSW areas to focus on**
- **Blast-radius reduction** and the ransomware kill-chain story (CSW intervenes between lateral movement and escalation).
- **Phased roadmap** — Phase 2 (macro: prod/non-prod, deny lateral admin protocols) is the fast, low-risk first win.
- **Compliance & audit evidence** (hand off depth to GRC) — point to [CSW-Compliance-Mapping](https://github.com/chandrapati/CSW-Compliance-Mapping).
- **Discovery-first model** — "we observe before we enforce" disarms the "it'll break things" scar.

**Proof points to show**
- A before/after blast-radius / ransomware fan-out visual.
- A 90-day phased plan with a concrete Phase-2 outcome.
- One-page exec summary of which frameworks segmentation supports.

**Metrics that resonate:** % east-west flows under explicit policy · lateral paths removed · prod isolated from non-prod · MTTD/dwell-time trend · audit findings closed.

---

## 2. CIO / VP Infrastructure

**Titles:** CIO, VP IT, Head of Infrastructure / Platform.

**What they care about**
- **Operational risk and uptime** — segmentation must not become an outage generator.
- **Agility** — cloud migration, M&A integration, data-center consolidation without re-architecting security each time.
- **Tool and cost rationalization** — fewer overlapping point products.
- **Team friction** — network vs security ownership wars slow everything down.

**What they fear / objections**
- "Who operates this day-2 — network or security?"
- "Does this slow down my cloud / app-delivery velocity?"
- "Another agent on every server?"

**How to approach**
- Position CSW as the **consistent segmentation layer across DC, cloud, and containers** — one model instead of per-environment one-offs.
- Address **operating-model** head-on: CSW gives security the policy and gives network/cloud the enforcement points they already own.
- Emphasize **automation** (policy-as-code, CMDB/cloud-tag label sync) to counter the "more manual work" fear.

**CSW areas to focus on**
- **Multicloud + container consistency**, agent and agentless options.
- **Automation / API / CI-CD** integration (labels and policy as code).
- **Integration with existing fabric** (ACI, Secure Firewall, cloud SGs) — extend, don't replace.

**Metrics that resonate:** environments under one policy model · time-to-segment a new app · reduction in manual firewall change tickets · migration/M&A integration time.

---

## 3. CTO / Chief Architect — *the visionary / influencer*

**Titles:** CTO, Chief Architect, Distinguished/Principal Architect.

**What they care about**
- **Long-term architecture** — does this fit a 3–5 year Zero Trust / platform strategy?
- **Standards and openness** — APIs, eBPF, Kubernetes-native, multicloud portability.
- Avoiding **lock-in** and dead-end designs.

**How to approach**
- Go **architecture-deep**: the policy "brain" with distributed enforcement (host agent, network, cloud).
- Connect to **Zero Trust reference models** (NIST 800-207) and the broader Cisco security fabric (Hybrid Mesh Firewall, Hypershield direction).
- Respect their intellect — bring a whiteboard, not a pitch.

**CSW areas to focus on**
- The **see → context → discover → simulate → enforce** pipeline as an architectural pattern.
- **Open integration surface** (API, connectors, SIEM, CMDB) and Kubernetes/eBPF direction.
- How CSW slots into a **Zero Trust segmentation architecture** alongside identity and network.

**Metrics that resonate:** architectural fit, integration breadth, portability across clouds, future-proofing.

---

## 4. CFO / Finance & Risk — *the economic gatekeeper*

**Titles:** CFO, Controller, VP Finance, Enterprise Risk Officer.

**What they care about**
- **ROI and TCO** — total cost vs quantified risk reduced.
- **Cyber-insurance economics** — premiums, coverage eligibility, and conditions tied to segmentation.
- **Avoided-cost** of a ransomware event (downtime, recovery, ransom, brand).

**How to approach**
- Speak **money and risk**, not technology: expected-loss reduction, insurance leverage, consolidation savings.
- Bring the **risk-transfer angle**: insurers increasingly ask about segmentation and lateral-movement controls; CSW gives documented evidence.
- Keep it to **one page of numbers** and let the CISO/CIO carry the technical weight.

**CSW areas to focus on**
- **Phased spend** aligned to phased value (don't ask for the whole program up front).
- **Quantified blast-radius reduction** translated to avoided-loss.
- **Insurance/audit evidence** as a tangible deliverable.

**Metrics that resonate:** TCO vs incumbent point tools · estimated avoided-loss · insurance premium/condition impact · consolidation savings.

---

## Cross-cutting tips for the executive room

- **Time-box features.** Executives give you 20 minutes — spend 15 on outcomes, 5 on "how," and offer a deep-dive for their architects.
- **Bring one visual, not forty slides.** The blast-radius before/after and the phased roadmap do most of the work.
- **Always name the next step:** a scoped POV with a defined Phase-2 outcome and the evidence it will produce.
- **Hand off cleanly:** every executive promise (audit evidence, app safety, fabric fit) is *proven* by a downstream persona — set that up explicitly.
