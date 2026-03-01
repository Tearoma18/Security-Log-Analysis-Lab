### Security Log Analysis Lab – Failed SSH Detection

## Project Overview

This project demonstrates the detection and analysis of failed SSH authentication attempts on a Linux system. The lab simulates suspicious login activity and analyzes system logs to identify brute-force style behavior.

The objective was to replicate real-world SOC analyst responsibilities involving authentication monitoring and log investigation.

## Lab Environment

Operating System: Kali Linux (Virtual Machine)

Service Analyzed: OpenSSH (sshd)

Log Source: systemd journal

## Tools Used:

systemctl

journalctl

grep

wc

## Objectives

Verify SSH service status

Simulate unauthorized login attempts

Analyze system authentication logs

Filter failed login events

Quantify suspicious activity

## Methodology

Verified SSH service was active.

Generated multiple failed login attempts using a non-existent user.

Reviewed SSH service logs using journalctl.

Filtered logs to isolate failed password entries.

Counted failed login attempts for analysis.

## Findings

A total of 13 failed SSH login attempts were detected.

All attempts targeted a non-existent user account.

Log entries included:

Failed password

pam_unix(sshd:auth)

authentication failure

The system correctly denied all unauthorized access attempts.

The activity pattern simulated a brute-force login attempt scenario.

## Risk Analysis

Repeated failed authentication attempts may indicate:

Brute-force attacks

Credential stuffing

Automated attack scripts

If successful, such activity could result in unauthorized system access and compromise.

## Recommendations

Implement Fail2Ban to block repeated failures

Disable password-based authentication

Use SSH key-based authentication

Limit login attempts

Continuously monitor authentication logs

## Repository Structure
security-log-analysis-lab/
│
├── README.md
│
├── report/
│   └── Security_Log_Analysis_Report.pdf
│
├── screenshots/
│   ├── 01_ssh_status.png
│   ├── 02_failed_login.png
│   ├── 03_log_output.png
│   ├── 04_filtered_failed.png
│   └── 05_failed_count.png
│
└── scans/
    └── failed_attempts.txt

    
## Skills Demonstrated

Log analysis

Event filtering

Suspicious activity detection

Basic incident investigation workflow

Linux command-line proficiency
