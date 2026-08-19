# Social Engineering Simulation with SET

## Project Overview

This project documents an **authorized CompTIA Security+ hands-on lab** focused on social-engineering attack simulation and defensive analysis using the **Social-Engineer Toolkit (SET)** in Kali Linux.

The lab demonstrated how a phishing pretext, malicious delivery mechanism, Metasploit listener, and user interaction can combine to create a successful compromise path in a controlled environment. The project emphasizes the **security lessons, attack chain, detection opportunities, and defensive controls** rather than real-world exploitation.

> **Ethical Use Notice:** All activities were performed inside an authorized training environment. This repository is for cybersecurity education, portfolio demonstration, and defensive learning only.

---

## Lab Result

**CompTIA Assisted Live Lab: Using SET to Perform Social Engineering**  
**Score: 100%**

The lab validated successful completion of tasks including:
- Confirming the generated lab payload file
- Confirming the hosted ZIP archive
- Checking Sendmail
- Verifying the listener connection
- Identifying the target host as `MS10`
- Evaluating primary defenses against phishing-based execution

---

## Objectives

- Explore the Social-Engineer Toolkit (SET)
- Identify supported social-engineering attack vectors
- Understand spear-phishing and mass-mailer workflows
- Observe how Metasploit is used to establish a lab listener
- Analyze phishing delivery from attacker and victim perspectives
- Observe how a reverse session can be established in a controlled lab
- Identify client-side protections that can interrupt the attack chain
- Recommend practical defensive controls

---

## Tools and Technologies

| Tool / Technology | Purpose |
|---|---|
| Kali Linux | Security-testing workstation |
| Social-Engineer Toolkit (SET) | Social-engineering simulation framework |
| Metasploit Framework | Lab listener and session handling |
| Meterpreter | Controlled post-exploitation session in the lab |
| Sendmail | Mail delivery in the simulated environment |
| Thunderbird | Victim-side email client |
| Windows Server 2016 | Simulated target host |
| PowerShell | Attack-vector concept explored in SET |
| QR Code / Wireless / Arduino modules | Additional SET attack-vector concepts explored |

---

## Skills Demonstrated

- Social-engineering risk analysis
- Phishing simulation
- Security awareness assessment
- Kali Linux
- SET navigation and configuration
- Metasploit listener validation
- Meterpreter session verification
- Email threat analysis
- Client-side security analysis
- Attack-chain mapping
- Defensive control recommendations
- Ethical security testing

---

## Lab Environment

The lab used two primary systems:

- **KALI** - Kali Linux security-testing VM
- **MS10** - Windows Server 2016 victim VM

The scenario simulated a security team evaluating the organization's susceptibility to social-engineering attacks with explicit authorization.

![Lab Overview](screenshots/01-lab-overview.png)

---

## Phase 1 - Explore SET

SET was launched in Kali Linux and the Social-Engineering Attacks menu was reviewed.

The lab exposed multiple attack-vector categories, including:

- Spear-Phishing Attack Vectors
- Website Attack Vectors
- Infectious Media Generator
- Create a Payload and Listener
- Mass Mailer Attack
- Arduino-Based Attack Vector
- Wireless Access Point Attack Vector
- QRCode Generator Attack Vector
- PowerShell Attack Vectors
- Third Party Modules

![SET Main Menu](screenshots/02-set-main-menu.png)

### Security Observation

The exercise demonstrated that social engineering is not limited to email. Attackers may combine **human trust, malicious links, removable media, spoofed infrastructure, QR codes, wireless techniques, and scripting tools**.

---

## Phase 2 - Spear-Phishing and Delivery Concepts

The spear-phishing module demonstrated how SET can be used to prepare targeted email-based simulations.

![Spear Phishing Module](screenshots/03-spear-phishing-module.png)

The lab also reviewed the Infectious Media Generator, which illustrates how removable media can be used as a delivery vector in social-engineering scenarios.

![Infectious Media Module](screenshots/04-infectious-media-module.png)

### Key Lesson

A technical control alone cannot eliminate phishing risk. A successful attack frequently depends on persuading a user to trust a message, open a link, download a file, or ignore a warning.

---

## Phase 3 - Mailer and Spoofing Concepts

The lab explored SET's mass-mailer functionality and Sendmail integration.

![Sendmail and Mass Mailer](screenshots/05-sendmail-mass-mailer.png)

The simulated message used a trusted-looking sender identity and urgent account-update language to create credibility and pressure.

### Social-Engineering Indicators

The lab highlighted several common warning signs:

- Unexpected account-update request
- Sense of urgency
- Request to download and run a file
- Sender identity that appears trusted
- Embedded hyperlink
- Pressure implying loss of access or certificate expiration

---

## Phase 4 - Additional SET Attack Vectors

SET also presented other attack-vector categories, including QR-code, PowerShell, wireless, Arduino-based, and third-party modules.

