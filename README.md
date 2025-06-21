cat <<EOF > README.md
# 🧠 Ansible Network Automation Lab

Welcome to my personal Ansible lab! This repository showcases how I use Ansible to automate network device configurations, structure scalable playbooks, and manage encrypted variables using Ansible Vault.

## 🔧 What This Lab Demonstrates

- Automated VLAN creation on Cisco IOSv switches
- Secure handling of device credentials using Ansible Vault
- Scalable inventory and group/host variable structure
- Git-managed Infrastructure-as-Code (IaC) workflow

## 📁 Repository Structure

(ansible-lab/)
├── inventory/
│   └── hosts.yml         - Lab device inventory (YAML)
├── group_vars/
│   └── all.yml           - Encrypted variables (e.g., credentials)
├── host_vars/            - (Optional) Per-device variables
├── playbooks/
│   └── create_vlans.yml  - Main playbook to configure VLANs
├── .gitignore            - Sensitive paths and files excluded from Git
├── README.md             - You're reading it!

## 🚀 Getting Started

Clone the repo:

    git clone git@github.com:gamingsurge/ansible-lab.git
    cd ansible-lab

### 🔐 Ansible Vault Usage

To view/edit encrypted vars:

    ansible-vault view group_vars/all.yml
    ansible-vault edit group_vars/all.yml

To run playbooks:

    ansible-playbook -i inventory/hosts.yml playbooks/create_vlans.yml --ask-vault-pass

## 📌 Inventory Example

    all:
      children:
        ios_switches:
          hosts:
            sw1:
              ansible_host: 192.168.1.101
            sw2:
              ansible_host: 192.168.1.102

## 🌐 About This Lab Environment

- Platform: Ansible on Docker container (or Linux VM)
- Targets: Cisco IOSv virtual switches (CML, GNS3)
- Purpose: Skill development in Ansible, GitOps, and network automation

## 📬 Contact

- GitHub: https://github.com/gamingsurge
- Website: https://serginetworks.com

EOF
