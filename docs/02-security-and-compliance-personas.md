# 02 — Security & Compliance Personas

> Security Architect / Zero Trust lead · SOC / IR / Threat · GRC / Compliance / Audit
>
> This is where your **champion** usually lives (Security Architect) and where your **evidence** matters most (SOC and GRC). Go technical and specific — these personas reward depth and punish hand-waving. See the [README](../README.md) for the full persona map.

---

## 5. Security Architect / Zero Trust Lead — *your most likely champion*

**Titles:** Security Architect, Zero Trust Architect, Segmentation Lead, Principal Security Engineer.

**What they care about**
- Designing least-privilege that **actually ships** — they've seen segmentation projects die in spreadsheets.
- **Policy model quality** — scopes, labels, allow-lists that map to how the business really works.
- **Defensibility** — being able to explain and justify every rule.
- Reducing **operational toil** of running segmentation over years.

**What they fear / objections**
- "Will ADM produce a policy mess I have to hand-curate forever?"
- "How do I avoid breaking apps when I flip to enforce?"
- "Can I express policy as code and review it like everything else?"

**How to approach**
- Get into the **policy lifecycle** with them: ADM → review with app owner → monitor → simulate → staged enforcement. Show, don't tell.
- Talk **label strategy** and **scopes** — this is the craft they care about most.
- Show **policy-as-code / API / drift detection** — treat segmentation like infrastructure.

**CSW areas to focus on**
- **ADM (Application Dependency Mapping)** + policy analysis and **simulation** before enforcement.
- **Label/scope architecture** sourced from CMDB, cloud tags, ISE, DNS.
- **Policy-as-code, CI/CD, drift detection** — see [CSW-Policy-Lifecycle](https://github.com/chandrapati/CSW-Policy-Lifecycle).
- **Enforcement placement** options (host agent, Secure Firewall agentless, cloud SGs).

**Proof points:** a live ADM map on one of *their* apps, a simulated policy with blocked vs allowed flows, a policy diff in git.

**Metrics that resonate:** % flows with explicit allow policy · apps modeled · monitor-to-enforce time · policy drift caught.

> **Win the architect and you have a champion who sells internally for you.** Invest here.

---

## 6. SOC / IR / Threat — *the evidence persona*

**Titles:** SOC Manager, Incident Response Lead, Threat Hunter, Detection Engineer.

**What they care about**
- **Detection and dwell-time** — catching lateral movement, not just perimeter events.
- **Forensic evidence** — process + flow context for investigations.
- **Integration with their stack** — SIEM/SOAR (Splunk, etc.), not yet another standalone console.
- **Containment** — the ability to lock down a scope during an active incident.

**What they fear / objections**
- "Is this just more alerts I have to triage?"
- "Does it feed my SIEM or make me pivot to another tool?"

**How to approach**
- Lead with **"every blocked flow is evidence"** — segmentation makes detection *better*, not noisier, because workload behavior becomes bounded and deviations stand out.
- Show **forensics events** and **MITRE ATT&CK-mapped** scenarios (account creation, credential access, RDP exploitation).
- Demonstrate **SIEM integration** patterns (Cisco Security Cloud App, syslog alerts, API-driven feeds).

**CSW areas to focus on**
- **Forensics + flow evidence**, anomaly detection, security dashboard.
- **Absolute policy for active-incident containment** (quarantine a scope fast).
- **Splunk / SIEM integration** — see [csw-splunk-integration](https://github.com/chandrapati/csw-splunk-integration).
- **Vulnerability-driven tightening** when a critical CVE lands.

**Metrics that resonate:** MTTD/dwell-time · lateral-movement detections · time-to-contain a scope · % incidents with workload forensic evidence.

---

## 7. GRC / Compliance / Audit — *the coach who arms your champion*

**Titles:** GRC Manager, Compliance Officer, Internal Audit, Risk & Controls.

**What they care about**
- **Documented, demonstrable segmentation** between regulated and non-regulated systems.
- **Framework mapping** — PCI DSS, HIPAA, SOX, NIST 800-53/CSF, ISO 27001, CMMC, DORA, NIS2, etc.
- **Exportable evidence** for auditors — not screenshots, but reports.
- **Scope reduction** — shrinking the regulated estate (e.g., PCI cardholder data environment).

**What they fear / objections**
- "Can you give me audit-ready evidence, or just a dashboard?"
- "Does this actually reduce my audit scope or just add a control?"

**How to approach**
- Speak **framework language** and map CSW controls to the *specific* frameworks they answer to.
- Emphasize **CDE/scope reduction** — segmenting regulated systems shrinks audit scope and cost.
- Show **exportable reports** as the deliverable auditors accept.

**CSW areas to focus on**
- **Compliance mapping** to their frameworks — point directly to [CSW-Compliance-Mapping](https://github.com/chandrapati/CSW-Compliance-Mapping).
- **Reports** (scheduled compliance/operational reports) and **policy export** as evidence.
- **Segmentation of regulated zones** (PCI CDE, PHI systems) as scope reduction.

**Proof points:** a framework-to-control mapping for *their* top regulation, plus a sample exported segmentation report.

**Metrics that resonate:** audit findings addressed · regulated-scope reduction · evidence-generation time (days → minutes) · control coverage per framework.

---

## Cross-cutting tips for the security & compliance room

- **The architect is your engine.** Spend the most hands-on time here; they run the POV and defend the design internally.
- **The SOC turns segmentation into a detection story** — use them to counter "it's just network plumbing."
- **GRC quantifies the audit/insurance value** the CISO promised upstairs — connect those two explicitly.
- **One POV, three proofs:** an ADM map (architect), a forensic trail (SOC), and an audit export (GRC) — plan the POV to produce all three.
