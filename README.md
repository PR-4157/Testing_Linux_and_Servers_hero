<img width="942" height="493" alt="Screenshot 2026-01-04 at 6 35 59 PM" src="https://github.com/user-attachments/assets/0185951a-b0d3-4e40-8ed0-9dac9e497d9c" /># DevOps Environment Setup & Automation

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
- Install Monitoring Tools:
    "sudo yum install -y epel-release"
    "sudo yum install -y htop nmon"
    <img width="772" height="133" alt="Screenshot 2026-01-04 at 6 31 29 PM" src="https://github.com/user-attachments/assets/b68607de-f45e-42c2-a1e4-7f009607746c" />

- Monitor CPU, Memory & Processes:
  <img width="942" height="493" alt="Screenshot 2026-01-04 at 6 35 59 PM" src="https://github.com/user-attachments/assets/1552697d-606e-45c3-9479-d6d87e3ec00d" />

- Disk Usage Monitoring:
  * "df -h"
    <img width="954" height="265" alt="Screenshot 2026-01-04 at 6 37 09 PM" src="https://github.com/user-attachments/assets/290406dc-15be-4c85-a7f6-e78ad009cbfa" />
  * "du -sh /var/*"
    <img width="579" height="157" alt="Screenshot 2026-01-04 at 6 38 35 PM" src="https://github.com/user-attachments/assets/3bdbbb36-c160-427a-ac0c-a453c3e9c2c9" />

- Identify Resouces - intensive Processes:
  * "ps aux --sort=-%cpu | head"
    <img width="960" height="327" alt="Screenshot 2026-01-04 at 6 40 10 PM" src="https://github.com/user-attachments/assets/4c3a88ad-fe3a-4544-ba5e-69b94ab37122" />
  * "ps aux --sort=-%mem | head"
    <img width="967" height="338" alt="Screenshot 2026-01-04 at 6 41 06 PM" src="https://github.com/user-attachments/assets/5033ee42-7a9a-476b-9505-f91387c865bd" />

# Task 2: User Management & Access Control (CentOS)
- Objective: Create secure user accounts with isolated workspaces and password policies.

- Implementation:
  * Create Users
    - Sarah
    - mike
  * Set Secure Passwords
  * Create Isolated Workspaces
    - Sarah: /home/Sarah/workspace
    - mike: /home/mike/workspace
  * Ownership & Permissions
  * Enforce Password Expiration
- Security Controls:
  * Directory permissions set to 700
  * Owenship restricted to respective users
  * Password expirations enforced every 30 day
  * Password warning enabled before expiry
   <img width="575" height="487" alt="Screenshot 2026-01-04 at 10 07 19 PM" src="https://github.com/user-attachments/assets/21270fcd-3075-4bf6-a3fa-f39b15cc25f2" />

# Task 3: Backup Configuration for Web Servers (CentOS)
- Objective: Automate weekly backups for Apache and Nginx with verification.

- Implementation:
  * Creat Backups Directory
    "sudo mkdir -p /backups"
    "sudo chmod 755 /backups"
    
- Apache Backup Script (Sarah):
  * /usr/local/bin/apache_backup.sh
    - Configuration: /etc/httpd/
    - Document Root: /var/www/html/
    - Script: apache_backup.sh

- Nginx Backup (mike):
  * /usr/local/bin/nginx_backup.sh
  - Configuration: /etc/nginx/
  - Document Root: /usr/share/nginx/html/
  - Script: nginx_backup.sh

- Backup Schedule:
  * Weekly backups (Tuesday 12:00 AM)
  * Stored in /backups
  * Verified using tar listing
<img width="668" height="188" alt="Screenshot 2026-01-04 at 10 47 21 PM" src="https://github.com/user-attachments/assets/ec73752d-9967-4562-a7cd-0d26b6e6dc75" />
