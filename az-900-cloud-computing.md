# AZ-900: Describe Cloud Computing

## 📘 Module Overview
- **XP:** 900  
- **Duration:** ~23 min (8 units)  
- **Level:** Beginner  
- **Roles:** Administrator, Developer, DevOps Engineer, Solution Architect  
- **Product:** Azure  

This module introduces general **cloud concepts**, deployment models, and the **shared responsibility model**.  
It also explains cloud consumption-based pricing and compares cloud pricing models.

---

## 🎯 Learning Objectives
By the end of this module, you should be able to:
1. Define **cloud computing**.  
2. Describe the **shared responsibility model**.  
3. Define **cloud models**: public, private, hybrid, and multi-cloud.  
4. Identify use cases for each model.  
5. Describe the **consumption-based model**.  
6. Compare **cloud pricing models** (CapEx vs OpEx).

---

## 📝 Key Concepts

### What is Cloud Computing?
- **Definition:** Delivery of computing services over the internet (compute, storage, databases, networking, IoT, AI, ML).  
- **Benefits:** Rapid scalability, flexibility beyond physical datacenters.  

---

### Shared Responsibility Model
- **Cloud Provider Responsible For:**  
  - Physical datacenter (security, power, cooling)  
  - Network infrastructure & physical hosts  

- **Customer Responsible For:**  
  - Data and information  
  - Devices that connect to the cloud  
  - Accounts & identities of people/services  

- **Varies by Service Model:**  
  - **IaaS:** Customer manages most (OS, apps, data).  
  - **PaaS:** Shared responsibilities (runtime, middleware managed by provider).  
  - **SaaS:** Provider manages nearly everything (customer only manages data and use).  

---

### Cloud Deployment Models
- **Private Cloud:**  
  - Used by one organization only  
  - Greater control but higher cost  
  - Can be on-premises or off-site in a dedicated data center  

- **Public Cloud:**  
  - Services provided by third-party provider (e.g., Azure)  
  - Anyone can purchase services  
  - Lower upfront cost, high scalability  

- **Hybrid Cloud:**  
  - Combination of private + public  
  - Flexibility for security, compliance, and temporary demand scaling  

- **Multi-Cloud:**  
  - Use of multiple public cloud providers  
  - Common for organizations migrating or mixing services  

- **Azure Arc:** Extends Azure services across hybrid and multi-cloud environments.  
- **Azure VMware Solution:** Run VMware workloads natively in Azure.  

---

### Consumption-Based Model
- **CapEx (Capital Expenditure):** Upfront spending (datacenters, hardware).  
- **OpEx (Operational Expenditure):** Pay-as-you-go spending.  

**Cloud = OpEx Model**  
- Pay only for what you use.  
- No upfront infrastructure cost.  
- Scale resources up/down as needed.  

---

## 📊 Cloud Pricing Models
- **Pay-as-you-go:** Most common; billed only for usage.  
- **Benefits:**  
  - Easier to plan operating costs  
  - Run infra more efficiently  
  - Scale dynamically with demand  

---

## ✅ Quick Exam Pointers
- Cloud computing = **delivery of services over the internet**.  
- **Hybrid cloud** = mix of public and private (key exam keyword).  
- **IaaS** places most responsibility on the customer.  
- **Consumption model = OpEx, not CapEx**.  
- Know differences between **deployment models** (public, private, hybrid, multi-cloud).  

---

## 📚 Additional Resources
- [Shared Responsibility Model](https://learn.microsoft.com/azure/security/fundamentals/shared-responsibility)  
- [Introduction to Azure Hybrid Cloud Services](https://learn.microsoft.com/azure/azure-arc/overview)  
- [Introduction to Azure VMware Solution](https://learn.microsoft.com/azure/azure-vmware/overview)  
