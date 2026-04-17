1. Server disk is full. What will you do?

First, check disk usage using df -h and find large files using du -sh *.
Then clean unnecessary logs, old files, or clear /tmp to free space.

---

2. A process is consuming high CPU. How do you fix it?

Use top or htop to identify the process using high CPU.
Then stop it using kill or restart the service if needed.

---


3. Website is not accessible. What steps will you take?

Check if the service is running using systemctl status.
Then verify port using netstat/ss and check firewall or logs.

---


4. You cannot connect to a server via SSH. What could be the issue?

Check if SSH service is running (systemctl status ssh).
Also verify security groups/firewall and correct IP, key, and permissions.

---

5. File got deleted accidentally. How can you recover it?

If backup exists, restore from backup.
Otherwise, recovery is difficult in Linux unless special tools are used immediately.

---

6. A service is not starting. What will you check?

Check logs using journalctl -u service-name.
Look for errors and fix configuration or dependency issues.

---


7. How do you check memory usage in a server?

Use free -h or top to check RAM usage.
This helps identify memory-heavy processes.

---

8. You need to run a task daily at 2 AM. What will you do?

Use a cron job by editing crontab -e.
Schedule the command with timing 0 2 * * *.

---

9. Permissions issue: user cannot access a file. How do you fix it?

Check permissions using ls -l.
Then update using chmod or change ownership using chown.

---

10. Application is slow. How will you troubleshoot?

Check CPU, memory, and disk usage using top, free, iostat.
Also check logs to identify bottlenecks or errors.
