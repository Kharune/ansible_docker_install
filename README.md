Ansible Role: Docker Installation

📌 Overview

This Ansible role automates the installation and configuration of Docker on Debian-based systems. It ensures that Docker is properly set up with the latest stable version and configures the system for optimal containerized application deployment.

✅ Features

- Removes old Docker packages (if any)

- Updates system packages

- Installs Docker and its dependencies

- Configures Docker to start on boot

- Adds the user to the docker group

- Ensures Docker is running and verifies installation

📋 Prerequisites

  🛠 Supported Operating Systems (tested)

    Debian 12+

  ⚙️ Required Dependencies

    Ensure the control machine has:

      Ansible 2.10+

      Python 3.6+

      Ansible collection community.docker

    Ensure the target machine has :

      Internet access (for package downloads)

🔑 Privileges

Run playbooks as a user with sudo privileges and SSH keys setup in this role the user is "Control"
