# Examining an Open-Source Honeypot

[Examining an Open Source Honeypot](https://github.com/StephVergil/Examining-an-Open-Source-Honeypot/blob/main/Homework%2013%20Examining%20an%20Open-Source%20Honeypot-Stephanie%E2%80%99s%20MacBook%20Pro.docx)

## What ports does the configuration file enable, and what software is served from these ports?

In the Linux Web Server configuration, OpenCanary enables several ports for emulating services:

- **FTP (Port 21):** Banner set to "FTP server ready."
- **HTTP (Port 80):** Banner "Apache/2.2.22 (Ubuntu)" with optional login skins such as "basicLogin" or "nasLogin" mimicking a Synology NAS login page.
- **SSH (Port 8022):** Banner "SSH-2.0-OpenSSH_5.1p1 Debian-4," designed to appear as a legitimate SSH service.

---

## What are all the services that OpenCanary currently supports faking natively?

OpenCanary can natively emulate several common server types, including:

- Linux Web Server
- Windows Server
- MySQL Server
- MSSQL Server

Each service can be customized with specific banners, ports, and login screens to enhance the illusion of genuine services, increasing the chances that attackers will interact with them.

---

## Summary of OpenCanary

**What is OpenCanary?**  
OpenCanary is an open-source honeypot tool designed to detect unauthorized access by emulating common services attackers target. It works by setting up fake services such as FTP, HTTP, SSH, and server databases and triggering alerts whenever someone tries to access them. The goal is to make attackers think they are interacting with real services, allowing administrators to detect suspicious activity early.

**Where would you set it up?**  
OpenCanary is typically set up on a non-critical server, separate from essential infrastructure, to reduce the risk of operational disruptions.

**How would you set it up?**  
1. Install OpenCanary on the server.
2. Adjust the `.opencanary.conf` configuration file to select the services to emulate and their respective ports.
3. Run OpenCanary in the background to monitor for interactions with the fake services.

**How would you be alerted upon intrusion?**  
If an attacker interacts with one of the fake services, OpenCanary can send alerts through various methods:

- Logging events
- Sending emails
- Triggering webhooks
- Sending text alerts using the Correlator tool, which links separate security events to detect attack patterns

OpenCanary provides administrators with an effective early-warning system against potential intrusions.
