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
```sudo dnf install -y epel-release
sudo dnf install -y ansible
```
Verify installation:

```ansible --version```

Step 2: Create Ansible Files

Create the following files in your project directory:

install_nginx.yml → Ansible playbook to install Nginx

inventory → List of target servers

Example inventory file
```[webservers]
server1_ip
server2_ip
```

Step 3: Test Connectivity to Target Servers

Before running the playbook, test whether Ansible can connect to the target servers:

``` ansible all -m ping ```

✅ If the result shows SUCCESS, continue to the next step.
❌ If it fails, check SSH access and inventory configuration.

Step 4: Run the Ansible Playbook

Execute the playbook to install Nginx on the target servers:

``` ansible-playbook -i inventory install_nginx.yml ```

Result

After successful execution:

Nginx will be installed on all servers listed in the inventory

Required packages and configurations will be applied automatically
