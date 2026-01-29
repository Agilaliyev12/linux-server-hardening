# Task 4 – auditd SSH Event Monitoring

## What was monitored
SSH-related activities that are critical for security monitoring were tracked using auditd.
This includes execution of the SSH service, user authentication attempts, and privilege escalation actions performed through sudo.
These activities are security relevant because they provide visibility into who accessed the system, how access was obtained, and whether elevated privileges were used.

## Audit rule design logic
Audit rules were designed to focus on high-value security events rather than collecting excessive data.
Monitoring SSH-related binaries helps identify when and how remote access is used.
Tracking authentication and privilege escalation events ensures that any attempt to gain or abuse elevated access is recorded.
The goal was to create meaningful audit logs that support investigation without overwhelming the system with noise.

## Incident investigation value
During a security incident, auditd events allow investigators to reconstruct user activity timelines.
They help identify which account was used, when access occurred, and whether administrative privileges were exercised.
This information is critical for determining the scope of a compromise and for distinguishing b