![Additional SET Options](screenshots/06-powershell-and-qrcode-options.png)

### Defensive Takeaway

Organizations should treat social engineering as a **multi-channel threat** rather than an email-only problem.

---

## Phase 5 - Controlled Listener and Payload Simulation

In the authorized lab, SET integrated with Metasploit to prepare a controlled listener and demonstrate how a successful user action could create a remote session.

![Payload and Listener Configuration](screenshots/07-payload-listener-configuration.png)

The Metasploit handler was successfully started in the lab environment.

![Listener Started](screenshots/08-listener-started.png)

### Security Observation

The important defensive lesson is that **malicious execution on the endpoint is the critical transition point**. Endpoint protections, application controls, attachment filtering, browser protections, and user awareness can all interrupt this stage.

---

## Phase 6 - Simulated Phishing Email

The lab generated and sent a simulated phishing message.

![Phishing Email Sent](screenshots/09-phishing-email-sent.png)

From the victim perspective, the email appeared as an "Important Account Update" from a support department and contained a link encouraging the user to download an update.

![Phishing Email Received](screenshots/10-phishing-email-received.png)

### Why the Pretext Can Be Effective

The message combined:

1. **Authority** - appears to come from support
2. **Urgency** - implies immediate action is necessary
3. **Fear of consequence** - suggests certificates or access may expire
4. **Convenience** - provides a direct link

These techniques can influence users to bypass normal caution.

---

## Phase 7 - Session Validation

After the simulated victim interaction, the handler became active in the controlled environment.

![Handler Active](screenshots/11-handler-active.png)

The lab then used the established session to verify system information. The target computer name was identified as:

`MS10`

The operating system was shown as Windows Server 2016.

![Meterpreter Sysinfo](screenshots/12-meterpreter-sysinfo.png)

---

## Attack Chain

```text
Social-Engineering Pretext
        |
        v
Phishing Email
        |
        v
User Clicks Link
        |
        v
File Download / Execution Attempt
        |
        v
Endpoint Security Decision
        |
        +---- Blocked ----> Attack Interrupted
        |
        +---- Allowed ----> Controlled Lab Session Established
                               |
                               v
                        System Information Verified
```

This lab demonstrates why social-engineering defense must combine **people, process, and technology**.

---

## Key Findings

### 1. Human Interaction Is a Critical Attack Surface

The simulated attack depended on the victim trusting the message and interacting with the supplied content.

**Risk:** High

**Recommendation:** Conduct recurring phishing-awareness training and simulations.

### 2. Spoofed or Trusted-Looking Sender Identities Increase Credibility

The lab demonstrated that email presentation can be manipulated to appear more trustworthy.

**Recommendation:** Implement SPF, DKIM, DMARC, secure email gateways, and user verification procedures.

### 3. Client-Side Security Controls Can Break the Attack Chain

The lab's score report identifies **client-side security blocking execution** as a primary limitation to successful compromise.

**Recommendation:** Use EDR/antimalware, application allowlisting, attachment scanning, browser protections, and least privilege.

### 4. Users Should Not Execute Unexpected Files from Email

The lab identifies **"Do not execute files from email"** as the primary defense against the demonstrated attack.

**Recommendation:** Train users to validate unexpected requests through a separate trusted communication channel.

### 5. Social Engineering Can Use Multiple Delivery Channels

SET exposes email, website, removable-media, wireless, QR-code, PowerShell, and other attack-vector concepts.

**Recommendation:** Security awareness programs should cover more than traditional phishing email.

---

## Recommended Security Controls

### People
- Security awareness training
- Phishing simulations
- Clear reporting procedures
- Verification of unusual or urgent requests

### Email Security
- SPF
- DKIM
- DMARC
- Secure email gateway
- URL rewriting / scanning
- Attachment sandboxing

### Endpoint Security
- EDR / antivirus
- Application allowlisting
- Least privilege
- PowerShell logging and controls
- Browser download protections
- File reputation and quarantine controls

### Network and Monitoring
- DNS filtering
- Web filtering
- IDS/IPS
- SIEM monitoring
- Detection of unusual outbound connections
- Network segmentation

---

## What I Learned

This lab strengthened my understanding of how a social-engineering attack can progress from a convincing pretext to endpoint interaction and a remote session in a controlled environment.

The most important lesson is that **social engineering succeeds by combining technical capabilities with human behavior**. Effective defense requires layered controls, including user awareness, secure email configuration, endpoint protection, network monitoring, and rapid incident reporting.

---

## Evidence

The `screenshots/` directory contains selected evidence from each major phase of the lab.

The original CompTIA score report is stored in:

`docs/CompTIA_Lab_Score_Report.pdf`

---

## Disclaimer

This project documents an authorized cybersecurity training exercise completed in a controlled CompTIA lab environment. It is intended solely for education, defensive security learning, and professional portfolio demonstration. No unauthorized systems were targeted.
