# Work done in Weeks #2 e #3

## Identification

- Description: A path traversal vulnerability in the web interfaces of Buffalo WSR-2533DHPL2 and WSR-2533DHP3 allowed unauthenticated users to bypass authentication.
- Applications/Operating Systems: Buffalo WSR-2533DHPL2 and WSR-2533DHP3 routers with firmware version <= 1.02 and <= 1.24, respectively.

## Cataloging

- Reporting: Reported by Tenable Network Security on August 3, 2021.
- Bug bounty: No bug bounty was offered for this vulnerability, sadly.
- Severity: High.

## Exploit

- Type: Path traversal vulnerability.
- Automation: An exploit for this vulnerability is available in the Metasploit framework.

## Attacks

- Reported use: The vulnerability was reported to be exploited in the wild within two days of its disclosure.
- Potential damage: This vulnerability can be used to gain unauthorized access to a Buffalo WSR-2533DHPL2 or WSR-2533DHP3 router.
- Consequences: This allows the attacker to perform malicious activities, such as stealing sensitive data, installing malware, or disrupting network traffic.
- Mitigation: The vulnerability can be mitigated by upgrading the firmware of the affected routers to version 1.03 or 1.25, respectively.

