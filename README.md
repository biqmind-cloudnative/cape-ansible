# Deploy CAPE and Kubernetes with Docker

<p align="center" style="background-color:#23327c">
  <img src="https://raw.githubusercontent.com/cape-sh/cape/master/assets/logo.png" height="250px" width="400px"/>
</p>

#### Recommended System requirements

```
OS: Centos 7.3/7.4/7.5  
CPU: 2 core
RAM : 4GB RAM
Disk Space: 10 GB free 
Server Internet access : yes
```
---

# How to deploy CAPE SAAS

> Do the below steps as "root" user in the machine where you want to deploy.

Do you want to access CapeUI with local private IP env.

>   Eg: If you and your VM is at home and you want IP like 192.168.1.7 to access
 
```bash
wget https://raw.githubusercontent.com/cape-sh/cape-k3s-ansible-deployment/master/script/capesaaPvtIP.sh
sh capesaaPvtIP.sh
```

Do you want to access CapeUI with Public IP env.

>   Eg: If your VM is on cloud and have public ip 

```bash
wget https://raw.githubusercontent.com/cape-sh/cape-k3s-ansible-deployment/master/script/capesaasPubIP.sh
sh capesaasPubIP.sh
```
===

### Now access the CAPE GUI 

Service may take 1-5 mins to come up based on server config and internet bandwidth.

> URL

```
http://<Your_server_ip>.nip.io/
```
** All CAPE documentation is available [here](https://docs.cape.sh/docs/) **


===

### What the different Ansible Roles do:

```
 Ansible Roles :
 
 1. Prereq: PreRequisite config at os layer eg: Autoconfigure all repositories , SELinux , disable firewall etc.
 2. Download: Downloads all the relevant packages and scripts
 3. K3S : Installs k3s , crictl master on centos7/RHEL7 
 4. Cape : Installs the Cape SAAS application & Enable access to CAPE GUI via URL
 5. Reset : Uninstall kubernetes packages from your machine 
``` 

---

### Troubleshooting 

Login as root to your machine

```bash
kubectl get pods -n cape
```
Make sure all pods are in a healthy state else kill any unhealthy pods and they will restart in few seconds

### To RESET everything  using playbook

Login as root to your machine

> Run this playbook to uninstall Kubernetes and crictl

```bash
cd cape-k3s-ansible-deployment
ansible-playbook reset.yml
```
> "cape-k3s-ansible-deployment" directory is located where capesaasPubIP.sh or capesaasPvtIP.sh script was downloaded 



## Getting Started with CAPE

Get started quickly using this [tutorial](https://docs.cape.sh/docs/simple-install)


## Getting Involved

We appreciate your feedback and active participation.

If you want to get in touch with us to discuss improvements and new
features, please [create a new issue on GitHub][1] or connect with us over on Slack:

* [`#general` Slack channel](https://capesh.slack.com)

## Reporting Bugs

If you encounter a bug, please [create a new issue on GitHub](https://github.com/cape-sh/cape/issues/new) or talk to us
on our [`#general` Slack channel](https://capesh.slack.com). When reporting a bug please include the
following information:






