# 05 — Quick-Reference Cheat Sheet

> One line per persona: **what they own · what to say · what to show · the trap to avoid.** Print this before a briefing. Full context in the [README](../README.md) and the persona deep-dives.

---

## What to say / what to show

| Persona | They own | Lead message (say this) | Show this | Trap to avoid |
|---------|----------|-------------------------|-----------|---------------|
| **CISO / VP Security** | Risk & board narrative | "When one workload is popped, it won't become 500." | Blast-radius before/after + phased roadmap | Feature tour instead of outcomes |
| **CIO / VP Infra** | Operating model & cost | "One consistent segmentation layer across DC, cloud, containers." | Multicloud + automation story | Ignoring the network-vs-security ownership question |
| **CTO / Architect** | Long-term architecture | "Policy brain, distributed enforcement, open & Zero-Trust-aligned." | The see→context→discover→simulate→enforce pipeline | Pitching down to a visionary |
| **CFO / Finance** | ROI & insurance | "Quantified risk reduction + cyber-insurance leverage." | One page of TCO / avoided-loss | Tech jargon; multi-page decks |
| **Security Architect** | Design & POV (champion) | "Discover, simulate, then enforce in stages — policy as code." | Live ADM + simulated policy + git diff | Over-simplifying; they want depth |
| **SOC / IR** | Detection & evidence | "Every blocked flow is evidence; contain a scope instantly." | Forensics + MITRE scenario + SIEM feed | Positioning it as more alert noise |
| **GRC / Compliance** | Audit evidence | "Documented least privilege + scope reduction, exportable." | Framework mapping + exported report | Showing a dashboard, not evidence |
| **Network Architect** | The fabric (blocker) | "Complement, not replace — ACI is the front door, CSW is every room." | Agentless/NSEL + inter vs intra-EPG | Sounding like you're replacing ACI/firewall |
| **Cloud / DevOps** | Multicloud & pipelines | "API-first, policy-as-code, dynamic workloads." | Cloud connectors + K8s + CI/CD | Anything manual/console-only |
| **Server / Virtualization** | Agents & OS (gatekeeper) | "Light footprint, broad OS, agentless where you can't install." | Agent modes + VDI pattern + agentless | Hiding footprint/support-matrix reality |
| **Identity team** | Identity context | "Identity-aware policy via ISE/pxGrid." | ISE integration enriching labels | Treating them as irrelevant |
| **Application Owner** | "Don't break my app" (blocker) | "We observe & simulate before we ever enforce." | ADM map of *their* app + simulation | Pitching enforcement before trust |
| **Operations / Change** | Stability & change | "Enforcement on your CAB schedule, staged, with rollback." | Monitor-mode evidence + run-books | Skipping change process / rollback |
| **Procurement** | Price & bake-off | "Platform breadth + consolidation; here's the capability gap vs alternatives." | Differentiation matrix + TCO | Letting it become a commodity bake-off |

---

## CSW capability → who cares most

| CSW capability | Primary persona(s) |
|----------------|--------------------|
| Blast-radius / ransomware containment | CISO, CFO |
| Phased roadmap (visibility→macro→micro) | CISO, CIO, Security Architect |
| ADM (dependency mapping) | Security Architect, Application Owner |
| Monitor → simulate → enforce | Application Owner, Operations, Security Architect |
| Forensics + anomaly detection | SOC / IR |
| Compliance mapping + reports | GRC / Compliance, CISO |
| Agentless (NSEL/ERSPAN/IPFIX) | Network Architect, Server/Virtualization |
| ACI / Secure Firewall integration | Network Architect |
| Cloud connectors + Kubernetes | Cloud / DevOps, CIO |
| Policy-as-code / API / CI-CD / drift | Cloud / DevOps, Security Architect |
| ISE / identity context | Identity team, Security Architect |
| Vulnerability-driven tightening | SOC / IR, Security Architect |
| Differentiation vs competitors | Procurement, CISO |

---

## The three messages that work on (almost) everyone

1. **"Discovery-first — we observe and simulate before we enforce."** (Disarms the app/ops/exec fear of breakage.)
2. **"Complement, not replace — CSW works with your fabric and cloud."** (Disarms the network blocker.)
3. **"Value at every phase — you win at macro before you ever reach micro."** (Disarms the "big scary multi-year project" fear.)
