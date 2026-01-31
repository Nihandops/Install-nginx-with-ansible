nstall Nginx with Ansible This project shows how to install Nginx on target servers using Ansible automation.

Step 1: Install Ansible on the Server First, install Ansible on the server where you will run Ansible commands (control node).

For Ubuntu / Debian sudo apt update sudo apt install -y ansible For RHEL / CentOS / Rocky / Alma bash Copy code sudo dnf install -y epel-release sudo dnf install -y ansible Verify Ansible installation:

bash Copy code ansible --version Step 2: Create Project Directory Create a directory for the Ansible project:

bash Copy code mkdir install-nginx-with-ansible cd install-nginx-with-ansible Step 3: Create Inventory File Create a file named inventory:

bash Copy code vi inventory Add the following content:

ini Copy code [webservers] server1_ip server2_ip Replace server1_ip and server2_ip with your target server IP addresses.

Step 4: Create Ansible Playbook Create a file named install_nginx.yml:

bash Copy code vi install_nginx.yml Add the following content:

yaml Copy code

name: Install Nginx on web servers hosts: webservers become: yes

tasks:

name: Update package cache apt: update_cache: yes

name: Install Nginx apt: name: nginx state: present

Step 5: Test Ansible Connectivity Before running the playbook, test connectivity with the target servers:

bash Copy code ansible all -m ping If the output shows SUCCESS, Ansible can connect to the servers correctly.

Step 6: Run the Ansible Playbook Run the playbook to install Nginx on the target servers:

bash Copy code ansible-playbook -i inventory install_nginx.yml Result After successful execution:

Nginx will be installed on all target servers

Installation is done automatically using Ansible
