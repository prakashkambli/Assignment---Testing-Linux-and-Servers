Assignment Report
🔹 Task 1: System Monitoring Setup
Steps Taken
•	Installed htop & nmon for CPU, memory, and process monitoring.
•	Used df -h and du -sh /var/* for disk usage tracking.
•	Created /usr/local/bin/sys_monitor.sh script to log CPU, memory, disk, and top processes.
•	Configured cron job to run monitoring script daily at midnight.
Verification (Screenshots/Outputs)
•	Output of df -h and du logs
•	Content of /var/log/system_monitor.log
•	Cron job entry in crontab –l
 

 

________________________________________
🔹 Task 2: User Management and Access Control
Steps Taken
•	Verified users Sarah and Mike exist.
•	Created isolated directories:
o	/home/Sarah/workspace
o	/home/Mike/workspace
•	Set secure permissions (chmod 700) and ownership.
•	Enforced password policy with chage -M 30.
•	Configured /etc/security/pwquality.conf for complexity rules.
Verification (Screenshots/Outputs)
•	Output of ls -ld /home/Sarah/workspace /home/Mike/workspace
•	Output of chage -l Sarah and chage -l Mike
•	Content of pwquality.conf
 
________________________________________

🔹 Task 3: Backup Configuration for Web Servers
Steps Taken
•	Created backup scripts:
o	/usr/local/bin/apache_backup.sh for Sarah’s Apache server (/etc/httpd/, /var/www/html/)
o	/usr/local/bin/nginx_backup.sh for Mike’s Nginx server (/etc/nginx/, /usr/share/nginx/html/)
•	Configured cron jobs: run every Tuesday at 12:00 AM.
•	Stored backups in /backups/ as apache_backup_YYYY-MM-DD.tar.gz and nginx_backup_YYYY-MM-DD.tar.gz.
•	Verified integrity with tar -tzf > verify.log.
Verification (Screenshots/Outputs)
•	ls -lh /backups/ showing backup files.
•	Contents of verification logs (cat /backups/*_verify.log).
•	Cron job entries (crontab -l).
Challenges & Solutions
•	Challenge: Apache service failed due to syntax error in httpd.conf.
•	Solution: Corrected Listen directive to Listen 8080.
•	Challenge: Needed Nginx on port 8000 → updated config.
 

 
 

________________________________________
🔹 Final Summary
•	Task 1: Monitoring in place, logs generated daily.
•	Task 2: Users Sarah & Mike secured with isolated workspaces and enforced password policies.
•	Task 3: Automated backups for Apache & Nginx working with cron jobs and verification logs.

