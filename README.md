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
<img width="1920" height="1080" alt="Screenshot 2026-08-16 110935" src="https://github.com/user-attachments/assets/ff44ad64-7aac-40e3-bb33-0bf68663d54f" />
<img width="1920" height="1080" alt="Screenshot 2026-08-16 111201" src="https://github.com/user-attachments/assets/08e8fb05-6212-4431-958b-177f80c6dd54" />
<img width="1920" height="1080" alt="Screenshot 2026-08-16 111532" src="https://github.com/user-attachments/assets/a05106d0-b253-4a99-9cfd-1ac731263d96" />
<img width="1483" height="762" alt="Screenshot 2026-08-16 112239" src="https://github.com/user-attachments/assets/e9857a03-eee7-447c-a539-5bce5a03ac03" />
<img width="1920" height="1020" alt="Screenshot 2026-08-16 114119" src="https://github.com/user-attachments/assets/5e703437-9393-42e3-8f71-b21da14ccce8" />
<img width="1920" height="1020" alt="Screenshot 2026-08-16 113731" src="https://github.com/user-attachments/assets/15681a71-5caa-441f-88e7-31a4ef0fb3e6" />
<img width="1920" height="1020" alt="Screenshot 2026-08-16 114317" src="https://github.com/user-attachments/assets/a3da7600-42b8-4b97-a939-28a3884e1578" />

## What I Learned

Hands-on experience provisioning cloud infrastructure, securing Linux servers, and automating routine administrative tasks — core skills for cloud support and Linux administration roles.
