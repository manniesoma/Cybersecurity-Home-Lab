# Cybersecurity Home Lab | Proxmox, OPNsense & Active Directory

**Project:** Virtualized cybersecurity infrastructure and security validation  
**Author:** Emmanuel Uzomefuna | Los Angeles Mission College  
**Documented:** October 2026  
**Status:** Operational foundation; further hardening in progress

## Overview

Built and documented a personally owned cybersecurity lab to practice virtualization, network segmentation, identity management, DNS, Windows/Linux administration, and evidence-based troubleshooting. This project supports a longer-term career goal in DevSecOps engineering.

## Architecture

```text
Administration workstation / home network
                 |
           Proxmox VE host
                 |
           OPNsense firewall
                 |
        Isolated lab subnet
          |       |       |
         DC1    Win11    Kali
       AD/DNS    client  validation
```

The logical diagram is simplified. Lab isolation has been demonstrated for selected IPv4 paths using OPNsense rule logs; IPv6 and alternate network paths still require validation.

## Technologies

- **Virtualization:** Proxmox VE
- **Networking and security:** OPNsense, firewall rules and logs, IPv4, routing, DNS, DHCP
- **Identity:** Windows Server Active Directory Domain Services, organizational units, security groups
- **Endpoints:** Windows domain client, Ubuntu Linux, Kali Linux for authorized lab-only tests
- **Administration and validation:** PowerShell, Command Prompt, Linux shell, SSH

## Verified accomplishments

1. Provisioned virtual machines and established the lab network behind an OPNsense firewall.
2. Applied an IPv4 lab-to-home blocking rule and observed matching deny entries in the firewall logs.
3. Deployed a Windows Server domain controller and DNS service for `cyberlab.test`.
4. Verified Active Directory service discovery using DNS SRV records.
5. Joined a Windows client to the lab domain and authenticated with a standard domain account.
6. Checked group membership, domain-controller discovery, and local administrator membership to support least-privilege validation.
7. Documented troubleshooting steps, expected results, and outstanding security tasks.

## Evidence

The report contains annotated screenshots and technical findings. See **[Manniesoma Lab Project](./Manniesoma%20Lab%20Project.pdf)** once the portfolio-safe PDF is uploaded to this repository.

Selected evidence is described in the report:
- Firewall deny logs: page 9
- Domain controller and DNS: page 10
- Organizational units and password policy: page 11
- Successful domain sign-in and least privilege: page 13
- Troubleshooting and open findings: pages 16–17

## Current limitations and planned next steps

- The workstation organizational-unit move was prepared but **not yet verified** at the report cutoff.
- Verify IPv6 filtering and alternate adapters/bridges before hosting intentionally vulnerable workloads.
- Separate intentionally vulnerable targets from the identity and management environment.
- Validate DHCP DNS options, GPO workstation hardening, and backup/restore recovery.
- Introduce Git-managed Linux configuration, scripts and automated verification; later build an isolated CI/CD project.

## Ethical scope

All security testing is restricted to equipment I own, isolated practice networks, and explicitly authorized training systems. No third-party systems are targeted.

## Privacy notice

Public materials exclude credentials, keys, sensitive device identifiers, and configuration backups. Addresses and hostnames shown in historical lab evidence are educational examples from a privately controlled environment.
