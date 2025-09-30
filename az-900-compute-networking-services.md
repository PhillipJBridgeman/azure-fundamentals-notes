# AZ-900: Azure Compute and Networking Services

## Module Overview
- **Level:** Beginner  
- **Roles:** Administrator, Developer, DevOps Engineer, Solution Architect  
- **XP:** 1500  
- **Focus:** Azure compute and networking service options, including VMs, containers, functions, app hosting, and connectivity (VNets, VPN, ExpressRoute, DNS).

### Learning Objectives
By the end, you should be able to:
- Compare compute types (VMs, containers, functions).
- Describe VM options: VMs, VM Scale Sets, Availability Sets, Azure Virtual Desktop.
- Identify resources required for VMs.
- Describe app hosting options: Web Apps, Containers, VMs.
- Explain Azure Virtual Networking, VPN Gateway, ExpressRoute, and DNS.
- Define public and private endpoints.

---

## 1) Azure Virtual Machines (VMs)
- **IaaS offering**: Full control of OS and software stack.
- **Use cases**: custom hosting configs, legacy apps, dev/test environments, datacenter extension, disaster recovery, lift-and-shift migrations.
- **Images**: templates with OS + optional software, allow quick provisioning.
- **Resources** needed:
  - Size (CPU, RAM)
  - Disks (HDD/SSD)
  - Networking (VNet, IP, ports)

### Scaling Options
- **VM Scale Sets (VMSS)**:
  - Create/manage load-balanced identical VMs.
  - Autoscale based on demand or schedule.
  - Load balancer included.
- **Availability Sets**:
  - Spread across **update domains** (stagger reboots) and **fault domains** (separate power/network).
  - Resiliency against single hardware/network failures.
  - No extra cost, only pay for VMs.

---

## 2) Azure Virtual Desktop (AVD)
- **Cloud-hosted Windows desktop** service accessible via apps or browser.
- **Security**:
  - Centralized with **Entra ID** (MFA, RBAC).
  - Apps/data separated from devices → reduces data leakage risk.
- **Multi-session**:
  - Windows 10/11 Enterprise multi-session → multiple users per VM.
  - Better consistency vs Windows Server RDS.

---

## 3) Containers
- **Lightweight virtualization**: isolate apps without a full OS.
- **Key benefit**: fast, scalable, restart quickly on failure.
- **Popular engine**: Docker.
- **Comparison with VMs**:
  - VMs = full OS per instance → heavier.
  - Containers = share OS kernel → lighter, faster.
- **Services**:
  - **Azure Container Instances (ACI)**: Fastest, simple PaaS container hosting.
  - **Azure Container Apps**: PaaS with added scaling/load balancing.
  - **Azure Kubernetes Service (AKS)**: Container orchestration for managing fleets.

**Typical use case**: Microservices architecture (front-end, back-end, storage separated into different containers).

---

## 4) Application Hosting Options
- **Virtual Machines**: max control, familiar but more management.
- **Containers**: modular, elastic.
- **Azure App Service (PaaS)**:
  - Host **web apps, APIs, mobile backends, background jobs**.
  - Supports .NET, Node.js, Python, Java, PHP, Ruby.
  - Windows & Linux supported.
  - CI/CD integrations (GitHub, Azure DevOps).
  - Types:
    - Web Apps
    - API Apps (Swagger support, marketplace-ready)
    - WebJobs (background tasks, triggered or scheduled)
    - Mobile Apps (back-end for iOS/Android, push notifications, auth)

---

## 5) Azure Virtual Networking (VNet)
- **Purpose**: Securely connect Azure resources, on-premises, and the internet.
- **Key capabilities**:
  - **Isolation/segmentation**: private IP ranges, subnets.
  - **Internet comms**: assign public IP/load balancer.
  - **Internal comms**: VMs, App Service Environments, AKS.
  - **Service endpoints**: link VNets to services like SQL/Storage.
- **Connectivity to on-premises**:
  - **Point-to-Site VPN**: single device to VNet.
  - **Site-to-Site VPN**: full on-prem to Azure.
  - **ExpressRoute**: private dedicated circuit.
- **Routing**:
  - Custom route tables.
  - Border Gateway Protocol (BGP) for dynamic routing.
- **Traffic filtering**:
  - **NSGs**: inbound/outbound rules.
  - **NVAs**: firewall/WAN optimization appliances.
- **Peering**:
  - Private network connection across VNets/regions.
  - Traffic stays on MS backbone, not the internet.
- **Endpoints**:
  - Public endpoint: accessible globally.
  - Private endpoint: internal VNet IP.

---

## 6) VPN Gateway
- **Encrypted tunnel** across the internet for secure connectivity.
- **Types**:
  - **Policy-based**: static IP rules.
  - **Route-based**: uses routing protocols, more resilient → **preferred**.
- **Use route-based for**: VNet-to-VNet, P2S, multisite, ExpressRoute coexistence.
- **High Availability**:
  - Default **Active/Standby**.
  - **Active/Active** with BGP + dual tunnels.
  - **Zone-redundant gateways** for AZ resiliency.
  - **ExpressRoute failover** possible.

---

## 7) ExpressRoute
- **Private dedicated link** to Microsoft cloud.
- **Not over the internet** → more reliable, secure, consistent latency.
- **Connectivity options**:
  - Cloud exchange colocation
  - Point-to-point Ethernet
  - Any-to-any (WAN integration)
  - Direct ExpressRoute sites
- **Benefits**:
  - Global connectivity (with Global Reach).
  - BGP for dynamic routing.
  - Built-in redundancy in peering locations.
- **Use cases**: Azure, Microsoft 365, Dynamics 365 access with guaranteed performance.

---

## 8) Azure DNS
- **DNS hosting service** with global Azure network.
- **Benefits**:
  - Reliability (anycast, global servers).
  - Security (RBAC, activity logs, resource locks).
  - Ease of use (portal, CLI, APIs).
- **Supports**:
  - Private DNS zones for VNets.
  - Alias records → dynamically track Azure resources (e.g., IPs, CDN, Traffic Manager).
- **Note**: Can’t register domains; buy via App Service domains or 3rd party registrar.

---

## Knowledge Check (from module)
1. Which VM feature staggers updates across domains? → **Availability Sets**  
2. Which service provides cloud-hosted Windows desktops? → **Azure Virtual Desktop**  
3. Which VPN type supports VNet-to-VNet, multisite, and coexistence with ExpressRoute? → **Route-based VPN Gateway**  

---

## Exam Tips
- **VMSS vs Availability Sets**: Scale (auto instances) vs Resiliency (fault/update domains).
- **AVD**: Multi-session Windows 10/11, RBAC + MFA via Entra ID.
- **Containers**: Use ACI for quick tasks, AKS for orchestration.
- **App Service**: Fully managed, CI/CD ready, focus on code, not infra.
- **Networking**:
  - **Endpoints**: Public = global, Private = internal.
  - **VPN Gateway**: Route-based is preferred.
  - **ExpressRoute**: Private, reliable, not internet.
  - **DNS Alias Records**: Auto-updates when resource IP changes.

---
