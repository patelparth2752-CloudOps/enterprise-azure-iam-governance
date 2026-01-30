# ENTERPRISE AZURE IAM & GOVERNANCE PROJECT (AZ-104)

## Overview

This project demonstrates hands-on Azure Identity and Access Management (IAM) and governance skills aligned with the Microsoft AZ-104 Azure Administrator role.

The project focuses on designing secure access using Microsoft Entra ID (Azure AD), implementing Azure RBAC with least privilege, and applying governance controls such as resource tags and locks. All activities follow real-world enterprise best practices with safe cleanup to avoid unnecessary costs.

---

## Azure Services & Skills Covered

- Microsoft Entra ID (Azure Active Directory)
- Azure Role-Based Access Control (RBAC)
- Users and Security Groups
- Resource Group–level access management
- Least privilege access design
- Governance using:
  - Resource Tags
  - Resource Locks
- Access validation and auditing
- Cost management and cleanup

---

## Architecture (Logical View)

Azure Subscription
|
v
Resource Group (rg-iam-governance)
|
+-- RBAC Assignments
| ├── Reader Role → Reader Group
| └── Contributor Role → Admin Group
|
+-- Governance Controls
├── Resource Tags
└── Delete Lock


---

## Project Implementation Phases

### Phase 1: Resource Group Setup
- Created a dedicated Resource Group to scope IAM permissions
- Ensured isolation of access control testing

---

### Phase 2: Identity Design (Entra ID)
- Created test users to simulate enterprise identities:
  - IAM Reader
  - IAM Admin
- Managed identities centrally using Entra ID

---

### Phase 3: Security Groups
- Created security groups for scalable permission management
- Added users to groups instead of assigning roles directly

Groups created:
- `grp-rg-readers`
- `grp-rg-admins`

---

### Phase 4: Azure RBAC Role Assignments
- Assigned **Reader** role to Reader group at Resource Group level
- Assigned **Contributor** role to Admin group at Resource Group level
- Followed least privilege principle

---

### Phase 5: Governance Controls

**Resource Tags**
- Environment: Test
- Owner: IAM-Project
- CostCenter: Training

**Resource Lock**
- Applied a Delete lock at Resource Group level
- Prevented accidental deletion of critical resources

---

### Phase 6: Validation & Testing

**Reader User Validation**
- Can view resources ✔
- Cannot modify or delete resources ❌

**Admin User Validation**
- Can create and manage resources ✔
- Cannot delete Resource Group due to lock ❌

This confirms correct RBAC and governance implementation.

---

### Phase 7: Cleanup & Cost Control
- Removed resource locks
- Deleted Resource Group
- Deleted test users and security groups
- Verified no active or billable resources remain

---

## Key Learnings

- Implemented secure IAM using Azure RBAC and Entra ID
- Designed group-based access following enterprise standards
- Applied governance controls to protect Azure resources
- Validated access using real user testing
- Practiced cost-safe Azure administration

---

## Screenshots (Optional)

Screenshots, if added, are stored in the `screenshots` folder and may include:
- RBAC role assignments
- Security group configuration
- Resource locks
- Access denied validation for Reader user

Example:


