# TKS Deploy Harbor

## Summary

Deploy Harbor Container Registry to Proxmox

## Warning

This is a demo, SSL is not used and repeatability is not guaranteed. Tested against CentOS 7 minimal.

## Instructions

0) Deploy a VM, configure DNS, install an SSH key, define your inventory.

1) Configure Ansible using environment variables.

```bash
   export ANSIBLE_REMOTE_USER="root"
   export ANSIBLE_ASK_PASS=false
   export ANSIBLE_PRIVATE_KEY_FILE="~/.ssh/sol.milkyway.harbor"
```

2) Configure variables for roles and deploy Harbor.

```bash
    vim roles/deploy_harbor/vars/main.yml
    ansible-playbook -i inventory.yml TKS-Deploy_Harbor/deploy_harbor.yml
```

