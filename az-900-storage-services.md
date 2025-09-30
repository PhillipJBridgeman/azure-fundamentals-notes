# AZ-900: Azure Storage Services

## 📘 Module Overview
- **Level:** Beginner  
- **Roles:** Administrator, Developer, DevOps Engineer, Solution Architect  
- **XP:** 1000  
- **Focus:** Storage accounts, redundancy, tiers, storage services, and data migration/movement tools.

### 🎯 Learning Objectives
By the end, you should be able to:
- Compare Azure storage services.
- Describe storage tiers.
- Explain redundancy options.
- Describe storage account types.
- Identify file movement tools (AzCopy, Storage Explorer, File Sync).
- Describe migration options (Azure Migrate, Data Box).

---

## 1) Azure Storage Accounts
- **Namespace**: Each account = unique namespace accessible globally via HTTP/HTTPS.  
- **Secure, durable, scalable, highly available**.  
- **Endpoints format**:  
  - Blob → `https://<account>.blob.core.windows.net`  
  - Data Lake Gen2 → `https://<account>.dfs.core.windows.net`  
  - Files → `https://<account>.file.core.windows.net`  
  - Queue → `https://<account>.queue.core.windows.net`  
  - Table → `https://<account>.table.core.windows.net`

### Account Types
| Type | Services | Redundancy | Use case |
|------|----------|------------|----------|
| Standard GPv2 | Blob, Queue, Table, Files | LRS, ZRS, GRS, RA-GRS, GZRS, RA-GZRS | Most scenarios, default |
| Premium block blobs | Blob only | LRS, ZRS | High IOPS, small object workloads, low latency |
| Premium file shares | Azure Files only | LRS, ZRS | Enterprise/high-perf file shares, SMB + NFS |
| Premium page blobs | Page blobs only | LRS | Scenarios needing page blobs (e.g., disks) |

---

## 2) Storage Redundancy Options
**Replication within primary region (always three copies):**
- **LRS**: Local, three copies in a single DC. 11 9’s durability. Lowest cost, least resilient.  
- **ZRS**: Across three availability zones. 12 9’s durability. Data is accessible even if the zone is down.

**Replication to secondary region (region pairs):**
- **GRS**: LRS in primary + async copy to LRS in paired region. 16 9’s durability.  
- **GZRS**: ZRS in primary + async copy to LRS in paired region. 16 9’s durability, max resiliency.  
- **Read access**:  
  - **RA-GRS / RA-GZRS** → read access to secondary region (data may lag due to RPO <15 min).

---

## 3) Azure Storage Services
- **Blobs**: Object storage, unstructured data, Data Lake Gen2, supports analytics.  
  - Use cases: media streaming, backups, logs, distributed access.  
  - **Access tiers**:  
    - **Hot**: frequent access.  
    - **Cool**: infrequent (≥30 days).  
    - **Cold**: infrequent (≥90 days).  
    - **Archive**: rarely accessed (≥180 days), cheapest, highest latency.  

- **Files**: Managed file shares with **SMB** or **NFS** protocols.  
  - Fully managed, accessible from Windows/Linux/macOS.  
  - **Azure File Sync** adds local caching and cloud tiering.  

- **Queues**: Messaging service for async workflows.  
  - Millions of messages possible, up to 64 KB each.  
  - Works with **Azure Functions** for event-driven automation.  

- **Disks**: Managed block-level storage for VMs.  
  - Like physical disks, but virtualized and resilient.  

- **Tables**: NoSQL datastore for large amounts of structured, non-relational data.  
  - Accessible via REST API or client libraries.  

---

## 4) File Movement Tools
- **AzCopy**: CLI tool to copy/upload/sync blobs/files. One-way sync.  
- **Azure Storage Explorer**: GUI client for managing storage, built on AzCopy.  
- **Azure File Sync**: Keeps on-prem Windows Server file shares in sync with Azure Files.  
  - Bi-directional sync.  
  - Cloud tiering for local caching.  
  - Supports SMB, NFS, FTPS.  

---

## 5) Migration Options
- **Azure Migrate** (hub for assessments and migrations):  
  - Discovery & Assessment (VMs, servers, workloads).  
  - Server Migration (VMware, Hyper-V, physical, cloud VMs).  
  - Database Migration Service (SQL → Azure SQL).  
  - App Service Migration Assistant (web apps → App Service).  
  - Data Migration Assistant (assess SQL compatibility).  

- **Azure Data Box** (offline transfer service):  
  - Rugged device (up to 80 TB) shipped to customer.  
  - Supports bulk transfer, periodic uploads, DR recovery, and compliance-driven exports.  
  - Wipes disks per **NIST 800-88r1** after use.  

---

## ✅ Knowledge Check
1. Which tool keeps on-prem Windows server and Azure synced? → **Azure File Sync**  
2. Which redundancy option offers **16 nines durability**? → **Geo-Zone-Redundant Storage (GZRS)**  
3. Which service supports big data analytics and unstructured data? → **Azure Blobs**  

---

## 🧠 Exam Tips
- **Account Types**: GPv2 = default, Premium = low latency/high performance.  
- **Redundancy**: LRS < ZRS < GRS < GZRS (RA versions = read secondary).  
- **Blobs**: Know tier use cases (Hot vs Cool vs Cold vs Archive).  
- **Files vs File Sync**: Azure Files = cloud share, File Sync = hybrid with local cache.  
- **Migration**: Azure Migrate = ongoing migration hub, Data Box = offline bulk.  
