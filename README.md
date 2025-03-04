🚀 Ansible Role: Docker Installation

📌 Overview

This Ansible role automates the installation and configuration of Docker on Debian-based systems. It ensures that Docker is properly set up with the latest stable version and configures the system for optimal containerized application deployment.

✅ Features

✔️ Removes old Docker packages (if any)
✔️ Updates system packages
✔️ Installs Docker and its dependencies
✔️ Configures Docker to start on boot
✔️ Adds the user to the docker group
✔️ Ensures Docker is running and verifies installation

📋 Prerequisites

🛠 Supported Operating Systems (Tested)

Debian 12+

⚙️ Required Dependencies

Ensure the control machine has:

Ansible 2.10+

Python 3.6+

Ansible collection community.docker

Ensure the target machine has:

Internet access (for package downloads)

🔑 Privileges

Run playbooks as a user with sudo privileges and SSH key-based authentication.

In this role, the default user is control.

🚀 Quick Start Guide

1️⃣ Install the Role

Clone this repository or download it:

git clone https://github.com/yourusername/ansible-role-docker.git
cd ansible-role-docker

2️⃣ Configure Inventory, Playbook, and Ansible Configuration

Before running the playbook, ensure the following files are properly configured based on your environment.

Inventory Configuration (hosts.yml)

lab:
  vars:
    ansible_python_interpreter: auto_silent
  hosts:
    192.168.253.130:22450  # Change this based on your environment
preprod:
  children:
    lab:

Playbook Configuration (PB_deploy_docker.yml)

---
- name: Install Docker on Debian
  hosts: preprod  # Change this based on your target group
  remote_user: control  # Change this based on your user
  become: true
  roles:
    - docker_install

Ansible Configuration (ansible.cfg)

Ensure your Ansible configuration is set correctly:

[defaults]
inventory=/home/control/hosts.yml  # Change to your inventory file
transport=paramiko  # Change if you don't use paramiko

3️⃣ Run the Playbook

Run the playbook:

ansible-playbook -i hosts.yml PB_deploy_docker.yml -K

💡 Tip: Use -K to prompt for the sudo password when running as a non-root user.
