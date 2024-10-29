# Ansible-Jenkins-Pipeline

## Project Overview

This project automates the setup and configuration of a remote host using Jenkins and Ansible. It utilizes a Jenkins multi-branch pipeline to accept parameters such as remote host IP, username, password, SSH key, and other configurations, and uses Ansible playbooks to provision the remote host.

### What the Project Should Do

1. **Jenkins Multi-Branch Pipeline**:

   - Accept parameters for remote host setup (IP, username, password, SSH key, package list, and config files).
   - Use the Ansible plugin to execute playbooks to configure the remote host.

2. **Ansible Playbooks**:
   - Create users if they don't exist.
   - Copy SSH keys for future access.
   - Install required packages (e.g., Nginx, MySQL).
   - Apply configuration files as templates for installed software.

### What the Project Actually Does

- The Jenkins pipeline is configured to:
  - Take user input parameters.
  - Connect to the remote host using the provided credentials.
  - Run the Ansible playbooks to configure the host.
- The Ansible playbooks:
  - Set up a user with the given credentials.
  - Install Nginx and MySQL and apply the necessary configurations.

### Gaps and Known Issues

- **Error Handling**: Current setup lacks robust error handling and logging.
- **Documentation**: Needs improvement, especially around Ansible roles and Jenkins configurations.

- [Install file](INSTALL.md)
- [Contributiors](CONTRIBUTIONS.md)
