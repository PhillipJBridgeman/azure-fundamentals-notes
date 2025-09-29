# AZ-900: Describe Cloud Service Types (IaaS, PaaS, SaaS)

## 📘 Module Overview
- **Units:** 6  |  **Level:** Beginner  
- **Roles:** Administrator, Developer, DevOps Engineer, Solution Architect  
- **Scope:** IaaS, PaaS, SaaS responsibilities, benefits, and typical use cases

## 🎯 Learning Objectives
You should be able to:
- Describe **Infrastructure as a Service (IaaS)**
- Describe **Platform as a Service (PaaS)**
- Describe **Software as a Service (SaaS)**
- Identify **appropriate use cases** for each model

---

## 1) Infrastructure as a Service (IaaS)
**What it is:** Rent raw infrastructure (compute, storage, networking).  
**You manage:** OS, runtime, apps, data, most network config, patching.  
**Provider manages:** Physical DC, hosts, physical network, internet connectivity.

**When to use:**
- **Lift-and-shift** migrations (mirror on-prem to cloud quickly)
- **Dev/Test** environments where you need full control
- Custom stacks that **require OS-level access**

> **Exam cue:** IaaS → **maximum customer control** and responsibility.

---

## 2) Platform as a Service (PaaS)
**What it is:** Managed platform/runtime to build & run apps.  
**You manage:** Application code & data (sometimes limited network/app security).  
**Provider manages:** Infra, OS, runtime, middleware, many DB services & patching.

**When to use:**
- **App development** without managing servers/OS
- **Analytics/BI** services delivered as a platform
- Faster releases with **built-in scalability/HA**

> **Analogy:** Like an IT-managed, domain-joined workstation—updates & patches handled for you.

---

## 3) Software as a Service (SaaS)
**What it is:** Fully managed **application** delivered over the internet.  
**You manage:** Data you enter, user/device access, configuration.  
**Provider manages:** App code, updates, platform, infra, security of the service.

**When to use:**
- **Email & messaging**, **productivity suites**
- **Finance & expense tracking**, CRM, ERP
- Quick time-to-value with the **least admin effort**

> **Exam cue:** SaaS → **least customer responsibility**, fastest adoption.

---

## 4) Shared Responsibility Highlights
| Area / Model | IaaS | PaaS | SaaS |
|---|---|---|---|
| Physical DC / Hosts / Physical Network | Provider | Provider | Provider |
| OS / Runtime / Middleware | **Customer** | Provider | Provider |
| Application Code | **Customer** | **Customer** | Provider |
| Data | **Customer** | **Customer** | **Customer** |
| Patching (OS/Platform) | **Customer** | Provider | Provider |
| Access / Identities / Devices | **Customer** | **Customer** | **Customer** |

**Key memory hook:** Responsibility **decreases** from IaaS → PaaS → SaaS.

---

## 5) Quick Use-Case Map
- **IaaS:** lift-and-shift, custom networking, legacy apps, full control needed  
- **PaaS:** web/mobile APIs, microservices, managed databases, analytics/BI  
- **SaaS:** email/collab, finance/expenses, CRM/ERP, HRIS—**ready-to-use apps**

---

## ✅ Knowledge Check (like the module)
1) Best for lift-and-shift migration? → **IaaS**  
2) Typical model for Finance & Expense tracking? → **SaaS**

---

## 🧠 Exam Tips
- “**Maximum control**” or “OS patching required” → **IaaS**  
- “**Build apps without managing servers**” → **PaaS**  
- “**Fully managed application**” → **SaaS**  
- Always tie back to the **shared responsibility** lineup above.

