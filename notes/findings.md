# Security Findings and Defensive Analysis

## Finding 1 - Social-engineering pretext can drive unsafe user action
Risk: High

The simulated phishing message used a trusted-looking support identity, urgent account-update language, and a link encouraging the recipient to download and run a file.

Recommended controls:
- Security awareness training
- Phishing simulations
- Out-of-band verification for unusual requests
- Clear reporting channels

## Finding 2 - Sender identity can be manipulated
Risk: High

The lab demonstrated that SET can use spoofed source-address concepts.

Recommended controls:
- SPF
- DKIM
- DMARC
- Secure email gateway
- Display-name and domain impersonation detection

## Finding 3 - Client-side controls are a key defense
Risk: High

The lab score report identifies client-side security blocking execution as a primary limitation to compromise.

Recommended controls:
- EDR/antimalware
- Application allowlisting
- Attachment sandboxing
- Browser protections
- Least privilege

## Finding 4 - Unexpected files from email should not be executed
Risk: High

The lab identifies avoiding execution of files from email as the primary defense against the demonstrated attack.

Recommended controls:
- Block risky file types
- Quarantine suspicious archives
- Train users to verify unexpected software-update requests
- Require software installation through approved management channels

## Finding 5 - Social engineering is multi-channel
Risk: Medium to High

SET exposed spear-phishing, website, removable-media, wireless, QR-code, PowerShell, and third-party attack-vector concepts.

Recommended controls:
- Expand awareness programs beyond email phishing
- Monitor QR-code and web-based lures
- Restrict removable media
- Harden PowerShell
- Segment wireless networks
