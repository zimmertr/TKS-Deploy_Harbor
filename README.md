# TKS - Deploy Harbor

This repository can be used on its own but it is intended to be used as a submodule of [TKS](https://github.com/zimmertr/TKS). TKS enables enthusiasts and administrators alike to easily provision highly available and production-ready Kubernetes clusters and other modern infrastructure on Proxmox VE. 

* [Summary](#Summary)
* [Requirements](#Requirements)
* [Instructions](#Instructions)
<hr>

## Summary

`Deploy Harbor` deploys an instance of Harbor to Proxmox.
<hr>

## Requirements

This project assumes you have a working [Proxmox server](https://github.com/zimmertr/TKS-Bootstrap_Proxmox) and leverages Telmate's [Terraform provider](https://github.com/Telmate/terraform-provider-proxmox). It uses a VM template produced by [TKS-Build_Template](https://github.com/zimmertr/TKS-Build_Template).
<hr>

## Instructions


1. Deploy a VM, configure DNS, install an SSH key, define your inventory.

   ```bash
   # Terraform to come
   ```

2. Configure Ansible using environment variables.

    ```bash
    export ANSIBLE_REMOTE_USER="root"
    export ANSIBLE_ASK_PASS=false
    export ANSIBLE_PRIVATE_KEY_FILE="~/.ssh/sol.milkyway.harbor"
    ```

3.  Configure variables, retrieve an SSL certificate, and deploy Harbor.

    ```bash
    certbot certonly -d harbor.tjzimmerman.dev
    vim roles/deploy_harbor/vars/main.yml
    ansible-playbook -i inventory.yml TKS-Deploy_Harbor/deploy_harbor.yml
    ```

