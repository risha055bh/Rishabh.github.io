# Logic Apps Pwner - Altered Security Red Labs

![Platform](https://img.shields.io/badge/Platform-Microsoft%20Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Provider](https://img.shields.io/badge/Training-Altered%20Security-red?style=flat-square)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow?style=flat-square)
![Labs](https://img.shields.io/badge/Labs-25-blue?style=flat-square)

## About Altered Security Red Labs

[Altered Security](https://redlabs.enterprisesecurity.io) is a cloud security training platform focused on offensive, hands-on learning for Azure and Azure AD (Entra ID) environments. Rather than relying on theory alone, Red Labs provisions **live, disposable Azure tenants** for each challenge, giving learners a real portal, real misconfigurations, and real attack paths to work through — the same conditions a penetration tester or red teamer would face against an actual customer environment.

Each lab starts with a scoped identity (a "compromised user") and a specific misconfiguration to discover and abuse. The goal is always the same: enumerate what access you have, identify what it lets you reach that it shouldn't, and retrieve a flag that proves successful exploitation — followed by understanding the real-world impact and how the misconfiguration should be remediated.

Red Labs is organized into **Learning Paths**, each focused on a specific Azure service or attack phase, including:

| Learning Path | Focus |
|---|---|
| **Logic Apps Pwner** | Abusing Azure Logic Apps workflow permissions, connectors, and triggers |
| **Storage Account Pwner** | Misconfigurations across Azure Storage (Blob, File Share, Table, Queue) |
| **Automation Account Pwner** | Privilege escalation via Azure Automation Accounts and runbooks |
| **Azure AD (Entra ID) Pwner** | Identity and Access Management misconfigurations in Entra ID |
| **Attack Phase – Discovery and Recon** | Unauthenticated and early-access enumeration techniques |
| **Attack Phase – Initial Access** | Techniques for gaining an initial foothold in an Azure environment |
| **Attack Phase – Privilege Escalation and Lateral Movement** | Chaining misconfigurations to escalate privileges and pivot |

---

## About This Repository

This repository tracks my hands-on progress through Altered Security's Red Labs. The plan is to work through **all of the default learning paths** end to end, documenting each completed lab as a detailed, reproducible write-up covering the scenario, exploitation steps, real-world impact, and remediation guidance.

Notes are added incrementally as each lab is completed — this is a living repository, not a finished one. Folders are organized by learning path, mirroring the structure on the Red Labs platform.

### 📂 Logic Apps Pwner

This folder covers the **Logic Apps Pwner** learning path, which focuses on Azure Logic Apps — a workflow automation service commonly connected to sensitive resources like Storage Accounts, Key Vault, and other Azure services via built-in connectors.

The central theme running through this path: **a Logic App's permissions belong to its connections, not to the user editing it.** A user with only read-only or no access to an underlying resource can often still reach it by editing a Logic App workflow that already has a privileged connection configured — turning workflow *edit* access into resource *read* (or worse) access.

Each write-up in this folder follows a consistent structure:

- **Scenario** — the starting access and objective
- **Overview** — the underlying Azure concept being tested
- **Steps to Reproduce** — full walkthrough of the exploitation path
- **Key Points During Flag Finding** — what made the exploit work
- **Impact / Impact in a Real-Time Environment** — why this matters outside a lab
- **Why We Need to Secure This** — the root cause
- **Remediation** — concrete controls to prevent the issue
- **How This Helps During Incident Response** — detection and forensic guidance
- **References** — official Microsoft documentation

Write-ups are added here as each lab in the path is completed. Check back for updates as more labs are covered.

---

## Coverage Plan

- 🟡 **Logic Apps Pwner** — In Progress (documenting labs as completed)
- 🟡 **Attack Phase – Discovery and Recon** — In Progress
- 🟡 **Attack Phase – Initial Access** — In Progress
- 🟡 **Attack Phase – Privilege Escalation and Lateral Movement** — In Progress
- ⚪ **Azure AD (Entra ID) Pwner** — Planned
- ⚪ **Storage Account Pwner** — Planned
- ⚪ **Automation Account Pwner** — Planned

All default learning paths on the platform are planned to be covered over time. This section will be updated as progress is made on each path.

---

## Disclaimer

All labs referenced in this repository were completed on Altered Security's official Red Labs platform using dedicated, disposable training environments provisioned for educational purposes. No production systems, real organizations, or unauthorized targets were involved. Write-ups are intended for defensive education — to help security teams understand, detect, and remediate these classes of misconfiguration in their own environments.

---

## References

- [Altered Security — Red Labs](https://redlabs.enterprisesecurity.io)
- [Azure Logic Apps Documentation](https://learn.microsoft.com/en-us/azure/logic-apps/logic-apps-overview)
- [Microsoft Entra ID Documentation](https://learn.microsoft.com/en-us/entra/identity/)
