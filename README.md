# Ansible Playbook: Install and Configure Apache HTTP Server

This Ansible playbook installs and configures the Apache HTTP server on a specified target server. It ensures the Apache service is installed, started, enabled on boot, and sets up a basic `index.html` page.

## Prerequisites

- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) installed on the control machine.
- SSH access to the target server(s).
- Sudo privileges on the target server(s).

## Playbook Details

### Tasks

1. **Install Apache HTTP Server**
    - Installs the `httpd` package.
    - Registers the result of the installation.

2. **Start Apache Service**
    - Starts the `httpd` service.
    - Runs only if the installation task results in changes.

3. **Enable Apache Service to Start on Boot**
    - Enables the `httpd` service to start on boot.
    - Runs only if the installation task results in changes.

4. **Create index.html File**
    - Creates a basic `index.html` file in the default web directory (`/var/www/html/`).

## Usage

1. Clone this repository:

    ```bash
    git clone https://github.com/yourusername/your-repo-name.git
    cd your-repo-name
    ```

2. Update the `hosts` field in the playbook to target your server(s):

    ```yaml
    hosts: your_target_server
    ```

3. Run the playbook with the following command:

    ```bash
    ansible-playbook -i your_inventory_file playbook.yml
    ```

    Replace `your_inventory_file` with the path to your Ansible inventory file.

## Example

### Inventory File

Create an inventory file named `hosts`:

```ini
[webservers]
192.168.1.10 ansible_user=your_user
