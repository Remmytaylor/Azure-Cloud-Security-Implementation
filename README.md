# ☁️ Azure Cloud Security Implementation (IaaS)

## Overview
This project demonstrates the secure implementation of an Infrastructure as a Service (IaaS) environment in Microsoft Azure, designed to meet PCI DSS and FISMA compliance requirements. The implementation focuses on RBAC, Key Vault encryption, and backup and recovery controls following the principle of least privilege.

## 🔐 Role-Based Access Control (RBAC)

Each department was assigned its own Azure Resource Group to enforce isolation and least privilege access.

### IT Resource Group (IT-RG)
**What was implemented:**
- IT department assigned Backup Contributor and Key Vault Contributor
- Full responsibility for system backups and recovery
- Scope-level permissions restricted to IT-owned resources only

**Why this matters:**
- Prevents non-IT users from modifying backup or security configurations
- Aligns with PCI DSS access control requirements

### Accounting Resource Group
**What was implemented:**
- Accounting users limited to Storage Account Contributor
- No access to IT or Marketing resources

**Security benefit:**
- Prevents lateral movement
- Reduces insider threat risk

### Marketing Resource Group
**What was implemented:**
- Marketing users restricted to their own compute and storage resources

**Security benefit:**
- Enforces least privilege
- Eliminates unnecessary access to sensitive financial data

## 🔑 Azure Key Vault & Encryption

Each department was provisioned its own Azure Key Vault to reduce blast radius and meet encryption requirements.

**Key Vaults per department:**
- Accounting Key Vault
- Marketing Key Vault
- IT Key Vault

**What was implemented:**
- Separate Key Vault per Resource Group
- Soft Delete and Purge Protection enabled
- Used for storing:
  - Secrets
  - Encryption keys
  - Certificates

**Why this matters:**
- Encrypts data at rest
- Supports TLS/SSL encryption in transit
- Meets FIPS and PCI DSS requirements

## 💾 Backup & Recovery Configuration

**Backup Policy Details:**
- Daily backups at 7:00 PM ET
- Instant snapshots retained for 3 days
- Daily backups retained for 45 days
- Recovery Point Objective (RPO): 1 day
- Recovery Time Objective (RTO): 36 hours

**Security & Compliance Impact:**
- Protects against ransomware and data loss
- Meets business continuity requirements
- IT department exclusively manages backups

## 🛡️ Shared Responsibility Model (IaaS)

**Azure Responsibilities:**
- Physical infrastructure
- Data center security
- Platform availability

**Customer Responsibilities:**
- VM configuration
- OS patching
- Backup configuration
- RBAC enforcement
- Encryption settings

## 📌 Key Skills Demonstrated
- Microsoft Azure IaaS
- Role-Based Access Control (RBAC)
- Azure Key Vault
- Encryption (at rest & in transit)
- Backup & disaster recovery
- PCI DSS & FISMA alignment
- Cloud security architecture


