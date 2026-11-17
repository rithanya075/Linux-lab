
# SRM LINUX COMMAND LIBRARY
## RHEL Practical Questions and Answers

---

# 01. FILE MANAGEMENT

## Practical 1: Create files and directories

Question: Create a directory named project and create two files inside it.

Commands:
```bash
mkdir project
cd project
touch file1.txt file2.txt
ls -l
```

Explanation:
- mkdir creates a directory.
- cd changes the current directory.
- touch creates empty files.
- ls -l displays file details.

## Practical 2: Copy and move files

Question: Copy a file and move it to another directory.

```bash
cp file1.txt backup.txt
mkdir destination
mv backup.txt destination/
ls -l destination/
```

## Practical 3: Remove files and directories

```bash
rm file2.txt
mkdir test
rmdir test
```

## Practical 4: Find files

Question: Find all text files inside /home.

```bash
find /home -type f -name "*.txt"
```

## Practical 5: Change permissions

Question: Give the owner full permissions and others read and execute permissions.

```bash
chmod 755 file1.txt
ls -l file1.txt
```

## Practical 6: Change ownership

```bash
sudo chown root:root file1.txt
ls -l file1.txt
```

---

# 02. PROCESS MANAGEMENT

## Practical 1: Display running processes

```bash
ps aux
ps -ef
top
```

## Practical 2: Find a process

```bash
pgrep sshd
pidof sshd
```

## Practical 3: Terminate a process gracefully

```bash
kill -15 PID
```

Replace PID with the actual process ID.

## Practical 4: Forcefully terminate a process

```bash
kill -9 PID
```

Use only when graceful termination fails.

## Practical 5: Background and foreground jobs

```bash
sleep 300 &
jobs
fg
```

Press Ctrl+Z to suspend a foreground job.

## Practical 6: Monitor system processes

```bash
top
uptime
free -h
ps aux --sort=-%cpu
```

---

# 03. RHEL SERVER MANAGEMENT

## Practical 1: Display system information

```bash
hostnamectl
uname -a
uptime
whoami
```

## Practical 2: Check memory and disk usage

```bash
free -h
df -h
lsblk
```

## Practical 3: Check logged-in users

```bash
who
w
last
```

## Practical 4: Change hostname

```bash
sudo hostnamectl set-hostname server1.example.com
hostnamectl
```

---

# 04. APACHE WEB SERVER

## Practical 1: Install Apache

```bash
sudo dnf install httpd -y
```

## Practical 2: Start and enable Apache

```bash
sudo systemctl enable --now httpd
sudo systemctl status httpd
```

## Practical 3: Create a webpage

```bash
echo "Welcome to LinuxLab" | sudo tee /var/www/html/index.html
```

## Practical 4: Test the web server

```bash
curl http://localhost
```

## Practical 5: Configure firewall

```bash
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --reload
sudo firewall-cmd --list-all
```

---

# 05. FILE TRANSFER

## Practical 1: Connect to a remote server

```bash
ssh username@server_ip
```

## Practical 2: Copy file to remote server

```bash
scp file.txt username@server_ip:/home/username/
```

## Practical 3: Copy file from remote server

```bash
scp username@server_ip:/home/username/file.txt .
```

## Practical 4: Connect using SFTP

```bash
sftp username@server_ip
```

---

# 06. LOG MANAGEMENT

## Practical 1: View system logs

```bash
sudo journalctl
```

## Practical 2: View recent logs

```bash
sudo journalctl -xe
```

## Practical 3: View service logs

```bash
sudo journalctl -u sshd
```

## Practical 4: Monitor logs continuously

```bash
sudo tail -f /var/log/messages
```

---

# 07. SOFTWARE MANAGEMENT

## Practical 1: Display configured repositories

```bash
dnf repolist
```

## Practical 2: Install a package

```bash
sudo dnf install httpd -y
```

## Practical 3: Remove a package

```bash
sudo dnf remove httpd
```

## Practical 4: List installed packages

```bash
rpm -qa
```

## Practical 5: Find package information

```bash
dnf info httpd
```

---

# 08. NETWORKING

## Practical 1: Display IP address

```bash
ip addr
ip -br addr
```

## Practical 2: Display routing table

```bash
ip route
```

## Practical 3: Test connectivity

```bash
ping -c 4 8.8.8.8
```

## Practical 4: Check listening ports

```bash
ss -tulnp
```

## Practical 5: Display network devices

```bash
nmcli device status
nmcli connection show
```

---

# 09. SERVICE MANAGEMENT

## Practical 1: Check service status

```bash
systemctl status sshd
```

## Practical 2: Start a service

```bash
sudo systemctl start sshd
```

## Practical 3: Stop a service

```bash
sudo systemctl stop sshd
```

## Practical 4: Restart a service

```bash
sudo systemctl restart sshd
```

## Practical 5: Enable service at boot

```bash
sudo systemctl enable sshd
```

---

# 10. WEB SERVER CONFIGURATION

## Practical 1: Check Apache configuration

```bash
sudo httpd -t
```

## Practical 2: Display Apache virtual host configuration

```bash
sudo httpd -S
```

## Practical 3: Reload Apache

```bash
sudo systemctl reload httpd
```

---

