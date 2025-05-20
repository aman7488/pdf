# Nginx Installation Guide for SIT Linux Server

This guide provides two methods for installing Nginx on a RHEL/CentOS 8/9-based Linux server. Choose the appropriate method based on your environment and access permissions.

---

## Method 1: Install Nginx via System Package Manager (Recommended)

### Prerequisites:
- Internet access from the server (for downloading packages)
- `sudo` access

### Steps:

```bash
# Step 1: Install EPEL repository
sudo yum install epel-release -y

# Step 2: Update system packages
sudo yum update -y

# Step 3: Install Nginx
sudo yum install nginx -y

# Step 4: Enable Nginx to auto-start on boot (optional but recommended)
sudo systemctl enable nginx

# Step 5: Start the Nginx service
sudo systemctl start nginx

# Step 6: Verify Nginx installation
nginx -v

# Step 7 (Optional): Check service status
sudo systemctl status nginx
```

---

## Method 2: Install Nginx Using a Local RPM File (Offline or Controlled Environments)

### Prerequisites:
- `.rpm` package provided (`nginx-1.26.1-6.el9.x86_64.rpm` is already there in the path /home/g.fmmisvmapp.001.dev)
- Sudo access to install local packages

### Steps:

```bash
# Step 1: Upload the RPM file to the server

# Step 2: Install the RPM package (use proper path for .rpm file)
sudo dnf install ./nginx-1.26.1-6.el9.x86_64.rpm

# (Alternative if dnf fails)
# sudo rpm -ivh nginx-1.26.1-6.el9.x86_64.rpm

# Step 3: Start the Nginx service
sudo systemctl start nginx

# Step 4 (Optional): Enable Nginx to start on reboot
sudo systemctl enable nginx

# Step 5: Verify Nginx installation
nginx -v
```

---

For any queries, please contact:
Aman Kumar (2010170)
