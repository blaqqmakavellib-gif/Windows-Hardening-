# SOC Lab #001: Endpoint Hardening & Identity Segregation

## 📌 Overview
This repository documents **SOC Lab #001**, focusing on Windows endpoint hardening and the implementation of the **Principle of Least Privilege (PoLP)**[cite: 4]. The lab simulates a blue team investigation to reduce the attack surface, isolate administrative privileges, and monitor security telemetry on a live Windows environment[cite: 3, 4, 11].

---

## 🛠️ Lab Methodology & Implementation

The lab was executed across five core phases to establish a zero-trust administrative boundary:

*   **Phase 1: Identity Segregation**[cite: 5]
    *   Provisioned a dedicated, password-protected local administrative account (`LocalAdmin`) to hold administrative tokens separately from daily operations[cite: 5].
*   **Phase 2: Privilege Demotion**[cite: 6]
    *   Transitioned the primary daily user profile (`QAZEEMADMIN`) from an "Administrator" to a "Standard User" account to strip master-key system access during day-to-day tasks[cite: 6].
*   **Phase 3: Security Audit & Testing**[cite: 7]
    *   Attempted unauthorized lateral movement from the standard user profile into administrative directories[cite: 7]. 
    *   Verified that the Windows File System (NTFS) successfully blocked access and triggered a UAC password prompt[cite: 7].
*   **Phase 4: Security Insight & Analysis**[cite: 8]
    *   Evaluated risk reduction metrics, confirming that isolating user privileges effectively breaks the persistence chain for common malware[cite: 8].
*   **Phase 5: SOC Monitoring Perspective**[cite: 9]
    *   Mapped defensive strategies to key Windows Event IDs for continuous monitoring and rapid threat detection[cite: 9]:
        *   **Event ID 4720:** User account creation (detecting unauthorized backdoor accounts)[cite: 9].
        *   **Event ID 4625:** Failed logon attempts (monitoring brute-force activity against administrative accounts)[cite: 9].
        *   **Event ID 4672:** Special privileges assigned to new logons[cite: 9].

---

## 📂 Repository Structure

```text
├── images/                  # Forensic screenshots and UI captures
├── report/                  # Official PDF lab documentation
└── README.md                # Project documentation and write-up

```
🔗 Resources & Documentation
Lab Report: You can view or download the complete detailed report here.

👤 Author
Qazeem Samshudeen Temitope

LinkedIn Profile: Qazeem samshudeen Temitope

Email Contact: qazeemsamshudeen@gmali.com