# 11. DISK AND FILESYSTEM MANAGEMENT

## Practical 1: Display disks

```bash
lsblk
sudo fdisk -l
sudo blkid
```

## Practical 2: Check filesystem usage

```bash
df -hT
du -sh /home
```

## Practical 3: Display mounted filesystems

```bash
findmnt
mount
```

## Practical 4: Check filesystem information

```bash
lsblk -f
```

---

# 12. GIT

## Practical 1: Check Git version

```bash
git --version
```

## Practical 2: Initialize repository

```bash
mkdir gitproject
cd gitproject
git init
```

## Practical 3: Add and commit files

```bash
touch file.txt
git add file.txt
git commit -m "First commit"
```

## Practical 4: Create a branch

```bash
git branch feature
git switch feature
```

## Practical 5: Merge branches

```bash
git switch main
git merge feature
```

---

# 13. LINUX SECURITY

## Practical 1: Check SELinux status

```bash
getenforce
sestatus
```

## Practical 2: Change SELinux mode temporarily

```bash
sudo setenforce 0
sudo setenforce 1
```

## Practical 3: Check firewall

```bash
sudo firewall-cmd --state
sudo firewall-cmd --list-all
```

## Practical 4: Check file permissions

```bash
ls -l
stat file.txt
```

---

# 14. KALI LINUX TOOLS

## Practical 1: Check Nmap version

```bash
nmap --version
```

## Practical 2: Scan an authorized host

```bash
nmap -sV TARGET_IP
```

## Practical 3: Discover authorized network hosts

```bash
nmap -sn NETWORK_CIDR
```

Use only systems and networks you are authorized to test.

---

# 15. MARIADB

## Practical 1: Install MariaDB

```bash
sudo dnf install mariadb-server -y
```

## Practical 2: Start MariaDB

```bash
sudo systemctl enable --now mariadb
```

## Practical 3: Connect to MariaDB

```bash
sudo mariadb
```

## Practical 4: Create database

```sql
CREATE DATABASE college;
SHOW DATABASES;
```

## Practical 5: Create table and insert records

```sql
USE college;

CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50)
);

INSERT INTO students VALUES (1, 'Rahul');
SELECT * FROM students;
```

---

# 16. AWS

## Practical 1: Check AWS CLI version

```bash
aws --version
```

## Practical 2: Configure AWS CLI

```bash
aws configure
```

## Practical 3: Display configured identity

```bash
aws sts get-caller-identity
```

Requires valid AWS credentials and permissions.

---

# 17. PODMAN

## Practical 1: Check Podman version

```bash
podman --version
```

## Practical 2: Download an image

```bash
podman pull nginx
```

## Practical 3: List images

```bash
podman images
```

## Practical 4: Run a container

```bash
podman run -d --name webserver -p 8080:80 nginx
```

## Practical 5: Check running containers

```bash
podman ps
podman ps -a
```

## Practical 6: Test container

```bash
curl http://localhost:8080
```

## Practical 7: Stop and remove container

```bash
podman stop webserver
podman rm webserver
```

---

# 18. SAMBA SERVER

## Practical 1: Install Samba

```bash
sudo dnf install samba samba-client samba-common -y
```

## Practical 2: Create shared directory

```bash
sudo mkdir -p /srv/samba/shared
sudo chmod 2775 /srv/samba/shared
```

## Practical 3: Create Samba user

```bash
sudo useradd sambauser
sudo smbpasswd -a sambauser
```

## Practical 4: Configure Samba

Edit configuration:

```bash
sudo nano /etc/samba/smb.conf
```

Add:

```ini
[shared]
path = /srv/samba/shared
browseable = yes
writable = yes
valid users = sambauser
```

## Practical 5: Validate configuration

```bash
testparm
```

## Practical 6: Start Samba services

```bash
sudo systemctl enable --now smb nmb
```

## Practical 7: Configure firewall

```bash
sudo firewall-cmd --permanent --add-service=samba
sudo firewall-cmd --reload
```

## Practical 8: List Samba shares

```bash
smbclient -L localhost -U sambauser
```

---

# 19. MONGODB

## Practical 1: Configure MongoDB repository

Create repository file:

```bash
sudo nano /etc/yum.repos.d/mongodb-org.repo
```

Repository configuration must match the chosen MongoDB release and RHEL version. Add the official MongoDB repository configuration from its installation documentation.

## Practical 2: Install MongoDB

```bash
sudo dnf install -y mongodb-org
```

## Practical 3: Start MongoDB

```bash
sudo systemctl enable --now mongod
sudo systemctl status mongod
```

## Practical 4: Connect to MongoDB

```bash
mongosh
```

## Practical 5: Create database

```javascript
use college
```

## Practical 6: Create collection

```javascript
db.createCollection("students")
```

## Practical 7: Insert document

```javascript
db.students.insertOne({
  name: "Rahul",
  department: "CSE"
})
```

## Practical 8: Display records

```javascript
db.students.find()
```

## Practical 9: Update record

```javascript
db.students.updateOne(
  { name: "Rahul" },
  { $set: { department: "Cyber Security" } }
)
```

## Practical 10: Delete record

```javascript
db.students.deleteOne({ name: "Rahul" })
```

---

# END OF SRM LINUX COMMAND LIBRARY
