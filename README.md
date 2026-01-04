# DevOps Environment Setup & Automation

# Overview
To onboard two developers (Sarsh and Mike), a secure, monitored, and automated Linux-based development environment is required.
The setup includes:
* System monitoring
* Secure user management
* Automated weekly backups for web servers
* Logging, verification and documentation

# Task 1: System Monitoring Setup (CentOS)
- Objective: Monitor CPU, Memory, disk usage, and processes to troubleshoot intermittent performance issues and support capacity planning.
- Implementation (CentOS):
  * Install Monitoring Tools
    "sudo yum install -y epel-release"
    "sudo yum install -y htop nmon"
    
