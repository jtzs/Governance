# ❓ Frequently Asked Questions (FAQ)

## General

### If I click on a malicious link but close it immediately, what are the potential dangers?
The worst case scenario is that your browser running in elevated mode contains vulnerabilities which allow escaping from the browser sandbox (CVE-2019-5782,CVE-2025-2857, CVE-2025-2783) allowing attackers to run privileged Remote Code Execution (RCE) (CVE-2024-5830, CVE-2025-21342).

However, the value of such 0-day vulnerabilities are typically in the millions and unless you are running a multimillion dollar enterprise or are part of a government you are less likely to be targetted by such attacks. However prudence is always recommended as attackers typically spray attacks are many targets through many vectors especially once the the vulnerability is announced and known exploits are easily available. It is always recommended to patch the devices you are using as soon as reasonably possible.