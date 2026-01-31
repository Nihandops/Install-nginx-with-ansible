# Install Nginx with Ansible

This project demonstrates how to install **Nginx** on target servers using **Ansible automation**.

---

## Step 1: Install Ansible on the Control Server

First, install Ansible on the server from where you will run Ansible commands (control node).

### For Ubuntu / Debian
```bash
sudo apt update
sudo apt install -y ansible
```
### For RHEL / CentOS / Rocky / Alma
sudo dnf install -y epel-release
sudo dnf install -y ansible```
