# AZ-900: Describe Azure Architecture and Services

## 📘 Learning Path Overview
- **XP:** 4700  
- **Duration:** ~2 hr 30 min  
- **Modules:** 4  
- **Level:** Beginner  
- **Roles:** Administrator, Developer, DevOps Engineer, Solution Architect  
- **Subjects:** Architecture, Cloud Computing, Technical Infrastructure  

This is Part 2 of the *Azure Fundamentals* series:  
1. **Describe Cloud Concepts**  
2. **Describe Azure Architecture and Services** ← (this file)  
3. **Describe Azure Management and Governance**  

---

## 🎯 Learning Objectives
By the end of this path, you should be able to:
- Identify the **core architectural components of Azure**.  
- Explain **Azure compute services** (VMs, containers, serverless, hosting options).  
- Explain **Azure networking services** (VNET, VPN, ExpressRoute, DNS).  
- Describe **Azure storage services** (types, redundancy, resiliency).  
- Describe **Azure identity, access, and security features**.  

---

## 📝 Modules

### 1) Core Architectural Components of Azure (1000 XP | 48 min | 9 units)
- Physical infrastructure (datacenters, regions, availability zones).  
- Resource hierarchy:
  - **Management Groups → Subscriptions → Resource Groups → Resources**.  
- **Azure Resource Manager (ARM):** Deployment/service management layer.  
- Hands-on: create an Azure resource.  

---

### 2) Azure Compute & Networking Services (1500 XP | 1 hr 1 min | 14 units)
**Compute**
- **Virtual Machines (VMs):** IaaS, full control.  
- **Azure Virtual Desktop:** Remote desktop & app streaming.  
- **Containers:** Lightweight, portable (Azure Container Instances, AKS).  
- **Functions (serverless):** Event-driven, pay-per-execution.  
- **App Hosting:** Azure App Service, Web Apps, Logic Apps.  

**Networking**
- **Virtual Network (VNet):** Logical isolation for resources.  
- **Network Security Groups (NSG):** Control inbound/outbound rules.  
- **VPN Gateway:** Secure on-prem ↔ Azure connections.  
- **ExpressRoute:** Private, dedicated high-speed connection.  
- **Azure DNS:** Host/manage DNS domains in Azure.  
- Hands-on: configure network access.  

---

### 3) Azure Storage Services (1000 XP | 46 min | 9 units)
- **Types of storage:**
  - Blob (object storage, unstructured data).  
  - Disk (VM disks).  
  - File (SMB file shares).  
  - Queue (messaging between apps).  
- **Redundancy/Resiliency:** LRS, ZRS, GRS, RA-GRS.  
- **Distributed infrastructure** → high durability/availability.  

---

### 4) Azure Identity, Access, and Security (1200 XP | 43 min | 11 units)
- **Authentication/Authorization:** Microsoft Entra ID (Azure AD).  
- **RBAC (Role-Based Access Control):** Assign permissions at resource level.  
- **Zero Trust Model:** Verify explicitly, least-privilege access, assume breach.  
- **Security features:** Defender for Cloud, Key Vault, Security Center.  
- **Identity governance:** Conditional access, MFA, PIM.  

---

## ✅ Exam Tips
- **Regions vs Availability Zones:** Regions = multiple DCs in a geography; AZs = physically separate locations within a region.  
- **ARM hierarchy:** Management Groups > Subscriptions > Resource Groups > Resources.  
- **Compute models:** VM (IaaS), Containers (portable), Functions (serverless).  
- **Networking keywords:** VPN Gateway = encrypted internet tunnel; ExpressRoute = private fiber.  
- **Storage types:** Blob = unstructured, Disk = VM OS/data, File = SMB, Queue = messaging.  
- **Redundancy acronyms:** LRS = 1 region, GRS = geo-redundant.  
- **Identity:** Entra ID + RBAC are central for secure governance.  

---
