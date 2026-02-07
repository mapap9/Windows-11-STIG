# Windows 11 STIG Remediation & Baseline

This repository focuses on **remediating and hardening Windows 11 systems** using **DISA Security Technical Implementation Guides (STIGs)** with an emphasis on **Group Policy Object (GPO)**–based enforcement and automation.

It is intended as a **reference and automation showcase** for security operations, compliance, and blue-team engineering roles.

---

## 🛡️ What is a DISA STIG?

The **Defense Information Systems Agency (DISA)** publishes Security Technical Implementation Guides (STIGs) that define secure configuration standards for operating systems, applications, and network devices.

The **Windows 11 STIG** provides:
- Security baselines aligned with DoD and NIST 800-53 controls
- Prescriptive remediation steps
- Audit and validation requirements

STIGs are commonly enforced using:
- Group Policy Objects (GPOs)
- Mobile Device Management (MDM)
- Local Group Policy (LGPO)

---

## 🎯 Project Objectives

- Implement **Windows 11 STIG remediations**
- Apply and validate **STIG GPO baselines**
- Document remediation logic and enforcement methods
- Support **repeatable and auditable compliance**

---

## Source Documentation

Authoritative STIG guidance and examples are sourced from:

- **DISA STIG GPO Downloads**  
  https://www.cyber.mil/stigs/gpo/

- **SecureStrux STIG & GPO Blogs**  
  https://github.com/SecureStrux/Blogs

  ---

## 📁 Repository Structure

```text
├── docs/
│   ├── STIG_OVERVIEW.md
│   └── Windows11_STIG_controls.xlsx
├── CONTRIBUTING.md
└── README.md
```

## Example STIG Controls

| STIG ID        | Control Area       | Description                                          |
| -------------- | ------------------ | ---------------------------------------------------- |
| WN11-CC-000063 | Policy Enforcement | Windows 11 must be managed using GPO or approved MDM |
| WN11-00-000005 | OS Configuration   | Systems must run Windows 11 Enterprise (64-bit)      |
| V-253259       | Disk Encryption    | BitLocker must be enabled                            |
| WN11-SO-000070 | Account Lockout    | Account lockout policies must be enforced            |

## Applying STIGs Using Group Policy
Download the Windows 11 STIG GPO package from DISA

Open Group Policy Management Console (GPMC)

Import the STIG GPO into the domain

Link the GPO to the appropriate Organizational Unit (OU)

Some STIGs require additional ADMX templates (for example, SecGuide.admx) to be installed in the Group Policy Central Store before import.

## Local Policy Enforcement (LGPO)
For standalone or lab systems, Microsoft’s LGPO.exe can be used to apply STIG GPOs locally.

Backup existing local policy

```.\LGPO.exe /b C:\GPO-Backup```

Apply STIG GPO locally

```.\LGPO.exe /g ".\Windows11-STIG-GPO"```

## Compliance Validation
Compliance and validation can be performed using:

STIG Viewer

SCAP Compliance Checker (SCC)

PowerShell auditing scripts

InSpec Windows 11 STIG baselines


## References
DISA STIGs and GPOs

https://www.cyber.mil/stigs/gpo/

SecureStrux Blogs

https://github.com/SecureStrux/Blogs

STIG Viewer

https://public.cyber.mil/stigs/
