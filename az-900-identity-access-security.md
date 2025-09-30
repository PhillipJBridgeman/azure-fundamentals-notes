# AZ-900: Identity, Access, and Security

## Module Overview
- **Level:** Beginner  
- **Roles:** Administrator, Developer, DevOps Engineer, Solution Architect  
- **XP:** 1200  
- **Focus:** Directory services, authentication methods, access models, Zero Trust, defense in depth, and Microsoft Defender for Cloud.

### Learning Objectives
By the end, you should be able to:
- Describe **Microsoft Entra ID** and **Microsoft Entra Domain Services**.
- Explain **authentication methods** (SSO, MFA, passwordless).
- Describe **external identities** and guest access.
- Explain **Conditional Access**.
- Describe **Azure RBAC** (Role-Based Access Control).
- Understand the **Zero Trust model**.
- Understand **Defense-in-Depth** strategy.
- Explain the purpose of **Microsoft Defender for Cloud**.

---

## 1) Azure Directory Services

### Microsoft Entra ID (cloud identity service)
- Cloud-based **identity and access management**.  
- Supports: authentication, SSO, MFA, self-service password reset, smart lockout.  
- Used by **Microsoft 365, Azure, Dynamics CRM Online**.  
- Benefits IT admins (control access), developers (add identity features), and users (manage own identities).  
- Detects **suspicious sign-ins** (location, devices).  

### Microsoft Entra Domain Services (managed AD in the cloud)
- Provides **domain join, Group Policy, LDAP, Kerberos/NTLM**.  
- Ideal for **legacy apps** that can’t use modern auth.  
- Managed DCs (replica set) deployed in Azure → no patching or config required.  
- One-way sync from Entra ID → Domain Services (not back).  

---

## 2) Authentication Methods

### Single Sign-On (SSO)
- One identity → access multiple apps.  
- Simplifies management, reduces password fatigue.  
- Weakest link = initial authenticator.  

### Multi-Factor Authentication (MFA)
- Requires **two or more factors**:  
  - Something you know (password, challenge Q).  
  - Something you have (phone, token).  
  - Something you are (fingerprint, face).  
- Reduces risk from stolen credentials.  
- Microsoft Entra MFA adds options like phone call, SMS, authenticator app.

### Passwordless Authentication
- Eliminates passwords → replaced with secure alternatives.  
- **Options**:  
  - **Windows Hello for Business** (biometric/PIN tied to device).  
  - **Microsoft Authenticator app** (push notification with biometric/PIN).  
  - **FIDO2 security keys** (USB, NFC, Bluetooth; unphishable standard).  
- Combines **high security + convenience**.  

---

## 3) External Identities
- Allow external users (partners, vendors, customers) to access resources.  
- Users can bring their own identity (Google, Facebook, corporate, etc.).  
- Managed via **Microsoft Entra External ID**.  

### Capabilities
- **B2B Collaboration**: invite guest users with their identity.  
- **B2B Direct Connect**: mutual trust between orgs (Teams shared channels).  
- **B2C**: identity management for consumer apps.  

### Access Reviews
- Guest access can be reviewed and recertified.  
- Ensures outdated or unused guest accounts are removed.  

---

## 4) Conditional Access
- Enforces policies based on **identity signals**: user, device, location, app.  
- Decisions: allow, block, or require MFA.  
- Examples:  
  - Require MFA for admins.  
  - Allow trusted devices only.  
  - Block untrusted locations.  

---

## 5) Role-Based Access Control (RBAC)
- **Principle of least privilege** → only the access needed.  
- Uses **roles** and **scopes**.  

### Roles
- Built-in roles (Owner, Contributor, Reader).  
- Custom roles are possible.  

### Scopes
- Management group → Subscription → Resource Group → Resource.  
- Inheritance applies (parent scope roles apply to children).  

### Enforcement
- Enforced via **Azure Resource Manager**.  
- Allow model → combined role permissions apply.  

---

## 6) Zero Trust Model
- Assumes **breach at all times**.  
- Protects resources as if from **untrusted networks**.  

### Principles
1. **Verify explicitly**: authenticate/authorize using all data.  
2. **Use least privilege access**: JIT/JEA, adaptive policies.  
3. **Assume breach**: segmentation, end-to-end encryption, analytics.  

Traditional = trusted network perimeter.  
Zero Trust = authenticate every request, regardless of location.  

---

## 7) Defense-in-Depth
- Multi-layered security approach (if one layer fails, others protect).  

### Layers (inside-out):
1. **Data** – secure storage, access control.  
2. **Application** – secure coding, secret management.  
3. **Compute** – secure VMs, patching, endpoint protection.  
4. **Network** – segmentation, restrict comms, deny by default.  
5. **Perimeter** – DDoS protection, firewalls.  
6. **Identity & Access** – MFA, SSO, logging.  
7. **Physical Security** – datacenter safeguards.  

---

## 8) Microsoft Defender for Cloud
- **Security posture management + threat protection**.  
- Monitors **Azure, hybrid, and multicloud**.  

### Key Features
- **Assess**: vulnerability scans (VMs, SQL, containers).  
- **Secure**: apply Azure Security Benchmark policies.  
- **Defend**: detect threats, send alerts, enable just-in-time VM access.  

### Protection Areas
- Azure PaaS (App Service, SQL, Storage).  
- Data services (auto classification, vulnerability assessment).  
- Networks (JIT access, adaptive controls).  
- Hybrid (via Azure Arc).  
- Multicloud (AWS, GCP integrations).  

---

## Knowledge Check
1. Which tool varies login requirements based on user signals? → **Conditional Access**  
2. Which security model assumes breach by default? → **Zero Trust**  
3. If a user has multiple RBAC role assignments, what applies? → **Union of all permissions**  

---

## Exam Tips
- **MFA > SSO > Passwordless**: know differences and strengths.  
- **Entra ID vs Domain Services**: ID = IAM in cloud, Domain Services = managed AD for legacy apps.  
- **RBAC**: roles + scopes; inherited hierarchy.  
- **Zero Trust**: verify explicitly, least privilege, assume breach.  
- **Defence-in-Depth**: remember the seven layers.  
- **Defender for Cloud**: assess, secure, defend.  
