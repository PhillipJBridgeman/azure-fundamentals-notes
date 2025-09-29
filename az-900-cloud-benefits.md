# AZ-900: Describe the Benefits of Using Cloud Services

## 📘 Module Overview
- **Units:** 7  |  **Level:** Beginner  
- **Roles:** Administrator, Developer, DevOps Engineer, Solution Architect  
- **Scope:** High availability & scalability, reliability & predictability, security & governance, manageability

## 🎯 Learning Objectives
By the end, you should be able to:
- Explain **high availability** (HA) and **scalability** benefits.
- Explain **reliability** and **predictability** (performance & cost).
- Explain **security** and **governance** benefits.
- Explain **manageability** benefits (of and in the cloud).

---

## 1) High Availability (HA) & Scalability
**High Availability (HA)**
- Goal: resources **available when needed** despite failures.
- Backed by provider **SLAs** and redundant architecture (zones/regions).

**Scalability**
- Ability to adjust capacity to meet demand and control cost (pay-as-you-go).
- Two patterns:
  - **Vertical scale (up/down):** change size/capacity of a resource (e.g., more CPU/RAM).
  - **Horizontal scale (out/in):** change **number** of instances (e.g., more VMs/containers).

| Scaling Type | What Changes           | Typical Use | Example |
|--------------|------------------------|-------------|---------|
| Vertical     | Resource size/capacity | Quick boost for a single node | Increase VM size |
| Horizontal   | Instance count         | Elastic web/app tiers          | Add/remove VM instances |

**Exam cue:** “Add/remove instances” → **Horizontal** scaling.

---

## 2) Reliability & Predictability
**Reliability**
- Systems recover from failures and continue operating (pillar of the **Well-Architected Framework**).
- Cloud **decentralization/global regions** enable resilient designs and failover.

**Predictability**
- **Performance predictability:** autoscale, load balancing, HA → consistent UX under load.
- **Cost predictability:** real-time usage, budgets/alerts, analytics, calculators (TCO, Pricing).

**Key ideas to recall**
- Architect across **AZs/regions** for resilience.
- Use **autoscale + load balancers** for performance predictability.
- Use **budgets, cost analysis, tags** for cost predictability.

---

## 3) Security & Governance
- Cloud provides **built-in security** and centralized controls; responsibilities vary by **IaaS/PaaS/SaaS**.
- Governance ensures resources meet **corporate/regulated standards** consistently.

**Typical Azure tools to remember**
- **Identity & Access:** Microsoft Entra ID (Azure AD), **RBAC**.  
- **Policy & Compliance:** **Azure Policy**, initiative assignments, compliance dashboards.  
- **Threat Protection:** **Defender for Cloud**.  
- **DDoS Protection:** platform-level defenses; optional DDoS plans.  
- **Patching/Updates:** more provider-managed in PaaS/SaaS models.  
- **Auditing:** activity logs, resource graph, alerts, recommendations.

**Exam cue:** Governance = **standardization + policy compliance** across resources.

---

## 4) Manageability (of vs. in the Cloud)
**Management _of_ the cloud (your resources)**
- **Deploy from templates** (ARM/Bicep) for consistency.
- **Autoscale** on metrics/schedules.
- **Monitor health** and auto-replace failing instances.
- **Alerts** on performance/cost/security signals.

**Management _in_ the cloud (how you operate)**
- **Portal** (GUI), **CLI**, **PowerShell**, **APIs**.
- Automate builds/deploys with pipelines; use IaC for repeatability.

---

## ✅ Quick Knowledge Check (like the module)
1) **Horizontal** scaling = add/remove instances (VMs/containers).  
2) Ability to recover from failures and continue functioning = **Reliability**.

---

## 🧠 Exam Tips
- HA ↔ **SLA/ redundancy**.  
- **Horizontal vs. Vertical** scaling: know the difference and examples.  
- Reliability vs. Predictability: reliability = **resilience**, predictability = **consistent performance & cost**.  
- Governance = **policy + compliance**; Security tools include **RBAC, Policy, Defender for Cloud, DDoS**.  
- Manageability includes **templates, monitoring, autoscale, alerts** and management via **Portal/CLI/PowerShell/APIs**.
