# Work done in Weeks #3 e #4

## Identification

- Description: Authentication bypass in the email verification function due to a random token generation weakness.

- Applications/Operating Systems: WooCommerce Booster plugin version 5.4.3
Wordpress 5.8.1

## Cataloging

- Reporting: Reported by Chloe Chamberland of Wordfence on August 30, 2021.
- Bug bounty: No bug bounty.
- Severity: High.

## Exploit

- Type: Authentication bypass vulnerability.
- Automation: https://www.exploit-db.com/exploits/50299

## Attacks

- Reported use: The probability of exploitation of this CVE in the next 30 days is 2.11%.
- Potential damage: This vulnerability permits attackers to impersonate users and initiate email address verification requests for any accounts. This lets regular users to have administrative privileges, allowing them to gain automatic access to the victim's account and all associated site permissions.
- Consequences: This lets regular users to have administrative privileges, allowing them to gain automatic access to the victim's account and all associated site permissions.
- Mitigation: The vulnerability can be mitigated by upgrading WooCommerce Booster plugin to version 5.4.4.


