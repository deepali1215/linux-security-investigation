# Linux Security Investigation

## Overview

A beginner-level Linux security investigation performed in Kali Linux to establish a system baseline and check for signs of suspicious activity.

The investigation focused on running processes, listening ports, active network connections, running services, and login activity.

## Tools & Commands

- **Kali Linux** — Linux environment used for the investigation
- **systemctl** — Reviewed running system services
- **ss** — Checked listening ports and active network connections
- **last** — Reviewed login history
- **who** — Checked currently logged-in users

## Investigation & Findings

### 1. Running Processes

Reviewed running processes and sorted them by CPU usage to identify processes consuming significant system resources.

**Finding:** The highest CPU-consuming processes were normal system and desktop processes. No obviously suspicious process was identified.

### 2. Listening Ports

Used `ss -tuln` to check for TCP and UDP ports waiting for incoming connections.

**Finding:** No listening TCP or UDP ports were displayed at the time of the investigation.

### 3. Active Network Connections

Used `ss -tun` to review active TCP and UDP network connections.

**Finding:** The observed connection was UDP traffic between the Kali VM (`10.0.2.15`) and the VirtualBox network gateway (`10.0.2.2`) using DHCP ports 68 and 67.

### 4. Running Services

Used `systemctl` to review currently running services.

**Finding:** The running services were consistent with a normal Kali Linux desktop environment. No obviously suspicious service was identified.

### 5. Login Activity

Used `last` and `who` to review login history and currently logged-in users.

**Finding:** The login history showed the `kali` user and expected system login-manager activity. Only the `kali` user was currently logged in.

## Evidence

Screenshots from the investigation are available in the [`evidence`](./evidence) folder.

- [`listening-ports.png`](./evidence/listening-ports.png) — Output from `ss -tuln` showing no listening TCP or UDP ports.
- [`active-connections.png`](./evidence/active-connections.png) — Output from `ss -tun` showing the observed DHCP network connection.
- [`login-history.png`](./evidence/login-history.png) — Output from `last` showing login history.

## Conclusion

The investigation established a baseline of the Kali Linux system and reviewed processes, network activity, services, and login activity.

No obvious indicators of suspicious activity were identified during the checks performed. The investigation demonstrates a basic Linux security triage workflow and the importance of collecting evidence before drawing conclusions.

## Skills Demonstrated

- Linux command-line investigation
- Process and service analysis
- Network connection and port analysis
- Basic login and access monitoring
- Security evidence collection
- Documenting investigation findings
