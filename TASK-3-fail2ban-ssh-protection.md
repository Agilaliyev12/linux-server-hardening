# Task 3 – fail2ban SSH Protection

## What was implemented
fail2ban was installed and enabled to monitor SSH authentication activity and automatically respond to repeated failed login attempts.
A dedicated SSH jail was configured using fail2ban’s standard mechanisms, without modifying default vendor configuration files.
The solution was designed to protect SSH access while keeping the system behavior predictable and maintainable.

## Design decisions
A limited number of allowed retries was chosen to balance security and usability, ensuring that occasional user mistakes do not result in unnecessary bans.
The ban duration was set to be temporary rather than permanent to reduce the risk of blocking legitimate users while still stopping automated attacks.
Default fail2ban backends were used to avoid overengineering and to stay aligned with common production practices.

## How the system responds to attacks
When an attacker repeatedly attempts to authenticate via SSH with incorrect credentials, fail2ban detects the failed attempts through SSH log analysis.
Once the retry threshold is exceeded, fail2ban automatically blocks the source IP address.
During the ban period, any further SSH connection attempts from that IP are denied.
After the ban time expires, access is automatically restored without manual intervention.

## Validation results
The configuration was tested by simulating multiple failed SSH login attempts from a single source.
After exceeding the allowed retry limit, the source IP was successfully banned and unable to establish new SSH connections.
Once the ban duration expired, SSH access was restored, confirming that the protection works as expected without impacting system stability.
