# Elevate-lab-Task15

# Vulnerability Assessment Report

**Target:** localhost (127.0.0.1)  
**Operating System:** Ubuntu 22.04 LTS  

---

## Executive Summary

A vulnerability assessment was performed on the local Ubuntu system.  
The review identified issues ranging from **Critical** to **Medium** severity.

### Primary Causes
- Outdated software components  
- Missing security patches  
- Weak security configurations  

The most serious risks involve an outdated OpenSSH server vulnerable to Remote Code Execution and an outdated Linux kernel with privilege escalation flaws. Immediate remediation is recommended.

---

## Scope and Methodology

### Scope
- Local system services  
- Network services  
- Installed packages  
- Security configurations  

### Methodology
- Nmap for port scanning and service detection  
- Lynis for system auditing and configuration review  
- Manual CVE correlation and CVSS verification  
- Review of Ubuntu Security Notices  

---

## Key Findings

### VULN-001 – Outdated OpenSSH Server
- **Severity:** Critical  
- **CVSS:** 9.8  
- **CVE:** CVE-2024-6387  

OpenSSH 8.9p1 is vulnerable to Remote Code Execution.  
Impact: Full system compromise and root-level access.

---

### VULN-002 – Outdated Linux Kernel
- **Severity:** High  
- **CVSS:** ~7.8  

Kernel 6.1.102 contains multiple vulnerabilities including privilege escalation and denial of service.  
Impact: Kernel-level compromise and service disruption.

---

### VULN-003 – VNC Authentication Enabled
- **Severity:** Medium  
- **CVSS:** 5.3  

VNC service is active on port 5900.  
Risks include weak passwords, brute-force attacks, and potential authentication bypass.

---

### VULN-004 – Weak SSH Configuration
- **Severity:** Medium  
- **CVSS:** 4.3  

Issues include default port usage, root login exposure, and permissive authentication settings.  
Impact: Increased attack surface.

---

### VULN-005 – Missing Security Patches
- **Severity:** High  

Multiple packages have pending security updates.  
Unpatched systems remain exposed to known vulnerabilities.

---

## Risk Priority List

1. **VULN-001 – Outdated OpenSSH (Critical)**
2. **VULN-002 – Outdated Kernel (High)**
3. **VULN-005 – Missing Security Patches (High)**
4. **VULN-004 – Weak SSH Configuration (Medium)**
5. **VULN-003 – VNC Service Exposure (Medium)**

---

## Remediation Summary

- Update OpenSSH to the latest secure version  
- Apply all kernel and package updates  
- Reboot after kernel upgrade  
- Harden SSH configuration  
- Secure or disable VNC service  
- Implement regular patch management  

---

## Conclusion

The system contains critical and high-risk vulnerabilities that could lead to system compromise.  
Timely updates and configuration hardening will significantly reduce risk exposure.

