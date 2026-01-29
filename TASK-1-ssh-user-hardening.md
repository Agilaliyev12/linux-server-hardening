# Task 1 – User Access & SSH Hardening

## What was done
A dedicated administrative user was created to replace direct root usage for daily system administration.
SSH access was restricted so that only this administrative user can connect remotely.
Direct SSH login for the root account was disabled to enforce controlled privilege escalation.

## Why this was done
Direct root access over SSH increases the risk of full system compromise if credentials are exposed.
Using a non-root administrative account with sudo enforces the principle of least privilege and creates a clear separation between authentication and privilege escalation.
Restricting SSH access to a single approved user reduces the server’s external attack surface.

## Risks mitigated
These changes reduce the risk of brute-force attacks targeting the root account.
They limit the impact of credential compromise by preventing immediate full system control.
Unauthorized or unused user accounts are prevented from accessing the server remotely via SSH.
