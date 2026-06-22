# 04 — Application & Operations Personas

> Application Owner / App Dev · Operations / Change Management · Procurement / Sourcing
>
> These personas rarely *buy* CSW — but they can **stop** it. The application owner who fears an outage and the procurement lead who wants a bake-off are where deals quietly stall. Turn the app owner from blocker into champion, and keep procurement honest with a clear differentiation story. See the [README](../README.md) for the persona map.

---

## 12. Application Owner / App Dev — *the blocker you must convert*

**Titles:** Application Owner, Dev Lead, Product Owner, DBA, App Support.

**What they care about**
- **"Do not break my application."** This is their entire universe in a segmentation project.
- **Uptime, SLAs, and being blamed** if a rule blocks a legitimate flow.
- **Not becoming a full-time policy reviewer.**
- Sometimes: genuinely **not knowing** all of their app's dependencies.

**What they fear / objections**
- "Security is going to put a firewall in front of my app and break it."
- "I don't have time to map every dependency."
- "When it breaks at 2am, I get paged, not you."

**How to approach**
- Lead with the **discovery-first promise**: *"We observe in monitor mode and simulate before anything is enforced — you'll see exactly what would be blocked before it ever is."*
- Reframe ADM as **a gift to them**: for the first time they get an accurate, current dependency map of *their* application — useful for troubleshooting, migrations, and audits regardless of segmentation.
- Make them a **reviewer with veto in the POV**, not a victim of it. App-owner signoff is a deliverable.
- Show the **rollback** path — enforcement is staged and reversible.

**CSW areas to focus on**
- **ADM** on their specific app — the map sells itself.
- **Monitor → simulate → enforce** with blocked-flow and allowed-transaction evidence.
- **Staged enforcement + rollback** to remove outage fear.

**Proof points:** a live dependency map of one of their apps; a simulation showing "here's what we'd block, here's what stays open."

**Metrics that resonate:** zero app-impacting incidents during POV · dependencies surfaced they didn't know about · app-owner signoff obtained.

> **Convert one app owner into a reference and the rest follow.** Their peers trust them more than they trust you.

---

## 13. Operations / Change Management — *the stability guardian*

**Titles:** IT Operations, NOC, Change/Problem Management, ITIL process owners.

**What they care about**
- **Stability and predictability** — no unplanned change, no surprise outages.
- **Change-window discipline** and proper CAB process.
- **Run-book burden** — who operates and troubleshoots this day-2.
- **Clean rollback** when something goes wrong.

**What they fear / objections**
- "Enforcement changes outside a change window will cause an incident."
- "My team will own the tickets when a flow gets blocked."

**How to approach**
- Respect the **change process**: enforcement rolls out on *their* CAB schedule, in stages, with monitor-mode evidence attached to each change.
- Show **drift detection and alerting** so out-of-band changes are caught, not discovered during an outage.
- Provide **clear day-2 run-books** (agent ops, policy review, rollback).

**CSW areas to focus on**
- **Monitor-mode evidence** to justify each enforcement change in CAB.
- **Alerting + drift detection** and **day-2 operations** tooling.
- **Rollback procedures** and agent operations.

**Metrics that resonate:** changes shipped with zero rollback · drift events caught proactively · MTTR for policy issues · run-book completeness.

---

## 14. Procurement / Sourcing — *the gatekeeper*

**Titles:** Procurement, Strategic Sourcing, Vendor Management, Category Manager.

**What they care about**
- **Price, terms, and contract structure.**
- **Competitive comparison** — they may run a bake-off (Illumio, Guardicore/Akamai, cloud-native SGs, ACI-only, firewall-only).
- **Vendor consolidation** leverage with the broader Cisco relationship.
- **Paper-process timelines.**

**What they fear / objections**
- "Why not just use the segmentation we already pay for (firewalls / ACI / cloud SGs)?"
- "Justify the premium over a cheaper point tool."

**How to approach**
- Arm your **champion** with crisp **differentiation** (the "Completing the segmentation story" matrix: CSW is infrastructure-agnostic, does ADM, automatic lifecycle, vuln + process visibility, all K8s, MITRE detection — where ACI/SD-Access are partial).
- Lean on **platform/consolidation** value and the existing Cisco relationship.
- Tie price to **phased value** and **avoided-loss / insurance** economics from the CFO conversation.

**CSW areas to focus on**
- **Differentiation vs alternatives** (capability matrix) and **consolidation** story.
- **Phased commercial structure** aligned to phased technical value.

**Metrics that resonate:** capability coverage vs competitors · consolidation savings · TCO over the program · time-to-value.

---

## Cross-cutting tips for the application & operations room

- **The discovery-first message is everything here.** "Observe and simulate before we enforce" neutralizes the deepest fear in the building.
- **ADM is a Trojan horse of goodwill** — app owners value the dependency map even before they value segmentation.
- **Run-books and rollback** win Operations; never pitch enforcement without them.
- **Don't let procurement frame it as a commodity** — keep the differentiation matrix in your champion's hands so the bake-off is on *your* terms.
