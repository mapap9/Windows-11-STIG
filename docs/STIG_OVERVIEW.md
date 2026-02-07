# STIG Overview – Windows 11 (v2r6)

## STIG Identification

- **Product:** Microsoft Windows 11
- **STIG Name:** Windows 11 Security Technical Implementation Guide
- **Version:** v2r6
- **Publisher:** Defense Information Systems Agency (DISA)
- **Source:** DoD Cyber Exchange (https://www.cyber.mil)

This repository is based on the **Windows 11 STIG v2r6** baseline and aligns with DISA-provided guidance and enforcement methods.

---

## Enforcement Methodology

### Local Group Policy (LGPO)

STIG enforcement in this repository is performed using **LGPO.exe**, as provided by Microsoft and referenced in DISA documentation.

The **LGPO utility and scripts provided by Cyber.mil** were used to:

- Back up existing local policy
- Apply DISA STIG GPO templates to standalone systems
- Validate that policy-based controls were correctly enforced

This approach allows STIG remediation without requiring Active Directory, while maintaining alignment with official DISA GPO baselines.

Example workflow:
1. Download DISA Windows 11 STIG GPO package
2. Extract GPO content and LGPO tooling
3. Back up existing local policies
4. Apply STIG GPOs using LGPO.exe
5. Validate applied settings

---

## Control Coverage Summary

The Windows 11 STIG includes controls that fall into multiple enforcement categories.

### Covered in This Repository
- Account policies (passwords, lockout)
- Local security options
- User rights assignments
- Advanced audit policy configuration
- Windows Firewall settings
- Defender and endpoint protection policies
- Administrative Template (ADMX)–based settings

These controls are enforced via **GPO/LGPO** and documented in the accompanying coverage spreadsheet.

### Not Fully Enforced
The following control types are **out of scope for direct GPO enforcement** and are not fully remediated:

- BitLocker enablement (requires manual action or scripting)
- Secure Boot and TPM requirements
- BIOS/UEFI configuration
- OS edition validation
- Certain application allowlisting controls

These controls are identified as **Manual** or **Combination** in the STIG.

---

## Documentation and Evidence

Detailed mappings of STIG IDs to enforcement methods are documented in:

- `docs/Windows11_STIG_controls.xlsx`

This spreadsheet identifies:
- STIG ID
- Control category
- Enforcement method (GPO / Manual)
- Notes on limitations or assumptions

---

## Assumptions and Dependencies

- Required ADMX templates (including DISA `SecGuide.admx`) are available
- Windows Defender is enabled and active
- Systems are configured for local or domain-based policy processing
- STIG Viewer is used as the authoritative reference for validation

---

## Limitations

- This repository does not replace official compliance validation tools
- Not all STIG findings can be remediated using policy alone
- Validation should always be performed in a controlled test environment

---

## Disclaimer

This repository is provided for **educational and demonstration purposes only**.  
Always validate STIG requirements against organizational policies and mission requirements before production deployment.
