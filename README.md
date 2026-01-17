# Configuring and Securing a Network Infrastructure

This project demonstrates how to configure a secure network environment on Ubuntu using UFW (Uncomplicated Firewall) and Bash scripting.

## Features
- System update and firewall installation
- Default deny/allow security rules
- SSH, HTTP, and HTTPS port configuration
- Automation using Bash script
- Validation of firewall rules

## Tools Used
- Ubuntu Linux
- UFW Firewall
- Bash Scripting

## Code
#!/bin/bash
echo "=== Basic Network Security Setup ==="
# 1. Update and install ufw if not present
sudo apt update
sudo apt install ufw -y

# 2. Enable UFW (Ubuntu Firewall)
sudo ufw enable

# 3. Set default policies
sudo ufw default deny incoming
sudo ufw default allow outgoing

# 4. Allow essential services
sudo ufw allow ssh # Allow SSH
sudo ufw allow 80/tcp # Allow HTTP
sudo ufw allow 443/tcp # Allow HTTPS

# 5. Deny everything else explicitly (optional)
# sudo ufw deny 23 # Deny Telnet

# 6. Show status
echo "=== Current Firewall Rules ==="
sudo ufw status verbose
echo "Network Security Configuration Complete."
