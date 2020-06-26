# Welcome to CAPE
<p align="center" style="background-color:#23327c">
  <img src="https://raw.githubusercontent.com/cape-sh/cape/master/assets/logo.png" height="125px" width="200px"/>
</p>

**About**

Organizations struggle to manage their Kubernetes clusters at a level expected by various stakeholders; they are debilitated by a lack of resources, expertise and tools. Organizations need to overcome these obstacles and become Kubernetes-ready. CAPE will provide organizations with the tooling and ability to perform:

- Disaster Recovery
  - Utilize Velero, an open source Kubernetes tool for backup & restore
  - Perform single scheduled backup & restore
  - Perform multi-cluster & multi-cloud backup & restore
- Multi-cluster application deployment
- Multi-cluster DNS and ingress

CAPE enables you to manage Kubernetes clusters on day one without specialized knowledge or proprietary API/CLI experience.

---

**Find out more about CAPE:**

[![](http://img.youtube.com/vi/4KJt8NXTO8E/0.jpg)](http://www.youtube.com/watch?v=4KJt8NXTO8E "Biqmind Cape")


---

## Try CAPE SAAS for FREE

### Install CAPE

> There are 2 options for accessing CAPE. Follow one of the options below as "root" user on the machine that you want to deploy to.

Option 1: 

Access CAPE UI with a local private IP env.

>   Eg: You and your VM are at home and you want to access using a private IP e.g., 192.168.1.7
 
```bash
curl https://raw.githubusercontent.com/cape-sh/cape-ansible/master/script/capesaaPvtIP.sh > capesaaPvtIP.sh
sh capesaaPvtIP.sh
```

Option 2:

Access CAPE UI with a public IP env.

>   Eg: Your VM is in the cloud and has a public IP e.g., 13.103.25.99

```bash
curl  https://raw.githubusercontent.com/cape-sh/cape-ansible/master/script/capesaasPubIP.sh > capesaasPubIP.sh
sh capesaasPubIP.sh
```
---

### Access CAPE UI 

The service may take 1-5 mins to come up based on the server config and the internet bandwidth.

> URL

```
http://<Your_server_ip>.nip.io/
```
** All CAPE documentation is available [here](https://docs.cape.sh/docs/) **

---

### What do the different Ansible roles do?

```
 1. Prereq: Prerequisite config at the os layer e.g., autoconfigure all repositories , SELinux , disable firewall etc.
 2. Download: Downloads all the relevant packages and scripts
 3. K3S: Installs k3s, crictl master on centos7/RHEL7 
 4. Cape: Installs the CAPE SAAS application & enables access to CAPE GUI via URL
 5. Reset: Uninstalls the Kubernetes packages from your machine 
``` 
---

### Troubleshooting 

Login as root to your machine

```bash
kubectl get pods -n cape
```
Make sure all pods are in a healthy state else kill any unhealthy pods and they will restart within a few seconds

---

### RESET everything using playbook

Login as root to your machine

> Run this playbook to uninstall Kubernetes and crictl

```bash
cd cape-ansible
ansible-playbook reset.yml
```
> "cape-ansible" directory is located where the capesaasPubIP.sh or capesaasPvtIP.sh script was downloaded earlier.

---

### Recommended System requirements

```
OS: Centos 7.3/7.4/7.5  
CPU: 2 core
RAM: 4GB RAM
Disk Space: 10 GB free 
Server Internet access: Yes
```

---

## Get Started with CAPE

Use this [tutorial](https://docs.cape.sh/docs/simple-install) to get started quickly.


## Get Involved

We appreciate your feedback and active participation.

If you want to get in touch with us to discuss improvements and new
features, please [create a new issue on GitHub](https://github.com/cape-sh/cape/issues/new) or connect with us over on Slack:

* [`#general` Slack channel](https://capesh.slack.com)







