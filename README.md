# EC2 Server Monitoring & Automation

Automated a Linux server monitoring system on AWS EC2 using Bash scripting and cron jobs to eliminate manual server health checks.

## What I Built

- Provisioned an AWS EC2 instance (Ubuntu 26.04) with a properly configured security group restricting SSH access to a single trusted IP
- Connected to the instance securely using SSH key-based authentication
- Wrote a Bash script to generate automated disk usage reports
- Scheduled the script to run automatically every day using cron
- Configured secure multi-user access with role-based sudo permissions
- Disabled password-based SSH login and enforced key-only authentication to harden server security

## Tech Stack

- AWS EC2
- Linux (Ubuntu)
- Bash Scripting
- Cron
- SSH / Security Groups

## Steps

### 1. EC2 Instance Setup
- Launched a t3.micro Ubuntu instance
- Configured security group to allow SSH only from my IP
- Connected via SSH using a key pair

### 2. Monitoring Script
Created a Bash script (`check_disk.sh`) to report disk usage:

\`\`\`bash
#!/bin/bash
echo "Disk Usage Report - $(date)"
df -h
\`\`\`

### 3. Automation with Cron
Scheduled the script to run daily at 9 AM:

\`\`\`
0 9 * * * /home/ubuntu/check_disk.sh >> /home/ubuntu/disk_log.txt
\`\`\`

### 4. Secure Multi-User Access
- Created a new user with limited sudo privileges
- Verified group membership and access levels

### 5. SSH Hardening
- Disabled `PasswordAuthentication` in `/etc/ssh/sshd_config`
- Restarted SSH service and verified key-only login works

## Screenshots

*(Add your screenshots here)*

## What I Learned

Hands-on experience provisioning cloud infrastructure, securing Linux servers, and automating routine administrative tasks — core skills for cloud support and Linux administration roles.
