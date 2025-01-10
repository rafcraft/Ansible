# Ansible Playbook for Various Roles

## Table of Contents
- [Description](#description)
- [Requirements](#requirements)
- [Setup](#setup)
- [Running the Playbook](#running-the-playbook)
- [Project Structure](#project-structure)
- [Roles and Required Files](#roles-and-required-files)
- [Troubleshooting](#troubleshooting)

## Description
This repository contains Ansible playbooks to install and configure various services on your servers. It includes multiple roles such as `nginx`, `PHP`, `postgresql`, `zabbix`, and others to manage installation, configuration, and service management.

## Requirements
- Ansible 2.9 or higher
- Access to the servers you want to manage via SSH
- Properly configured inventory file

## Setup

### Clone the repository:
```sh
git clone https://github.com/rafcraft/Ansible.git
cd Ansible
```

### Install Ansible if you haven't already:
```sh
sudo apt-get update
sudo apt-get install ansible
```

## Running the Playbook
To run the main playbook with a specified inventory file, use the following command:
```sh
ansible-playbook -i inventory/inventory.yml playbook/main.yml
```

## Project Structure
The repository is structured as follows:
```plaintext
Ansible/
├── inventory
│   └── inventory.yml
├── playbook
│   └── main.yml
├── README.md
└── roles
    ├── borgbackup
    │   └── tasks
    │       └── main.yml
    ├── nginx
    │   ├── files
    │   │   └── options-ssl-nginx.conf
    │   ├── tasks
    │   │   └── main.yml
    │   └── vars
    │       └── main.yml
    ├── oracle_instantclient
    │   ├── files
    │   ├── tasks
    │   │   └── main.yml
    │   └── vars
    │       └── main.yml
    ├── PHP
    │   ├── files
    │   │   ├── php-fpm.conf
    │   │   └── php.ini
    │   ├── tasks
    │   │   └── main.yml
    │   └── vars
    │       └── main.yml
    ├── postgresql
    │   ├── tasks
    │   │   └── main.yml
    │   └── vars
    │       └── main.yml
    ├── users
    │   ├── tasks
    │   │   └── main.yml
    │   └── vars
    │       └── main.yml
    └── zabbix
        ├── files
        ├── handlers
        │   └── main.yml
        ├── tasks
        │   └── main.yml
        └── vars
            └── main.yml
```

## Roles and Required Files

### 1. Role: nginx
- **Path:** `roles/nginx`
- **Required Files:**
  - Configuration File: `roles/nginx/files/options-ssl-nginx.conf`
  - Variables File: `roles/nginx/vars/main.yml`
- **Tasks:** Install and configure Nginx.

### 2. Role: PHP
- **Path:** `roles/PHP`
- **Required Files:**
  - Configuration Files:
    - `roles/PHP/files/php-fpm.conf`
    - `roles/PHP/files/php.ini`
  - Variables File: `roles/PHP/vars/main.yml`
- **Tasks:** Install and configure PHP.

### 3. Role: postgresql
- **Path:** `roles/postgresql`
- **Required Files:**
  - Variables File: `roles/postgresql/vars/main.yml`
- **Tasks:** Install and configure PostgreSQL.

### 4. Role: zabbix
- **Path:** `roles/zabbix`
- **Required Files:**
  - Handlers File: `roles/zabbix/handlers/main.yml`
  - Variables File: `roles/zabbix/vars/main.yml`
- **Tasks:** Install and configure Zabbix.

### 5. Role: oracle_instantclient
- **Path:** `roles/oracle_instantclient`
- **Required Files:**
  - Variables File: `roles/oracle_instantclient/vars/main.yml`
- **Tasks:** Install and configure Oracle Instant Client.

### 6. Role: borgbackup
- **Path:** `roles/borgbackup`
- **Tasks:** Install and configure BorgBackup.

### 7. Role: users
- **Path:** `roles/users`
- **Required Files:**
  - Variables File: `roles/users/vars/main.yml`
- **Tasks:** Manage user accounts.

## Troubleshooting
If you encounter any issues:

1. Make sure all required files and directories are present.
2. Verify SSH access to the servers listed in your inventory.
3. Check the Ansible version compatibility.

For any further assistance, please open an issue on the repository.

---
**Note:** Ensure you create and populate the missing directories and configuration files before running the playbook to avoid any errors during execution.
