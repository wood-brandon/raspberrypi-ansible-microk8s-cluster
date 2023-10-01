# Raspberry Pi Kubernetes cluster - Ansible setup
This is my custom script for setting up a Raspberry Pi cluster, and running Kubernetes on it. This will:
 - Set up Pis, including configuring cgroup memory for kubernetes
 - Install kubernetes and reccomended dependencies
 - Set up one master node and N worker nodes, and automatically create a working cluster

## Requirements
 - At least two Raspberry Pis (minimum one control node, one worker node)
 - Pis should run Ubuntu Server
 - SSH access with publickey authentication setup from the same computer running the playbook

## Setup
Create your inventory file `inventory/inventory.yml`. This should follow the format of `inventory/inventory_template`

```bash
touch inventory/inventory.yml
```

Then, edit the `inventory/group_vars/cluster.yml` file to the correct SSH host name of your Raspberry pi's (default `ubuntu`)

## Usage
The script can be run by executing the `cluser.yml` playbook:

```bash
ansible-playbook cluster.yml -i inventory/inventory.yml
```
