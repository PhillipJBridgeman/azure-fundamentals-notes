# AZ-900: Core Architectural Components of Azure

## 📘 Module Overview
- **Units:** 9  |  **Level:** Beginner
- **Roles:** Administrator, Developer, DevOps Engineer, Solution Architect
- **Focus:** Physical infrastructure (DCs, Regions, AZs, Region Pairs, Sovereign Regions) and Management hierarchy (Resources, Resource Groups, Subscriptions, Management Groups)

## 🎯 Learning Objectives
You should be able to:
- Describe **regions**, **region pairs**, and **sovereign regions**
- Describe **Availability Zones (AZs)**
- Describe **Azure datacenters**
- Describe **resources** and **resource groups (RGs)**
- Describe **subscriptions**
- Describe **management groups (MGs)**
- Explain the **hierarchy** across MG → Subscription → RG → Resource

---

## 1) What is Microsoft Azure (quick context)
- A continually expanding set of cloud services to **build, manage, and deploy** apps on a **global network** using your preferred tools and frameworks.
- Goes beyond VMs: **AI/ML**, **IoT**, scalable storage, and more.

---

## 2) Accounts & Subscriptions
- You need an **Azure account**; at least one **subscription** is created to provision resources.
- **Free Account:** 12 months of popular services, 30-day credit, 25+ always-free products.
- **Student Account:** credit + developer tools, **no credit card** required.
- Best practice: complete **cleanup** steps after labs to avoid charges.

---

## 3) Interacting with Azure
- **Azure Portal**: GUI at `https://portal.azure.com`
- **Cloud Shell** (in-portal): PowerShell or Bash; switch with **pwsh** / **bash**
- **Azure CLI**: `az <command>`; try `az version`, `az upgrade`
- **CLI Interactive Mode**: `az interactive` → auto-complete, built-in help

---

## 4) Physical Infrastructure

### Datacenters
- Large facilities with racks, power, cooling, and networking.

### Regions
- **Geographic areas** containing one or more datacenters on a **low-latency network**.
- Some services are **region-specific**; some are **global** (e.g., Entra ID, Traffic Manager, Azure DNS).

### Availability Zones (AZs)
- **Physically separate** datacenters within a region with independent power, cooling, network.
- Purpose: **isolation boundary**—if one zone fails, others continue.
- **Zone-aware patterns**:
  - **Zonal**: you pin a resource to a zone (VMs, managed disks, IPs).
  - **Zone-redundant**: platform replicates across zones (ZRS, SQL DB).
  - **Non-regional**: resilient by design (global services).
- **Note:** Not every region has AZs; AZ-enabled regions have **≥ 3 zones**.

### Region Pairs
- Most regions are paired **≥ 300 miles** apart in the **same geography**.
- Benefits:
  - **Prioritized recovery**—one region in each pair is restored first in large outages.
  - **Staged updates**—rollouts one region at a time to reduce risk.
  - **Data residency** within geography (with exceptions e.g., **Brazil South**).
- **Not automatic** for all services—configure geo-replication/failover as needed.

### Sovereign Regions
- **Isolated** Azure instances for compliance/legal reasons.
  - **US Gov** regions (DoD, Gov Virginia/Iowa, etc.)—operated by screened U.S. personnel.
  - **China** regions (operated by 21Vianet) under separate arrangements.

---

## 5) Management Infrastructure (Logical Hierarchy)

### Resources
- Fundamental units (VMs, VNets, DBs, Functions, etc.).

### Resource Groups (RGs)
- Logical containers for **lifecycle, access, and management**.
- A **resource belongs to exactly one RG** (can be moved, not nested).
- **Actions inherit**: e.g., delete RG → delete all contained resources; RBAC at RG applies to its resources.

### Subscriptions
- Units of **billing, access control, and scale**.
- **Boundaries**:
  - **Billing** boundary: separate invoices/reports by subscription.
  - **Access** boundary: RBAC/policy at subscription scope.
- Use multiple subscriptions to separate **environments** (dev/test/prod), **org units**, or **cost centers**.

### Management Groups (MGs)
- Scope **above** subscriptions for **governance at scale**.
- Apply **Azure Policy** and **RBAC** to MG → inherited by all child subs/RGs/resources.
- **Limits**:
  - Up to **10,000** MGs per directory.
  - Up to **6 levels** deep (excluding root and subscription).
  - Each MG/subscription has **one parent**.
- Typical use: global guardrails (e.g., allowed regions, cost or security baselines) and broad RBAC assignments.

### Full Hierarchy
**Management Group → Subscription → Resource Group → Resource**

---

## 6) Hands-on Pattern (from the exercise)
- Create a VM and **observe** that Azure also creates **dependent resources** (NIC, disk, NSG, etc.) in the **same RG** with related names.
- **Cleanup**: deleting the RG removes all associated resources.

---

## ✅ Knowledge Check (like the module)
1) How many RGs can a resource be in simultaneously? → **One**  
2) What happens when you apply a setting at RG scope? → **Applies to current and future resources in that RG**  
3) What feature replicates across regions ~300 miles apart? → **Region pairs**

---

## 🧠 Exam Tips
- **AZ vs Region Pairs**: AZ = intra-region fault isolation; Region Pair = **geo** resilience & staged updates.
- **Not automatic**: geo-replication/failback often requires **explicit configuration**.
- **RG facts**: no nesting; resource in **one** RG at a time; RG-scope operations **inherit**.
- **Hierarchy memory**: **MG > Sub > RG > Resource**; governance rises as you move **up**.
- **Sovereign** ≠ standard regions; isolated for **compliance/data residency**.

