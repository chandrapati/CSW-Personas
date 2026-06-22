# 03 — Infrastructure & Platform Personas

> Network Architect / Engineering · Cloud / Platform / DevOps · Server / Virtualization / VDI · Identity
>
> These personas own **where CSW runs and enforces**. The network architect in particular is the **most common blocker** — they often feel CSW overlaps with ACI, firewalls, or NAC. The single most important message to all of them: **CSW complements the fabric, it does not replace it.** See the [README](../README.md) for the persona map.

---

## 8. Network Architect / Engineering — *the most common blocker*

**Titles:** Network Architect, Data Center Network Engineer, Fabric/ACI lead, NetOps.

**What they care about**
- **Protecting the fabric** they built (ACI, Nexus, Secure Firewall, SD-Access).
- **Not introducing overlap or conflict** between network policy and a new tool.
- **Performance and stability** — no surprises in the data path.
- Clarity on **who owns what** between network and security.

**What they fear / objections**
- *"This overlaps with ACI / our firewalls — why do we need it?"* (the #1 objection)
- "Agents on every host is operational overhead I'll get blamed for."
- "Is security going to push policy into *my* network?"

**How to approach**
- Lead with **"complement, not replace."** ACI/firewall = macro / fabric (the *front door*); CSW = workload truth + micro (*every room*). Use the ACI-vs-CSW framing: macro now, micro next.
- Offer the **agentless path** (NSEL/ERSPAN/IPFIX, FMC enforcement) so they see CSW respects the network they own.
- Give them **visibility they don't have today** — host + process context the fabric can't see.
- Be explicit about the **operating model**: security writes intent, network keeps its enforcement points.

**CSW areas to focus on**
- **ACI / Secure Firewall integration** and agentless flow ingest — see [CSW-Secure-Firewall-Integration-Guide](https://github.com/chandrapati/CSW-Secure-Firewall-Integration-Guide).
- **Inter-EPG vs intra-EPG** — CSW handles the intra-tier paths ACI alone can't separate.
- **Enforcement placement** flexibility (host, network, cloud) so they choose.

**Metrics that resonate:** east-west visibility gained · intra-EPG paths controlled · firewall rule sprawl reduced · no data-path performance impact.

> **Disarm this persona early.** A CISO-sponsored deal still dies if the network team quietly says "we already have this."

---

## 9. Cloud / Platform / DevOps — *often a fast champion*

**Titles:** Cloud Architect, Platform Engineer, SRE, Kubernetes/Container lead, DevOps.

**What they care about**
- **Consistency across clouds** (AWS, Azure, GCP) and on-prem without per-environment snowflakes.
- **Automation and API-first** — anything manual is a non-starter.
- **No friction in the pipeline** — segmentation must move at CI/CD speed.
- **Container/Kubernetes-native** enforcement.

**What they fear / objections**
- "Will this slow down deploys or break autoscaling?"
- "Is it API-driven or console-clicky?"

**How to approach**
- Speak **automation**: labels and policy as code, drift detection, promotion dev→stage→prod in monitor then enforce.
- Show **cloud connectors** (tag ingestion, flow logs, native SG/NSG/firewall enforcement) and **K8s** support.
- Emphasize **dynamic workloads** — policy follows workloads as they scale/move.

**CSW areas to focus on**
- **Cloud connectors** — [AWS](https://github.com/chandrapati/csw-aws-connector) / [Azure](https://github.com/chandrapati/csw-azure-connector) / [GCP](https://github.com/chandrapati/csw-gcp-connector).
- **Kubernetes/container enforcement** and dynamic workload policy.
- **CI/CD / policy-as-code / API** integration.

**Metrics that resonate:** environments under one policy model · policy applied via pipeline (not console) · time-to-segment a new service · dynamic policy accuracy.

---

## 10. Server / Virtualization / Endpoint Team — *agent gatekeeper*

**Titles:** Wintel/Server team, VMware/virtualization, EUC/VDI, endpoint engineering.

**What they care about**
- **Agent footprint** — CPU/memory impact, stability, support matrix.
- **OS coverage** — including older/legacy systems.
- **Golden-image / VDI** deployment mechanics.
- **Patch and lifecycle** burden of another agent.

**What they fear / objections**
- "Another agent that'll get blamed for every server problem."
- "Will it work on my legacy OS / appliances where I *can't* install an agent?"
- "How does this behave in a non-persistent VDI golden image?"

**How to approach**
- Be **straight about footprint** and the support matrix; offer **deep-visibility vs enforcement** agent modes.
- For systems that can't take an agent, pivot to the **agentless** story (NSEL/ERSPAN) so they don't feel cornered.
- Address **VDI/golden-image** explicitly with the right install pattern.

**CSW areas to focus on**
- **Agent installation** patterns and modes — see [CSW-Agent-Installation-Guide](https://github.com/chandrapati/CSW-Agent-Installation-Guide).
- **Golden-image / VDI** deployment and **specific-version pinning** where change control requires it.
- **Agentless coverage** for legacy/appliance workloads.

**Metrics that resonate:** agent footprint measured · OS coverage achieved · agentless coverage for the un-agentable · clean golden-image rollout.

---

## 11. Identity Team — *the context multiplier*

**Titles:** IAM lead, Active Directory team, Cisco ISE owner.

**What they care about**
- **Identity as policy context** — user/device identity feeding segmentation.
- **ISE / pxGrid** integration health.
- Not having identity data **mishandled** by yet another consumer.

**How to approach**
- Show how **ISE/identity context** enriches CSW labels for user-aware microsegmentation (e.g., admin jump-host paths).
- Keep them informed as an **influencer** — identity-aware policy strengthens the Zero Trust story the architect is building.

**CSW areas to focus on**
- **ISE / pxGrid integration** — see [csw-ise-integration](https://github.com/chandrapati/csw-ise-integration).
- **User/device identity labels** for identity-aware policy and admin-path control.

**Metrics that resonate:** identity-enriched workloads · user-aware policies · admin-path restrictions enforced.

---

## Cross-cutting tips for the infrastructure room

- **"Complement, not replace" is the headline** for the whole room — especially the network architect.
- **Offer choice of enforcement point** (host / network / cloud) so each team keeps what they own.
- **Always have the agentless answer ready** — it removes the "we can't put agents everywhere" wall.
- **Automation is the trust-builder** with cloud/DevOps; manual processes lose them instantly.
