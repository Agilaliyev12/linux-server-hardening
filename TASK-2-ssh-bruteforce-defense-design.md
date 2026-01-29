# Task 2 – SSH Brute-force Attack & Defense Design

## Attack overview
Attackers typically try to guess the password by repeatedly attempting different username and password combinations.
These attacks are usually automated and can generate thousands of login attempts in a very short time.
The goal is to gain unauthorized access to the system by exploiting weak or reused credentials, especially on internet-exposed SSH services.

## Detection signals
Brute-force attempts can be detected by monitoring SSH authentication logs.
Common signals include multiple failed login attempts from the same IP address, repeated authentication failures for the same user, and a high frequency of login attempts within a short time window.
Log entries showing repeated “authentication failure” or “invalid user” messages are strong indicators of an ongoing brute-force attack.

## Defense strategy
A Linux system should respond to repeated failed SSH attempts by automatically limiting or blocking the source of the attack.
After a predefined number of failed login attempts, the attacking IP address should be temporarily banned to stop further attempts.
Temporary bans are preferred because they reduce attack noise without permanently blocking potentially legitimate users.
Automated response mechanisms ensure that the system reacts quickly and consistently without manual intervention.

## Why this matters in production
Ignoring SSH brute-force attacks can lead to compromised credentials and full system access.
Even if the attack does not succeed immediately, continuous login attempts increase system load and log noise, making real incidents harder to detect.
In production environments, successful SSH compromise can result in data theft, service disruption, or the server being used as a pivot point for further attacks.
