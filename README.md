# Examining an Open-Source Honeypot

---

## Overview

OpenCanary is an open-source honeypot tool designed to detect unauthorized access by emulating common services attackers target. By mimicking real server behaviors such as FTP, HTTP, SSH, and database services, OpenCanary can lure attackers into interacting with these fake services, triggering alerts and enabling system administrators to take swift action.

This document details the functionality of OpenCanary, the services it emulates, and its practical applications in detecting intrusion attempts.

---

## Ports Enabled and Software Emulated

In the Linux Web Server configuration, OpenCanary enables the following ports and emulates corresponding services:

- **FTP (Port 21):** Displays the banner "FTP server ready."
- **HTTP (Port 80):** Provides the banner "Apache/2.2.22 (Ubuntu)" and optional login skins such as "basicLogin" or "nasLogin," which mimic Synology NAS login pages.
- **SSH (Port 8022):** Simulates an SSH service with the banner "SSH-2.0-OpenSSH_5.1p1 Debian-4," making it appear as a legitimate SSH server.

These services are configured in the `.opencanary.conf` file to emulate real-world server behaviors, enticing attackers to interact with them.

---

## Services Supported by OpenCanary

OpenCanary can natively emulate a wide variety of server types, including:

- **Linux Web Server**
- **Windows Server**
- **MySQL Server**
- **MSSQL Server**

Each service can be customized with specific banners, ports, and login screens to increase realism, enhancing the likelihood of attacker interaction.

---

## Key Features

1. **Customizable Services:** Choose which services to emulate and customize their appearance to mimic genuine systems.
2. **Realistic Banners:** Configure banners to provide authentic-looking service details.
3. **Alert Mechanisms:** Receive notifications via:
   - Email alerts
   - Log files
   - Webhooks
   - Text messages through Correlator (for identifying patterns in attack events)
4. **Cross-Platform Compatibility:** Deployable on a variety of platforms, making it versatile for different environments.

---

## Setting Up OpenCanary

**Where to Set It Up:**
- Deploy OpenCanary on non-critical servers separate from production environments to minimize potential risks.

**How to Set It Up:**
1. Install OpenCanary on the server using package managers or source installation.
2. Edit the `.opencanary.conf` configuration file to define which services to emulate and their respective ports.
3. Start the OpenCanary service, allowing it to monitor interactions in the background.

---

## Alert Mechanisms Upon Intrusion

When an attacker interacts with one of the emulated services, OpenCanary provides several alert options:

- **Logging Events:** Tracks activity for analysis.
- **Email Notifications:** Sends alerts to the administrator's email.
- **Webhooks:** Triggers webhooks to integrate with external alerting systems.
- **SMS Alerts:** Uses tools like Correlator to analyze and notify administrators of suspicious patterns.

---

## Practical Use Cases

1. **Early Intrusion Detection:** Monitor unauthorized access attempts on non-critical systems.
2. **Deception Strategies:** Divert attackers from production systems to honeypots.
3. **Incident Response:** Gain insights into attacker behavior for better incident handling.

---

## Important Notes

- OpenCanary is best used in a controlled environment for monitoring purposes.
- Unauthorized deployment in non-controlled environments may violate ethical and legal guidelines.

---

## References

- [OpenCanary Official Website](https://opencanary.org)
- [GitHub Repository for OpenCanary](https://github.com/thinkst/opencanary)

For more details, see the [Examining an Open-Source Honeypot Project](https://github.com/StephVergil/Examining-an-Open-Source-Honeypot/blob/main/Homework%2013%20Examining%20an%20Open-Source%20Honeypot-Stephanie%E2%80%99s%20MacBook%20Pro.docx).
